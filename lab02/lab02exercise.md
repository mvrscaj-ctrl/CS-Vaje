For this to work you need to change in the settings of virtual machine network from NAT to BRIDGED and than you get a proper IP.

Report:

<?xml version="1.0" encoding='UTF-8'?>
<harvester>
   URL=http://127.0.0.1:8000/login.html
   <url>      <param>username=test</param>
      <param>password=password123</param>
   </url>
</harvester>


Victim could recognise fake site  by the url.

The goal of a phishing page is deception through mimicing the original site. While they look official, they almost always contain subtle technical or visual "tells."

URL anomalies:

Typosquatting: Using domains like g00gle.com or faceb0ok.com.

Subdomain Manipulation: A URL like paypal.security-update.com—where the actual domain is security-update.com, not PayPal.

Homograph Attacks: Using look-alike characters from different alphabets (e.g., a Cyrillic "а" instead of a Latin "a").

Urgency and Pressure: The content often uses "scare tactics," such as "Your account will be suspended in 2 hours" or "Unauthorized login detected," to bypass your critical thinking.

Input-Only Design: Unlike a real site, phishing pages often have broken links for the "About Us" or "Contact" sections. They are built only to capture the username and password field.

How to protect yourself

- Here you can only inspect URL.


Why Modern Sites Make Attacks Difficult
The web ecosystem has introduced several technical protocols that make it harder for attackers to impersonate legitimate brands.

1. HSTS (HTTP Strict Transport Security)
HSTS tells the browser that a site should only be accessed using HTTPS. This prevents "man-in-the-middle" attacks where an attacker tries to downgrade your connection to an unencrypted version to steal data.

2. SPF, DKIM, and DMARC
These are email authentication protocols. They allow a domain owner (like Google or Chase) to specify which mail servers are allowed to send emails on their behalf. If a phisher tries to "spoof" an official email address, these protocols help your inbox flag the message as "Spam" or "Dangerous" before you even see it.

3. FIDO2 and WebAuthn
Modern login standards are moving toward Hardware-backed authentication. Unlike a six-digit SMS code (which can be phished on a fake page), FIDO2 hardware keys (like YubiKeys) cryptographically "bind" the login to the specific domain. A hardware key will physically refuse to provide a credential if the domain in the browser is even slightly incorrect.

4. Sandboxing and Browser Protection
Modern browsers (Chrome, Firefox, Safari) maintain "Safe Browsing" lists. They constantly crawl the web for malicious pages; when you land on a known phishing site, the browser intercepts the connection and displays a full-screen red warning.