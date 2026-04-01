uname -a
Linux codespaces-65b900 6.8.0-1044-azure #50~22.04.1-Ubuntu SMP Wed Dec  3 15:13:22 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux

pwd
/workspaces/codespaces-blank

ls

cd..
bash: cd..: command not found

cd ..

ls
bin                boot  etc  home  lib.usr-is-merged  lib64  mnt  proc  run   sbin.usr-is-merged  sys  usr  vscode
bin.usr-is-merged  dev   go   lib   lib32              media  opt  root  sbin  srv                 tmp  var  workspaces

ls -l
total 92
lrwxrwxrwx    1 root      root      7 Apr 22  2024 bin -> usr/bin
drwxr-xr-x    2 root      root   4096 Jul 10  2025 bin.usr-is-merged
drwxr-xr-x    2 root      root   4096 Apr 22  2024 boot
drwxr-xr-x   14 root      root   3980 Apr  1 15:02 dev
drwxr-xr-x    1 root      root   4096 Apr  1 15:02 etc
drwxrwsr-x    3 codespace golang 4096 Nov 27 10:44 go
drwxr-xr-x    1 root      root   4096 Apr  1 15:02 home
lrwxrwxrwx    1 root      root      7 Apr 22  2024 lib -> usr/lib
drwxr-xr-x    2 root      root   4096 Nov 14  2024 lib.usr-is-merged
lrwxrwxrwx    1 root      root      9 Nov 27 10:32 lib32 -> usr/lib32
lrwxrwxrwx    1 root      root      9 Apr 22  2024 lib64 -> usr/lib64
drwxr-xr-x    2 root      root   4096 Oct 13 14:02 media
drwxr-xr-x    2 root      root   4096 Oct 13 14:02 mnt
drwxrwsr-x    1 codespace oryx   4096 Apr  1 15:02 opt
dr-xr-xr-x  257 root      root      0 Apr  1 15:02 proc
drwx------    1 root      root   4096 Nov 27 10:46 root
drwxr-xr-x    1 root      root   4096 Apr  1 15:03 run
lrwxrwxrwx    1 root      root      8 Apr 22  2024 sbin -> usr/sbin
drwxr-xr-x    2 root      root   4096 Jul 10  2025 sbin.usr-is-merged
drwxr-xr-x    2 root      root   4096 Oct 13 14:02 srv
dr-xr-xr-x   12 root      root      0 Apr  1 15:00 sys
drwxr-xrwt+   4 root      root   4096 Apr  1 15:03 tmp
drwxr-xr-x    1 root      root   4096 Nov 27 10:32 usr
drwxr-xr-x    1 root      root   4096 Apr  1 15:02 var
drwxr-xr-x    5 root      root   4096 Apr  1 15:01 vscode
drwxr-xrwx+   5 codespace root   4096 Apr  1 15:02 workspaces

ls / > fis.txt
bash: fis.txt: Permission denied

mkdir example
mkdir: cannot create directory ‘example’: Permission denied

sudo ls / > fis.txt
bash: fis.txt: Permission denied

cd home

ls / > fis.txt
bash: fis.txt: Permission denied

sudo ls / > fis.txt
bash: fis.txt: Permission denied

mkdir newfolder
mkdir: cannot create directory ‘newfolder’: Permission denied

sudo mkdir newFolder

cd newFolder/

touch file.txt
touch: cannot touch 'file.txt': Permission denied

sudo touch file.txt

nano file.txt

sudo nano file.txt

cat file.txt
hello this is my edit of this file.txt. bye bye

rm file.txt
rm: remove write-protected regular file 'file.txt'? y
rm: cannot remove 'file.txt': Permission denied

sudo rm file.txt

sudo rm-r newFolder
sudo: rm-r: command not found

sudo rm -r newFolder
rm: cannot remove 'newFolder': No such file or directory

cd ..

sudo rm -r newFolder

ls
codespace  vscode

mkdir newFolder
mkdir: cannot create directory ‘newFolder’: Permission denied

sudo mkdir newFolder

touch decription.txt
touch: cannot touch 'decription.txt': Permission denied

sudo touch decription.txt

sudo nano description.txt

mkdir test
mkdir: cannot create directory ‘test’: Permission denied

sudo mkdir test

sudo mv description.txt /home/test/

sudo cp my_profile.txt my_profile1.txt

sudo mv  my_profile.txt /home/

cd ..

ls -lh
total 24K
drwxr-x--- 1 codespace codespace 4.0K Apr  1 15:02 codespace
-rw-r--r-- 1 root      root         0 Apr  1 15:26 decription.txt
-rw-r--r-- 1 root      root        14 Apr  1 15:27 my_profile.txt
drwxr-xr-x 2 root      root      4.0K Apr  1 15:26 newFolder
drwxr-xr-x 2 root      root      4.0K Apr  1 15:31 test
drwxr-xr-x 3 root      root      4.0K Apr  1 15:02 vscode

sudo chmod 444 my_profile.txt

ls -lh
total 24K
drwxr-x--- 1 codespace codespace 4.0K Apr  1 15:02 codespace
-rw-r--r-- 1 root      root         0 Apr  1 15:26 decription.txt
-r--r--r-- 1 root      root        14 Apr  1 15:27 my_profile.txt
drwxr-xr-x 2 root      root      4.0K Apr  1 15:26 newFolder
drwxr-xr-x 2 root      root      4.0K Apr  1 15:31 test
drwxr-xr-x 3 root      root      4.0K Apr  1 15:02 vscode

whoami
codespace

uname -a
Linux codespaces-65b900 6.8.0-1044-azure #50~22.04.1-Ubuntu SMP Wed Dec  3 15:13:22 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux

df -a
Filesystem     1K-blocks     Used Available Use% Mounted on
overlay         32847680  9866328  21287256  32% /
proc                   0        0         0    - /proc
tmpfs              65536        0     65536   0% /dev
devpts                 0        0         0    - /dev/pts
sysfs                  0        0         0    - /sys
cgroup                 0        0         0    - /sys/fs/cgroup
mqueue                 0        0         0    - /dev/mqueue
shm                65536        0     65536   0% /dev/shm
/dev/root       30298176 17174384  13107408  57% /usr/sbin/docker-init
/dev/sdc1       46127956  3325620  40426760   8% /tmp
/dev/root       30298176 17174384  13107408  57% /vscode
/dev/loop4      32847680  9866328  21287256  32% /workspaces
/dev/root       30298176 17174384  13107408  57% /.codespaces/bin
/dev/loop4      32847680  9866328  21287256  32% /etc/resolv.conf
/dev/loop4      32847680  9866328  21287256  32% /etc/hostname
/dev/loop4      32847680  9866328  21287256  32% /etc/hosts
/dev/loop4      32847680  9866328  21287256  32% /var/lib/docker
/dev/loop4      32847680  9866328  21287256  32% /home/vscode/.minikube
/dev/root       30298176 17174384  13107408  57% /workspaces/.codespaces/shared
/dev/loop4      32847680  9866328  21287256  32% /workspaces/.codespaces/.persistedshare
none                   0        0         0    - /sys/kernel/security

top
top - 15:36:16 up 35 min,  0 user,  load average: 0.27, 0.35, 0.57
Tasks:  18 total,   1 running,  17 sleeping,   0 stopped,   0 zombie
%Cpu(s):  5.0 us,  3.5 sy,  0.0 ni, 91.3 id,  0.0 wa,  0.0 hi,  0.2 si,  0.0 st 
MiB Mem :   7943.6 total,    187.8 free,   1804.3 used,   6330.8 buff/cache     
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   6139.3 avail Mem 

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                      
   1780 codespa+  20   0   42.1g 336992  57088 S   1.3   4.1   0:26.63 node                         
   1753 codespa+  20   0   11.3g 130400  52736 S   1.0   1.6   0:07.62 node                         
   2228 codespa+  20   0 1144608  75488  48128 S   0.3   0.9   0:04.27 node                         
      1 codespa+  20   0    1136    512    512 S   0.0   0.0   0:00.07 docker-init                  
      7 codespa+  20   0    2800   1536   1536 S   0.0   0.0   0:00.44 sh                           
    324 root      20   0   12016   2964   1920 S   0.0   0.0   0:00.00 sshd                         
    357 root      20   0 1895732  81092  57728 S   0.0   1.0   0:00.77 dockerd                      


du -ah ~ | sort -rh | head -n 5
283M    /home/codespace
228M    /home/codespace/.local
208M    /home/codespace/.local/lib/python3.12/site-packages
208M    /home/codespace/.local/lib/python3.12
208M    /home/codespace/.local/lib

