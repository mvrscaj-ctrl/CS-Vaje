┌──(kali㉿kali)-[~]
└─$ sudo apt update
sudo apt install gnupg
[sudo] password for kali: 
Hit:1 http://http.kali.org/kali kali-rolling InRelease
1905 packages can be upgraded. Run 'apt list --upgradable' to see them.
Upgrading:                      
  dirmngr  gnupg  gnupg-l10n  gpg  gpg-agent  gpg-wks-client  gpgconf  gpgsm

Summary:
  Upgrading: 8, Installing: 0, Removing: 0, Not Upgrading: 1897
  Download size: 2,957 kB
  Freed space: 31.7 kB

Continue? [Y/n] y
Get:1 http://kali.download/kali kali-rolling/main amd64 gpg-wks-client amd64 2.4.9-4 [106 kB]
Get:2 http://mirror.pyratelan.org/kali kali-rolling/main amd64 dirmngr amd64 2.4.9-4 [382 kB]                   
Get:3 http://kali.download/kali kali-rolling/main amd64 gpg-agent amd64 2.4.9-4 [270 kB]                        
Get:7 http://mirror.karneval.cz/pub/linux/kali kali-rolling/main amd64 gpgsm amd64 2.4.9-4 [275 kB]             
Get:6 http://mirror.init7.net/kali kali-rolling/main amd64 gnupg all 2.4.9-4 [415 kB]                           
Get:5 http://kali.download/kali kali-rolling/main amd64 gpgconf amd64 2.4.9-4 [126 kB]                    
Get:8 http://kali.download/kali kali-rolling/main amd64 gnupg-l10n all 2.4.9-4 [749 kB]                         
Get:4 http://mirror1.sox.rs/kali/kali kali-rolling/main amd64 gpg amd64 2.4.9-4 [635 kB]                        
Fetched 2,957 kB in 1s (3,246 kB/s)                                                                             
(Reading database ... 422826 files and directories currently installed.)
Preparing to unpack .../0-gpg-wks-client_2.4.9-4_amd64.deb ...
Unpacking gpg-wks-client (2.4.9-4) over (2.4.8-4) ...
Preparing to unpack .../1-dirmngr_2.4.9-4_amd64.deb ...
Unpacking dirmngr (2.4.9-4) over (2.4.8-4) ...
Preparing to unpack .../2-gpg-agent_2.4.9-4_amd64.deb ...
Unpacking gpg-agent (2.4.9-4) over (2.4.8-4) ...
Preparing to unpack .../3-gpg_2.4.9-4_amd64.deb ...
Unpacking gpg (2.4.9-4) over (2.4.8-4) ...
Preparing to unpack .../4-gpgconf_2.4.9-4_amd64.deb ...
Unpacking gpgconf (2.4.9-4) over (2.4.8-4) ...
Preparing to unpack .../5-gnupg_2.4.9-4_all.deb ...
Unpacking gnupg (2.4.9-4) over (2.4.8-4) ...
Preparing to unpack .../6-gpgsm_2.4.9-4_amd64.deb ...
Unpacking gpgsm (2.4.9-4) over (2.4.8-4) ...
Preparing to unpack .../7-gnupg-l10n_2.4.9-4_all.deb ...
Unpacking gnupg-l10n (2.4.9-4) over (2.4.8-4) ...
Setting up gnupg-l10n (2.4.9-4) ...
Setting up gpgconf (2.4.9-4) ...
Setting up gpg (2.4.9-4) ...
Setting up gpg-agent (2.4.9-4) ...
Setting up gpgsm (2.4.9-4) ...
Setting up dirmngr (2.4.9-4) ...
Setting up gnupg (2.4.9-4) ...
Setting up gpg-wks-client (2.4.9-4) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for man-db (2.13.1-1) ...
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ gpg --full-generate-key
gpg (GnuPG) 2.4.9; Copyright (C) 2025 g10 Code GmbH
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

gpg: keybox '/home/kali/.gnupg/pubring.kbx' created
Please select what kind of key you want:
   (1) RSA and RSA
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
   (9) ECC (sign and encrypt) *default*
  (10) ECC (sign only)
  (14) Existing key from card
Your selection? 1
RSA keys may be between 1024 and 4096 bits long.
What keysize do you want? (3072) 4096
Requested keysize is 4096 bits
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0) 1y
Key expires at Mon 26 Apr 2027 08:03:22 AM EDT
Is this correct? (y/N) y

GnuPG needs to construct a user ID to identify your key.

Real name: Real student
Email address: realstudent@example.com
Comment: real
You selected this USER-ID:
    "Real student (real) <realstudent@example.com>"

Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? O
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
gpg: /home/kali/.gnupg/trustdb.gpg: trustdb created
gpg: directory '/home/kali/.gnupg/openpgp-revocs.d' created
gpg: revocation certificate stored as '/home/kali/.gnupg/openpgp-revocs.d/5AC39A8A93852335DBBA28FC9099A1F6225E6EBF.rev'
public and secret key created and signed.

pub   rsa4096 2026-04-26 [SC] [expires: 2027-04-26]
      5AC39A8A93852335DBBA28FC9099A1F6225E6EBF
uid                      Real student (real) <realstudent@example.com>
sub   rsa4096 2026-04-26 [E] [expires: 2027-04-26]

                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ gpg --list-keys
gpg: checking the trustdb
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
gpg: next trustdb check due at 2027-04-26
/home/kali/.gnupg/pubring.kbx
-----------------------------
pub   rsa4096 2026-04-26 [SC] [expires: 2027-04-26]
      5AC39A8A93852335DBBA28FC9099A1F6225E6EBF
uid           [ultimate] Real student (real) <realstudent@example.com>
sub   rsa4096 2026-04-26 [E] [expires: 2027-04-26]

                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ gpg --armor --export realstudent@example.com > student_pubkey.asc
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ ls -l         
total 60
drwxr-xr-x 2 kali kali 4096 Apr 26 08:07 Desktop
-rw-rw-r-- 1 kali kali  832 Apr 26 07:04 Dockerfile
-rw-rw-r-- 1 kali kali  832 Apr 26 07:06 Dockerfile.1
drwxr-xr-x 2 kali kali 4096 Apr 26 03:21 Documents
drwxr-xr-x 2 kali kali 4096 Apr  1 10:25 Downloads
-rw-rw-r-- 1 kali kali 9634 Apr 26 02:11 gists.txt
drwxr-xr-x 2 kali kali 4096 Apr  1 10:25 Music
-rw-rw-r-- 1 kali kali   30 Apr 26 07:41 passwords.txt
drwxr-xr-x 2 kali kali 4096 Apr  1 10:25 Pictures
drwxr-xr-x 2 kali kali 4096 Apr  1 10:25 Public
-rw-rw-r-- 1 kali kali 3163 Apr 26 08:06 student_pubkey.asc
drwxr-xr-x 2 kali kali 4096 Apr  1 10:25 Templates
drwxr-xr-x 2 kali kali 4096 Apr  1 10:25 Videos
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ cd Desktop 
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --import peer_pubkey.asc  
gpg: key 9D522C56D35989EE: public key "Robi Test (FIS) <robi@test.local>" imported
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
gpg: Total number processed: 1
gpg:               imported: 1
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --list-keys
/home/kali/.gnupg/pubring.kbx
-----------------------------
pub   rsa4096 2026-04-26 [SC] [expires: 2027-04-26]
      5AC39A8A93852335DBBA28FC9099A1F6225E6EBF
uid           [ultimate] Real student (real) <realstudent@example.com>
sub   rsa4096 2026-04-26 [E] [expires: 2027-04-26]

pub   rsa4096 2026-04-22 [SC] [expires: 2027-04-22]
      E90469DE46081E396BDC6C769D522C56D35989EE
uid           [ unknown] Robi Test (FIS) <robi@test.local>
sub   rsa4096 2026-04-22 [E] [expires: 2027-04-22]

                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ echo "To: peer@example.com
From: student@example.com
Date: $(date)
Secret message: Confidential message" > message.txt
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --encrypt --sign --armor --recipient peer@example.com message.txt
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
gpg: error retrieving 'peer@example.com' via WKD: No data
gpg: peer@example.com: skipped: No data
gpg: message.txt: sign+encrypt failed: No data
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpgconf --kil                                                        
usage: gpgconf [options] 
Need one component argument
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ sudo apt update gpg-agent
Error: The update command takes no arguments
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --encrypt --sign --armor --recipient peer@example.com message.txt
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
gpg: error retrieving 'peer@example.com' via WKD: No data
gpg: peer@example.com: skipped: No data
gpg: message.txt: sign+encrypt failed: No data
                                                                                                                                                                                                                                
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --encrypt --sign --armor --recipient peer@example.com message.txt
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
gpg: error retrieving 'peer@example.com' via WKD: No data
gpg: peer@example.com: skipped: No data
gpg: message.txt: sign+encrypt failed: No data
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --encrypt --sign --armor --recipient robi@test.local message.txt 
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
gpg: E8C8438D8A1E2F62: There is no assurance this key belongs to the named user

sub  rsa4096/E8C8438D8A1E2F62 2026-04-22 Robi Test (FIS) <robi@test.local>
 Primary key fingerprint: E904 69DE 4608 1E39 6BDC  6C76 9D52 2C56 D359 89EE
      Subkey fingerprint: 093C 5A1C 7FFE 66C8 7E6C  F88B E8C8 438D 8A1E 2F62

It is NOT certain that the key belongs to the person named
in the user ID.  If you *really* know what you are doing,
you may answer the next question with yes.

Use this key anyway? (y/N) y
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --decrypt message.txt.asc > decrypted_message.txt
gpg: encrypted with rsa4096 key, ID E8C8438D8A1E2F62, created 2026-04-22
      "Robi Test (FIS) <robi@test.local>"
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
gpg: public key decryption failed: No secret key
gpg: decryption failed: No secret key
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ cat decrypted_message.txt
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg gpgconf --kil all                                
gpg: Note: '--kil' is not considered an option
gpg: WARNING: no command supplied.  Trying to guess what you mean ...
usage: gpg [options] [filename]
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg gpgconf --kill all
gpg: Note: '--kill' is not considered an option
gpg: WARNING: no command supplied.  Trying to guess what you mean ...
usage: gpg [options] [filename]
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --encrypt --sign --armor --recipient realstudent@example.com message.txt
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
File 'message.txt.asc' exists. Overwrite? (y/N) y
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ gpg --decrypt message.txt.asc > decrypted_message.txt                       
gpg: encrypted with rsa4096 key, ID BF28DE018B39DBC0, created 2026-04-26
      "Real student (real) <realstudent@example.com>"
gpg: WARNING: server 'gpg-agent' is older than us (2.4.8 < 2.4.9)
gpg: Note: Outdated servers may lack important security fixes.
gpg: Note: Use the command "gpgconf --kill all" to restart them.
gpg: Signature made Sun 26 Apr 2026 08:22:43 AM EDT
gpg:                using RSA key 5AC39A8A93852335DBBA28FC9099A1F6225E6EBF
gpg: Good signature from "Real student (real) <realstudent@example.com>" [ultimate]
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ 
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ cat decrypted_message.txt
To: peer@example.com
From: student@example.com
Date: Sun Apr 26 08:09:21 AM EDT 2026
Secret message: Confidential message
                                                                                                                 
┌──(kali㉿kali)-[~/Desktop]
└─$ 
