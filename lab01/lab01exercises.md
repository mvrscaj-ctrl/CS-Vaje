┌──(kali㉿kali)-[~]
└─$ whoami
kali
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ hostnamectl
 Static hostname: kali
       Icon name: computer-vm
         Chassis: vm 🖴
      Machine ID: b69758c0cad3481e967dcad827001d56
         Boot ID: dcbd67f489f6485ab31aa73002c20748
  Virtualization: oracle
Operating System: Kali GNU/Linux Rolling          
          Kernel: Linux 6.16.8+kali-amd64
    Architecture: x86-64
 Hardware Vendor: innotek GmbH
  Hardware Model: VirtualBox
Hardware Version: 1.2
Firmware Version: VirtualBox
   Firmware Date: Fri 2006-12-01
    Firmware Age: 19y 4month 3w 3d                
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ uname /a
uname: extra operand ‘/a’
Try 'uname --help' for more information.
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ uname -a
Linux kali 6.16.8+kali-amd64 #1 SMP PREEMPT_DYNAMIC Kali 6.16.8-1kali1 (2025-09-24) x86_64 GNU/Linux
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ df -h
Filesystem      Size  Used Avail Use% Mounted on
udev            883M     0  883M   0% /dev
tmpfs           198M  968K  197M   1% /run
/dev/sda1        79G   16G   59G  21% /
tmpfs           986M  4.0K  986M   1% /dev/shm
none            1.0M     0  1.0M   0% /run/credentials/systemd-journald.service
tmpfs           986M   20K  986M   1% /tmp
none            1.0M     0  1.0M   0% /run/credentials/getty@tty1.service
tmpfs           198M  104K  198M   1% /run/user/1000
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:63:b0:05 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute eth0
       valid_lft 85491sec preferred_lft 85491sec
    inet6 fd17:625c:f037:2:990f:39da:ed99:9036/64 scope global dynamic noprefixroute 
       valid_lft 85955sec preferred_lft 13955sec
    inet6 fe80::7e46:5e20:346d:ad10/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ wget https://gist.githubusercontent.com/EdwardRayl/3436572afde8ce9e3faf5b7b95356a49/raw/6b25895fce480713560829dec31ac8220ffe5272/gists.txt
--2026-04-26 02:11:26--  https://gist.githubusercontent.com/EdwardRayl/3436572afde8ce9e3faf5b7b95356a49/raw/6b25895fce480713560829dec31ac8220ffe5272/gists.txt
Resolving gist.githubusercontent.com (gist.githubusercontent.com)... 185.199.109.133, 185.199.110.133, 185.199.111.133, ...
Connecting to gist.githubusercontent.com (gist.githubusercontent.com)|185.199.109.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9634 (9.4K) [text/plain]
Saving to: ‘gists.txt’

gists.txt                    100%[===========================================>]   9.41K  --.-KB/s    in 0s      

2026-04-26 02:11:26 (43.0 MB/s) - ‘gists.txt’ saved [9634/9634]

                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ sudo apt install 7zip
[sudo] password for kali: 
Upgrading:                      
  7zip
                                                                                                                 
Summary:
  Upgrading: 1, Installing: 0, Removing: 0, Not Upgrading: 1810
  Download size: 1,608 kB
  Freed space: 1,024 B

Err:1 http://http.kali.org/kali kali-rolling/main amd64 7zip amd64 26.00+dfsg-4
  404  Not Found [IP: 54.39.128.230 80]
Error: Failed to fetch http://http.kali.org/kali/pool/main/7/7zip/7zip_26.00%2bdfsg-4_amd64.deb  404  Not Found [IP: 54.39.128.230 80]
Error: Unable to fetch some archives, maybe run apt update or try with --fix-missing?
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ sudo apt update      
Get:1 http://mirror.init7.net/kali kali-rolling InRelease [34.0 kB]
Get:2 http://mirror.init7.net/kali kali-rolling/main amd64 Packages [21.1 MB]
Get:3 http://mirror.init7.net/kali kali-rolling/main amd64 Contents (deb) [53.4 MB]
Get:4 http://mirror.init7.net/kali kali-rolling/contrib amd64 Packages [118 kB]
Get:5 http://mirror.init7.net/kali kali-rolling/contrib amd64 Contents (deb) [274 kB]
Get:6 http://mirror.init7.net/kali kali-rolling/non-free amd64 Packages [188 kB]
Get:7 http://mirror.init7.net/kali kali-rolling/non-free amd64 Contents (deb) [907 kB]
Get:8 http://mirror.init7.net/kali kali-rolling/non-free-firmware amd64 Packages [15.3 kB]
Get:9 http://mirror.init7.net/kali kali-rolling/non-free-firmware amd64 Contents (deb) [38.7 kB]
Fetched 76.1 MB in 7s (10.4 MB/s)                                                                               
1906 packages can be upgraded. Run 'apt list --upgradable' to see them.
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ sudo apt install 7zip
Upgrading:                      
  7zip
                                                                                                                 
Summary:
  Upgrading: 1, Installing: 0, Removing: 0, Not Upgrading: 1905
  Download size: 1,607 kB
  Freed space: 1,024 B

Get:1 http://http.kali.org/kali kali-rolling/main amd64 7zip amd64 26.00+dfsg1-2 [1,607 kB]
Fetched 1,607 kB in 1s (1,896 kB/s)
(Reading database ... 422160 files and directories currently installed.)
Preparing to unpack .../7zip_26.00+dfsg1-2_amd64.deb ...
Unpacking 7zip (26.00+dfsg1-2) over (25.01+dfsg-4) ...
Setting up 7zip (26.00+dfsg1-2) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for man-db (2.13.1-1) ...
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ which nmap
/usr/bin/nmap
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ which john
/usr/sbin/john
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ cd /
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ ls -la
total 976640
drwxr-xr-x  18 root root       4096 Dec  2 22:02 .
drwxr-xr-x  18 root root       4096 Dec  2 22:02 ..
lrwxrwxrwx   1 root root          7 Nov 10 04:50 bin -> usr/bin
drwxr-xr-x   3 root root       4096 Dec  2 22:03 boot
drwxr-xr-x  18 root root       3240 Apr 26 01:55 dev
drwxr-xr-x 181 root root      12288 Apr 26 01:55 etc
drwxr-xr-x   3 root root       4096 Dec  2 21:36 home
lrwxrwxrwx   1 root root         33 Dec  2 22:02 initrd.img -> boot/initrd.img-6.16.8+kali-amd64
lrwxrwxrwx   1 root root         33 Dec  2 22:02 initrd.img.old -> boot/initrd.img-6.16.8+kali-amd64
lrwxrwxrwx   1 root root          7 Nov 10 04:50 lib -> usr/lib
lrwxrwxrwx   1 root root          9 Dec  2 21:33 lib32 -> usr/lib32
lrwxrwxrwx   1 root root          9 Nov 10 04:50 lib64 -> usr/lib64
drwx------   2 root root      16384 Dec  2 22:01 lost+found
drwxr-xr-x   2 root root       4096 Dec  2 21:29 media
drwxr-xr-x   2 root root       4096 Dec  2 21:29 mnt
drwxr-xr-x   3 root root       4096 Dec  2 21:33 opt
dr-xr-xr-x 220 root root          0 Apr 26 01:55 proc
drwx------   5 root root       4096 Apr 26 01:55 root
drwxr-xr-x  36 root root        860 Apr 26 01:56 run
lrwxrwxrwx   1 root root          8 Nov 10 04:50 sbin -> usr/sbin
drwxr-xr-x   3 root root       4096 Dec  2 21:34 srv
-rw-------   1 root root 1000000000 Dec  2 22:02 swap
dr-xr-xr-x  13 root root          0 Apr 26 01:55 sys
drwxrwxrwt  12 root root        320 Apr 26 02:12 tmp
drwxr-xr-x  15 root root       4096 Dec  2 21:33 usr
drwxr-xr-x  12 root root       4096 Apr  1 10:23 var
lrwxrwxrwx   1 root root         30 Dec  2 22:02 vmlinuz -> boot/vmlinuz-6.16.8+kali-amd64
lrwxrwxrwx   1 root root         30 Dec  2 22:02 vmlinuz.old -> boot/vmlinuz-6.16.8+kali-amd64
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ htop       
Command 'htop' not found, but can be installed with:
sudo apt install htop
Do you want to install it? (N/y)y
sudo apt install htop
Installing:                     
  htop
                                                                                                                 
Suggested packages:
  strace

Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1905
  Download size: 222 kB
  Space needed: 578 kB / 63.1 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 htop amd64 3.5.0-1 [222 kB]
Fetched 222 kB in 0s (469 kB/s)
Selecting previously unselected package htop.
(Reading database ... 422160 files and directories currently installed.)
Preparing to unpack .../htop_3.5.0-1_amd64.deb ...
Unpacking htop (3.5.0-1) ...
Setting up htop (3.5.0-1) ...
Processing triggers for mailcap (3.75) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for desktop-file-utils (0.28-1) ...
Processing triggers for hicolor-icon-theme (0.18-2) ...
Processing triggers for man-db (2.13.1-1) ...
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ htop
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ sudo apt install btop
Installing:                     
  btop
                                                                                                                 
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1905
  Download size: 631 kB
  Space needed: 2,003 kB / 63.1 GB available

Get:1 http://mirror.pyratelan.org/kali kali-rolling/main amd64 btop amd64 1.4.6-2 [631 kB]
Fetched 631 kB in 1s (711 kB/s)
Selecting previously unselected package btop.
(Reading database ... 422171 files and directories currently installed.)
Preparing to unpack .../btop_1.4.6-2_amd64.deb ...
Unpacking btop (1.4.6-2) ...
Setting up btop (1.4.6-2) ...
Processing triggers for mailcap (3.75) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for desktop-file-utils (0.28-1) ...
Processing triggers for hicolor-icon-theme (0.18-2) ...
Processing triggers for man-db (2.13.1-1) ...
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ btop
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ htop
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ sudo apt install traceroute -y
traceroute is already the newest version (1:2.1.6-1).
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 1905
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ traceroute arnes.si
arnes.si: No address associated with hostname
Cannot handle "host" cmdline arg `arnes.si' on position 1 (argc 1)
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ traceroute www.arnes.si
traceroute to www.arnes.si (193.2.1.67), 30 hops max, 60 byte packets
 1  10.0.2.2 (10.0.2.2)  1.839 ms  1.725 ms  1.408 ms
 2  * * *
 3  * * *
 4  * * *
 5  * * *
 6  * * *
 7  * * *
 8  * * *
 9  * * *
10  * * *
11  * * *
12  * * *
13  * * *
14  * * *
15  * * *
16  * * *
17  * * *^C
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ sudo apt install nload -y     
Installing:                     
  nload
                                                                                                                 
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1905
  Download size: 71.8 kB
  Space needed: 215 kB / 63.1 GB available

Get:1 http://http.kali.org/kali kali-rolling/main amd64 nload amd64 0.7.4+git20180309.8f92dc0-0.1 [71.8 kB]
Fetched 71.8 kB in 1s (98.5 kB/s)
Selecting previously unselected package nload.
(Reading database ... 422219 files and directories currently installed.)
Preparing to unpack .../nload_0.7.4+git20180309.8f92dc0-0.1_amd64.deb ...
Unpacking nload (0.7.4+git20180309.8f92dc0-0.1) ...
Setting up nload (0.7.4+git20180309.8f92dc0-0.1) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for man-db (2.13.1-1) ...
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nload
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ strings /bin/ls | head   
!/lib64/ld-linux-x86-64.so.2
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
fgetfilecon_raw
fgetfilecon
freecon
lgetfilecon
lgetfilecon_raw
_IO_stdin_used
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ sudo apt install speedtest-cli -y
Installing:                     
  speedtest-cli
                                                                                                                 
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1905
  Download size: 23.8 kB
  Space needed: 104 kB / 63.1 GB available

Get:1 http://mirror.pyratelan.org/kali kali-rolling/main amd64 speedtest-cli all 2.1.3-3 [23.8 kB]
Fetched 23.8 kB in 0s (50.5 kB/s)        
Selecting previously unselected package speedtest-cli.
(Reading database ... 422225 files and directories currently installed.)
Preparing to unpack .../speedtest-cli_2.1.3-3_all.deb ...
Unpacking speedtest-cli (2.1.3-3) ...
Setting up speedtest-cli (2.1.3-3) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.4.3) ...
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ speedtest-cli --secure           
Retrieving speedtest.net configuration...
Testing from Telekom Slovenije (86.61.97.37)...
Retrieving speedtest.net server list...
Selecting best server based on ping...
Hosted by COSYS DATA GmbH (Vienna) [278.52 km]: 16.207 ms
Testing download speed................................................................................
Download: 409.84 Mbit/s
Testing upload speed......................................................................................................
Upload: 102.64 Mbit/s
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ speedtest-cli --secure
Retrieving speedtest.net configuration...
Testing from Telekom Slovenije (86.61.97.37)...
Retrieving speedtest.net server list...
Selecting best server based on ping...
Hosted by COSYS DATA GmbH (Vienna) [278.52 km]: 13.87 ms
Testing download speed................................................................................
Download: 511.00 Mbit/s
Testing upload speed.....................................................................................................
.Upload: 97.59 Mbit/s
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ speedtest-cli --secure
Retrieving speedtest.net configuration...
Testing from Telekom Slovenije (86.61.97.37)...
Retrieving speedtest.net server list...
Selecting best server based on ping...
Hosted by Nessus GmbH (10G Uplink) (Vienna) [278.52 km]: 13.813 ms
Testing download speed................................................................................
Download: 434.66 Mbit/s
Testing upload speed......................................................................................................
Upload: 103.86 Mbit/s
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ speedtest-cli         
Retrieving speedtest.net configuration...
Testing from Telekom Slovenije (86.61.97.37)...
Retrieving speedtest.net server list...
Selecting best server based on ping...
Hosted by Wien Energie Superschnell (Vienna) [278.52 km]: 18.7 ms
Testing download speed................................................................................
Download: 434.78 Mbit/s
Testing upload speed......................................................................................................
Upload: 101.40 Mbit/s
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ sudo tcpdump -c 10               
[sudo] password for kali: 
tcpdump: verbose output suppressed, use -v[v]... for full protocol decode
listening on eth0, link-type EN10MB (Ethernet), snapshot length 262144 bytes
^[
^C
0 packets captured
0 packets received by filter
0 packets dropped by kernel
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nmap -o 192.168.1.101
Failed to open normal output file 192.168.1.101 for writing: Permission denied (13)
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nmap -O 192.168.1.101
Starting Nmap 7.95 ( https://nmap.org ) at 2026-04-26 02:54 EDT
Nmap scan report for 192.168.1.101
Host is up (0.00055s latency).
All 1000 scanned ports on 192.168.1.101 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Aggressive OS guesses: AXIS 2100 Network Camera (92%), D-Link DP-300U, DP-G310, or Hamlet HPS01UU print server (92%), HP Tru64 UNIX 5.1A (92%), Sanyo PLC-XU88 digital video projector (92%), TRENDnet TV-IP100 webcam (92%), Vantage HD7100S satellite receiver (92%), Linux 2.6.8 (90%), Asus WL-500gP wireless broadband router (89%), Cisco 1812, 3640, or 3700 router (IOS 12.4) (89%), Cisco DOCSIS cable modem termination server (IOS 12.1) (89%)
No exact OS matches for host (test conditions non-ideal).

OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 6.44 seconds
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nmap -p 1-65535 -T4 192.168.1.1
Starting Nmap 7.95 ( https://nmap.org ) at 2026-04-26 02:56 EDT

                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nmpa -sS -T4 192.168.1.11      
Command 'nmpa' not found, did you mean:
  command 'nmap' from deb nmap
Try: sudo apt install <deb name>
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nmap -sS -T4 192.168.1.11
Starting Nmap 7.95 ( https://nmap.org ) at 2026-04-26 03:06 EDT
Nmap scan report for 192.168.1.11
Host is up (0.00052s latency).
All 1000 scanned ports on 192.168.1.11 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)

Nmap done: 1 IP address (1 host up) scanned in 4.15 seconds
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ searchsploit wordpress ftp
------------------------------------------------------------------------------- ---------------------------------
 Exploit Title                                                                 |  Path
------------------------------------------------------------------------------- ---------------------------------
WordPress Plugin MiwoFTP 1.0.5 - Arbitrary File Download (1)                   | php/webapps/36774.txt
WordPress Plugin MiwoFTP 1.0.5 - Arbitrary File Download (2)                   | php/webapps/36801.txt
WordPress Plugin MiwoFTP 1.0.5 - Cross-Site Request Forgery / Arbitrary File C | php/webapps/36763.txt
WordPress Plugin MiwoFTP 1.0.5 - Cross-Site Request Forgery / Arbitrary File D | php/webapps/36761.txt
WordPress Plugin MiwoFTP 1.0.5 - Multiple Cross-Site Request Forgery / Cross-S | php/webapps/36762.txt
------------------------------------------------------------------------------- ---------------------------------
Shellcodes: No Results
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ dnsenum www.arnes.si
dnsenum VERSION:1.3.1

-----   www.arnes.si   -----                                                                                     
                                                                                                                 
                                                                                                                 
Host's addresses:                                                                                                
__________________                                                                                               
                                                                                                                 
splet.arnes.si.                          3600     IN    A        193.2.1.67                                      

                                                                                                                 
Name Servers:                                                                                                    
______________                                                                                                   
                                                                                                                 
 Error: can't continue no NS record for www.arnes.si                                                             
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ dnenum google.com   
Command 'dnenum' not found, did you mean:
  command 'dnsenum' from deb dnsenum
Try: sudo apt install <deb name>
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ dnsenum google.com  
dnsenum VERSION:1.3.1

-----   google.com   -----                                                                                       
                                                                                                                 
                                                                                                                 
Host's addresses:                                                                                                
__________________                                                                                               
                                                                                                                 
google.com.                              40       IN    A        172.217.168.142                                 

                                                                                                                 
Name Servers:                                                                                                    
______________                                                                                                   
                                                                                                                 
ns4.google.com.                          1207     IN    A        216.239.38.10                                   
ns1.google.com.                          6967     IN    A        216.239.32.10
ns2.google.com.                          3930     IN    A        216.239.34.10
ns3.google.com.                          5625     IN    A        216.239.36.10

                                                                                                                 
Mail (MX) Servers:                                                                                               
___________________                                                                                              
                                                                                                                 
smtp.google.com.                         89       IN    A        142.251.127.27                                  
smtp.google.com.                         89       IN    A        142.251.127.26

                                                                                                                 
Trying Zone Transfers and getting Bind Versions:                                                                 
_________________________________________________                                                                
                                                                                                                 
                                                                                                                 
Trying Zone Transfer for google.com on ns3.google.com ... 
AXFR record query failed: corrupt packet

Trying Zone Transfer for google.com on ns2.google.com ... 
AXFR record query failed: corrupt packet

Trying Zone Transfer for google.com on ns4.google.com ... 
AXFR record query failed: corrupt packet

Trying Zone Transfer for google.com on ns1.google.com ... 
AXFR record query failed: corrupt packet

                                                                                                                 
Brute forcing with /usr/share/dnsenum/dns.txt:                                                                   
_______________________________________________                                                                  
                                                                                                                 
about.google.com.                        300      IN    CNAME    www3.l.google.com.                              
www3.l.google.com.                       223      IN    A        192.178.24.174
accounts.google.com.                     239      IN    A        142.251.127.84
admin.google.com.                        57       IN    A        172.217.23.78
ads.google.com.                          177      IN    A        172.217.168.142
america.google.com.                      300      IN    CNAME    www3.l.google.com.
www3.l.google.com.                       298      IN    A        172.217.23.174
ap.google.com.                           300      IN    CNAME    www2.l.google.com.
www2.l.google.com.                       300      IN    A        172.217.168.132
apps.google.com.                         300      IN    CNAME    www3.l.google.com.
www3.l.google.com.                       110      IN    A        172.217.23.78
archive.google.com.                      300      IN    A        172.217.23.174
asia.google.com.                         300      IN    A        142.250.181.164
blog.google.com.                         300      IN    CNAME    www.blogger.com.
www.blogger.com.                         271      IN    CNAME    blogger.l.google.com.
blogger.l.google.com.                    300      IN    A        172.217.168.137
channel.google.com.                      300      IN    A        142.251.209.46
d.google.com.                            300      IN    CNAME    www3.l.google.com.
www3.l.google.com.                       198      IN    A        192.178.24.174
directory.google.com.                    300      IN    CNAME    www3.l.google.com.
www3.l.google.com.                       63       IN    A        172.217.18.174
dns.google.com.                          712      IN    A           8.8.8.8
dns.google.com.                          712      IN    A           8.8.4.4
elections.google.com.                    300      IN    A        142.251.208.110
environment.google.com.                  300      IN    A        172.217.23.78
europe.google.com.                       300      IN    A        172.217.168.132
finance.google.com.                      300      IN    CNAME    www3.l.google.com.
www3.l.google.com.                       262      IN    A        172.217.23.174
health.google.com.                       300      IN    A        172.217.168.142
^C
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ lbd google.com

lbd - load balancing detector 0.4 - Checks if a given domain uses load-balancing.
                                    Written by Stefan Behte (http://ge.mine.nu)
                                    Proof-of-concept! Might give false positives.

Checking for DNS-Loadbalancing: NOT FOUND
Checking for HTTP-Loadbalancing [Server]: 
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
/usr/bin/lbd: line 81: .nlog: Permission denied
grep: .nlog: No such file or directory

/usr/bin/lbd: line 90: .log: Permission denied
sort: cannot read: .log: No such file or directory
 NOT FOUND

rm: cannot remove '.nlog': No such file or directory
rm: cannot remove '.log': No such file or directory
Checking for HTTP-Loadbalancing [Date]: 07:10:43, 07:10:44, 07:10:44, 07:10:44, 07:10:44, 07:10:44, 07:10:44, 07:10:45, 07:10:45, 07:10:45, 07:10:45, 07:10:45, 07:10:46, 07:10:46, 07:10:46, 07:10:46, 07:10:46, 07:10:47, 07:10:47, 07:10:47, 07:10:47, 07:10:47, 07:10:48, 07:10:48, 07:10:48, 07:10:48, 07:10:48, 07:10:49, 07:10:49, 07:10:49, 07:10:49, 07:10:49, 07:10:50, 07:10:50, 07:10:50, 07:10:50, 07:10:50, 07:10:50, 07:10:51, 07:10:51, 07:10:51, 07:10:51, 07:10:51, 07:10:52, 07:10:52, 07:10:52, 07:10:52, 07:10:53, 07:10:53, 07:10:53, NOT FOUND

Checking for HTTP-Loadbalancing [Diff]: /usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
^Ccp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
/usr/bin/lbd: line 154: .nlog: Permission denied
cp: cannot stat '.nlog': No such file or directory
NOT FOUND
rm: cannot remove '.nlog': No such file or directory
rm: cannot remove '.log': No such file or directory

google.com does NOT use Load-balancing.

                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nth                      
Command 'nth' not found, but can be installed with:
sudo apt install name-that-hash
Do you want to install it? (N/y)y
sudo apt install name-that-hash
[sudo] password for kali: 
Installing:                     
  name-that-hash
                                                                                                                 
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1905
  Download size: 17.6 kB
  Space needed: 126 kB / 63.1 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 name-that-hash all 1.11.0-0kali1 [17.6 kB]
Fetched 17.6 kB in 1s (25.7 kB/s)   
Selecting previously unselected package name-that-hash.
(Reading database ... 422240 files and directories currently installed.)
Preparing to unpack .../name-that-hash_1.11.0-0kali1_all.deb ...
Unpacking name-that-hash (1.11.0-0kali1) ...
Setting up name-that-hash (1.11.0-0kali1) ...
Processing triggers for kali-menu (2025.4.3) ...
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ nth -t ef487f75307f96954d3bb132e5f4b035  

  _   _                           _____ _           _          _   _           _     
 | \ | |                         |_   _| |         | |        | | | |         | |    
 |  \| | __ _ _ __ ___   ___ ______| | | |__   __ _| |_ ______| |_| | __ _ ___| |__  
 | . ` |/ _` | '_ ` _ \ / _ \______| | | '_ \ / _` | __|______|  _  |/ _` / __| '_ \ 
 | |\  | (_| | | | | | |  __/      | | | | | | (_| | |_       | | | | (_| \__ \ | | |
 \_| \_/\__,_|_| |_| |_|\___|      \_/ |_| |_|\__,_|\__|      \_| |_/\__,_|___/_| |_|

https://twitter.com/bee_sec_san
https://github.com/HashPals/Name-That-Hash 
    

ef487f75307f96954d3bb132e5f4b035

Most Likely 
MD5, HC: 0 JtR: raw-md5 Summary: Used for Linux Shadow files.
MD4, HC: 900 JtR: raw-md4
NTLM, HC: 1000 JtR: nt Summary: Often used in Windows Active Directory.
Domain Cached Credentials, HC: 1100 JtR: mscach

Least Likely
Domain Cached Credentials 2, HC: 2100 JtR: mscach2 Double MD5, HC: 2600  Tiger-128,  Skein-256(128),  
Skein-512(128),  Lotus Notes/Domino 5, HC: 8600 JtR: lotus5 md5(md5(md5($pass))), HC: 3500 Summary: Hashcat mode 
is only supported in hashcat-legacy. md5(uppercase(md5($pass))), HC: 4300  md5(sha1($pass)), HC: 4400  
md5(utf16($pass)), JtR: dynamic_29 md4(utf16($pass)), JtR: dynamic_33 md5(md4($pass)), JtR: dynamic_34 Haval-128,
JtR: haval-128-4 RIPEMD-128, JtR: ripemd-128 MD2, JtR: md2 Snefru-128, JtR: snefru-128 DNSSEC(NSEC3), HC: 8300  
RAdmin v2.x, HC: 9900 JtR: radmin Cisco Type 7,  BigCrypt, JtR: bigcrypt 
                                                                                                                 
┌──(kali㉿kali)-[/]
└─$ 


Kali Linux is a linux distribution for learning, studying and analyzing world of cybersecurity technologies, software and vulnerabilities.
SPecifically its intended for the cyber security space. Most desktop distros (like Ubuntu or Fedora) have "safety rails" to prevent you from 
accidentally deleting system files or executing malicious scripts. 
Kali assumes you want total control, making it much easier to accidentally break your OS.

Kali comes pre-loaded with hundreds of specialized tools which are its strengths. 
For daily use, you likely don't need a forensic imaging tool or a wireless packet injector running in the background. These are all bloatware for normal users. 
They impact performance by consuming system resources and clutter your application menu, making it harder to find standard apps like a browser or document editor.