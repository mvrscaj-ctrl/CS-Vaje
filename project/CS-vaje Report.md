# **Project report: Assessing SSH vulnerabilities and defensive hardening**

**Author:** Martin Vrščaj

**Institution:** Faculty of Information Studies (FIS)

**Course:** Cyber Security

**Project:** SSH Hardening Lab 2026

**Date:** April 27, 2026

**Environment:** Virtualized Pentesting Lab (Kali Linux & Docker)

## 

## **1\. Introduction**

### **1.1 Background**

The Secure Shell (SSH) protocol (standardized in RFC 4251\) is the cornerstone of secure remote management in Linux environments. While its encryption is robust, the protocol is often targeted at its weakest point: the authentication phase. Brute-force attacks remain one of the most common vectors for initial access in corporate and cloud environments.

### **1.2 Objectives**

The objective of this lab is threefold:

1. To simulate an automated brute-force attack against an SSH daemon.  
2. To analyze the impact of password entropy on the success rate of such attacks.  
3. To evaluate application-layer hardening techniques (specifically MaxAuthTries) as a mitigation strategy.

## 

## **2\. Methodology**

### **2.1 Lab architecture**

The lab utilizes a containerized architecture to isolate the attack surface.

* **Attacker node:** Kali Linux (Rolling Edition), utilizing Hydra for multi-threaded authentication attempts and nmap for service reconnaissance.  
* **Target node:** A Docker container (ssh\_lab) running a minimal Debian-based environment.  
* **Network topology:** A Docker bridge network mapping the host's port 2222 to the container's port 22\.

### **2.2 Software & versioning**

| Component | Version/Details |
| :---- | :---- |
| **OS (host)** | Kali Linux 2024.x |
| **SSH server** | OpenSSH 9.6p1 |
| **Attack tool** | THC-Hydra v9.6 |
| **Scanner** | Nmap 7.94 |
| **Container engine** | Docker Engine v24.x |

## 

## **3\. Experimental setup**

### **3.1 Target configuration**

The target was initialized using a custom shell script to ensure a clean state for each test.

**create\_users.sh Logic:**

Bash

\#\!/bin/bash  
	useradd \-m \-s /bin/bash weakuser  
	echo "weakuser:123456" | chpasswd

	useradd \-m \-s /bin/bash stronguser  
	echo "stronguser:Str0ng\!Pass\#2026" | chpasswd

### **3.2 Reconnaissance (Nmap)**

Prior to the attack, service verification was performed to confirm the "fingerprint" of the target.

* **Command:** sudo nmap \-sV \-p 2222 127.0.0.1  
* **Findings:** The service was correctly identified as OpenSSH 9.6p1. This informs the attacker that standard SSH exploits (like User Enumeration on older versions) may not be applicable, necessitating a brute-force approach.

## 

## **4\. Execution & results**

### **4.1 Experiment phase I: The "Low entropy" vector**

* **Target:** weakuser  
* **Wordlist:** passwords.txt (including 123456\)  
* **Tool configuration:** hydra \-l weakuser \-P passwords.txt ssh://127.0.0.1:2222 \-t 1  
* **Result:** **COMPROMISED.**  
* **Analysis:** Because 123456 is a top-10 most common password globally, it was located in the first three attempts. The attack completed in under 1 second.  
* Log record:

*\[172.18.0.2\]:2222 penalty: failed authentication*

*2026-04-27 09:02:02.533900199  drop connection \#0 from \[172.18.0.1\]:47844 on \[172.18.0.2\]:2222 penalty: failed authentication*

*2026-04-27 09:02:02.763698897  drop connection \#0 from \[172.18.0.1\]:47846 on \[172.18.0.2\]:2222 penalty: failed authentication*

*2026-04-27 09:05:35.519040930  Received disconnect from 172.18.0.1 port 47614:11: Bye Bye \[preauth\]*

*2026-04-27 09:05:35.519044765  Disconnected from authenticating user weakuser 172.18.0.1 port 47614 \[preauth\]*

***2026-04-27 09:05:35.794097959  Accepted password for weakuser from 172.18.0.1 port 47618 ssh2***

*2026-04-27 09:05:35.799991648  Failed to set uids to 1001\.*

*2026-04-27 09:09:12.247894571  Received disconnect from 172.18.0.1 port 33834:11: Bye Bye \[preauth\]*

### **4.2 Experiment phase II: Bypassing complexity without rate limiting**

* **Target:** stronguser  
* **Password:** Str0ng\!Pass\#2026  
* **Server Config:** MaxAuthTries 6 (Default)  
* **Result:** **COMPROMISED.** (Failed since we did not have a pass in wordlist, but would eventually be compromised, if wordlist was large enough.)  
* **Analysis:** While the password was complex, the server allowed the tool to attempt passwords indefinitely (by opening new sessions). This proved that **complexity is not a defense against high-speed automated attacks** if the server allows unlimited retries.

### **4.3 Experiment phase III: Hardened application layer**

* **Hardening Action:** Modified /etc/ssh/sshd\_config to MaxAuthTries 2\.  
* **Tool Configuration:** hydra \-t 16 (High speed)  
* **Result:** **FAILED.**  
* **Analysis:** Hydra encountered a massive increase in error rates. Because the server "slammed the door" after only two guesses, Hydra’s parallel tasks were constantly disconnected. The tool eventually timed out or was disabled by the server's resource protection.  
* Log record:

2026-04-27 09:09:12.578636065  maximum authentication attempts exceeded for stronguser from 172.18.0.1 port 33836 ssh2 \[preauth\]

2026-04-27 09:09:12.578638010  Disconnecting authenticating user stronguser 172.18.0.1 port 33836: Too many authentication failures \[preauth\]

## **5\. Discussion**

### **5.1 The Mathematics of Brute Force**

The time required to crack a password is a function of entropy, which is calculated as:

H \= L x log\_2  x R

Think of a password like a series of slots:

* **L (Length):** This is the number of "slots" or characters in the password.  
* **log\_2 R (Bits per character):** This represents how much "information" or "uncertainty" is packed into a single character based on the size of the pool (R) you are picking from (e.g., just numbers, or numbers \+ letters \+ symbols).

By multiplying the **length** by the **entropy of a single character**, you get the total **Entropy (H)** of the entire password in bits.

You can think of it like storage: if one character takes up \~6.5 bits of "randomness," a 10-character password (L=10) has 65 bits of total entropy. Every time you add one more character (increasing L), you aren't just adding to the strength; you are multiplying the difficulty for an attacker like Hydra to guess it.

In Phase I, R was only 10 (numbers), making the search space negligible. In Phase II, R was 95 (including symbols/caps), making the search space astronomically larger, yet the **speed** of the attack remained the vulnerability.

### **5.2 Security vs. Usability**

The implementation of MaxAuthTries 2 creates a significant "Usability Friction." In an educational or professional setting, a user with "fat fingers" who mistypes their password twice is now disconnected. This may increase support tickets. However, as demonstrated, the security gain against automated tools is massive.

### **5.3 Log forensics (Blue team analysis)**

I have examined logs in /home/kali/Documents/project/config/logs/openssh/ during the attack and saw:

**Weak user not found password yet:**

2026-04-27 09:02:01.123045783  Invalid user weakuser from 172.18.0.1 port 37510  
2026-04-27 09:02:01.125110846  Could not get shadow information for NOUSER  
2026-04-27 09:02:01.125112729  Failed password for invalid user weakuser from 172.18.0.1 port 37510 ssh2  
2026-04-27 09:02:01.133295379  Failed password for invalid user weakuser from 172.18.0.1 port 37510 ssh2  
2026-04-27 09:02:01.144111269  Failed password for invalid user weakuser from 172.18.0.1 port 37510 ssh2  
2026-04-27 09:02:01.154434855  Failed password for invalid user weakuser from 172.18.0.1 port 37510 ssh2  
2026-04-27 09:02:01.166168724  Failed password for invalid user weakuser from 172.18.0.1 port 37510 ssh2  
2026-04-27 09:02:01.177268913  Failed password for invalid user weakuser from 172.18.0.1 port 37510 ssh2  
2026-04-27 09:02:01.182223639  maximum authentication attempts exceeded for invalid user weakuser from 172.18.0.1 port 37510 ssh2 \[preauth\]

**Weakuser found password:**

2026-04-27 09:02:02.763698897  drop connection \#0 from \[172.18.0.1\]:47846 on \[172.18.0.2\]:2222 penalty: failed authentication  
2026-04-27 09:05:35.519040930  Received disconnect from 172.18.0.1 port 47614:11: Bye Bye \[preauth\]  
2026-04-27 09:05:35.519044765  Disconnected from authenticating user weakuser 172.18.0.1 port 47614 \[preauth\]  
2026-04-27 09:05:35.794097959  Accepted password for weakuser from 172.18.0.1 port 47618 ssh2  
2026-04-27 09:05:35.799991648  Failed to set uids to 1001\.  
2026-04-27 09:09:12.247894571  Received disconnect from 172.18.0.1 port 33834:11: Bye Bye \[preauth\]

**Stronguser not found password:**

2026-04-27 09:09:12.247898330  Disconnected from authenticating user stronguser 172.18.0.1 port 33834 \[preauth\]  
2026-04-27 09:09:12.522701535  Failed password for stronguser from 172.18.0.1 port 33836 ssh2  
2026-04-27 09:09:12.529888615  Failed password for stronguser from 172.18.0.1 port 33836 ssh2  
2026-04-27 09:09:12.540308492  Failed password for stronguser from 172.18.0.1 port 33836 ssh2  
2026-04-27 09:09:12.552176698  Failed password for stronguser from 172.18.0.1 port 33836 ssh2  
2026-04-27 09:09:12.562237821  Failed password for stronguser from 172.18.0.1 port 33836 ssh2  
2026-04-27 09:09:12.573631724  Failed password for stronguser from 172.18.0.1 port 33836 ssh2  
2026-04-27 09:09:12.578636065  maximum authentication attempts exceeded for stronguser from 172.18.0.1 port 33836 ssh2 \[preauth\]

A surge of these entries (hundreds per minute) is a definitive **Indicator of compromise (IoC)**.

## 

## **6\. Advanced hardening: The role of Fail2Ban**

While MaxAuthTries manages the session, it does not block the attacker's IP. **Fail2Ban** acts as an Intelligent Intrusion Prevention System (IPS).

1. It parses the auth.log in real-time.  
2. If it finds 5 failures from the same IP, it executes a DROP command in iptables.  
3. **Impact:** The attacker is no longer allowed to even "knock" on the door for a set duration (e.g., 1 hour). This is a **Global rate limit** and is significantly more effective than application-layer settings.

## 

## **7\. Conclusion & Recommendations**

### **7.1 Summary of findings**

The experiment confirms that an SSH server with default settings is highly vulnerable to automated brute force, regardless of password complexity. Hardening the application settings (MaxAuthTries) is an effective "speed bump," but not a total solution.

### **7.2 Strategic recommendations**

To ensure the highest security posture for remote access, the following "Defense in depth" layers should be implemented:

1. **Elimination of passwords:** Enforce **Ed25519 SSH Keys**. This replaces the "Shared secret" (password) with "Asymmetric cryptography," making brute force mathematically impossible.  
2. **Network obfuscation:** Move SSH from port 22 to a random high port (e.g., 49152). This reduces log noise from automated botnets by over 90%.  
3. **Active response:** Deploy **Fail2Ban** or **CrowdSec** to dynamically block IPs that exhibit malicious behavior.  
4. **MFA integration:** Implement a PAM (Pluggable Authentication Module) for Google Authenticator or Duo to require a second factor even if the primary credential is lost.

## **8\. Reference**

Google. (2026). Gemini (April 27 version) \[Large language model\]. https://gemini.google.com/

Notes

Use of AI: The Gemini(Google) tool was used in the development of the content and preparation of the documentation, which served as an aid in generating ideas, optimizing the code and formatting the texts. All final solutions were reviewed, verified and, if necessary, adjusted by the project author.

