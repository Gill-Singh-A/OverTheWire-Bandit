# Level 6
The password for the next level is stored in a file somewhere on the server and has all of the following properties:
* owned by user bandit7
* owned by group bandit6
* 33 bytes in size
<!-- -->

## Theory
When we run the 'ls -l' command, the shell does a long listing of the current working directory and the output looks something like this:
```bash
kaptaan@PEACOCK:~/CTF/Google/Level 4$ ls -l
total 68
-rwxrwxr-x 1 kaptaan kaptaan 14328 Apr 12 01:44 chal
-rw-r--r-- 1 kaptaan kaptaan  2962 Apr 12 01:44 chal.c
drwxrwxr-x 2 kaptaan kaptaan  4096 Apr 12 01:45 CTF
-rw-rw-r-- 1 kaptaan kaptaan 21588 Apr  9 23:42 eafc850054672b6e5242ffb8b2f3110760a20cabcca90a69c00c4f4c91912c2e43c5ea8e68ad529692da3aac7763f6301888b843c7ee5e94699e22c8ea94db5c
-rw-r--r-- 1 kaptaan kaptaan 18432 Dec 31  1979 pico.uf2
```
Each line on the list tells us something about a file or directory<br />
After the first string of 10 characters and an integer, we get two names followed by the size of the file/directory in bytes.<br />
* First Name  : Name of the owner of that file/directory
* Second Name : Name of the Group of that owner of that file/directory

## Solution
HOST = bandit.labs.overthewire.org<br />
PORT = 2220<br />
USERNAME = bandit6<br />
PASSWORD = 'P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        '<br />
SERVICE = ssh<br /><br />

To log on the server using ssh, we simply have to type the command:
```bash
ssh user@host -p port
```
So after substituting the values, we get the following command:
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```
After this we will be greeted with the following text:
```bash
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit6@bandit.labs.overthewire.org's password:
```
Here we have to give the password which is given above.<br />
After entering the password, we get the following text and access to the server's shell.
```bash
      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

 Both python2 and python3 are installed.

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit6@bandit:~$
```
Let's change our directory to the root directory of the server with 'cd' command:
```bash
bandit6@bandit:~$ cd /
```
Let's look for a file with 33 bytes in size and 'bandit7' name with the 'du' command:
```bash
bandit6@bandit:/$ du -a -b | grep 33 | grep bandit7
du: cannot read directory './sys/kernel/tracing': Permission denied
du: cannot read directory './sys/kernel/debug': Permission denied
du: cannot read directory './sys/fs/pstore': Permission denied
du: cannot read directory './sys/fs/bpf': Permission denied
du: cannot read directory './lost+found': Permission denied
du: cannot read directory './boot/efi': Permission denied
du: cannot read directory './drifter/drifter14_src/axTLS': Permission denied
du: cannot read directory './proc/tty/driver': Permission denied
du: cannot access './proc/1418218/task/1418218/fd/4': No such file or directory
du: cannot access './proc/1418218/task/1418218/fdinfo/4': No such file or directory
du: cannot access './proc/1418218/fd/3': No such file or directory
du: cannot access './proc/1418218/fdinfo/3': No such file or directory
du: cannot read directory './run/chrony': Permission denied
du: cannot read directory './run/user/11022': Permission denied
du: cannot read directory './run/user/11004': Permission denied
du: cannot read directory './run/user/11006/systemd/inaccessible/dir': Permission denied
du: cannot read directory './run/user/8006': Permission denied
du: cannot read directory './run/user/11015': Permission denied
du: cannot read directory './run/user/11003': Permission denied
du: cannot read directory './run/user/11002': Permission denied
du: cannot read directory './run/user/11011': Permission denied
du: cannot read directory './run/user/11014': Permission denied
du: cannot read directory './run/user/11018': Permission denied
du: cannot read directory './run/user/11007': Permission denied
du: cannot read directory './run/user/11013': Permission denied
du: cannot read directory './run/user/11016': Permission denied
du: cannot read directory './run/user/11001': Permission denied
du: cannot read directory './run/user/11026': Permission denied
du: cannot read directory './run/user/11000': Permission denied
du: cannot read directory './run/user/11023': Permission denied
du: cannot read directory './run/user/11025': Permission denied
du: cannot read directory './run/user/11005': Permission denied
du: cannot read directory './run/user/11027': Permission denied
du: cannot read directory './run/user/11012': Permission denied
du: cannot read directory './run/user/11020': Permission denied
du: cannot read directory './run/user/11024': Permission denied
du: cannot read directory './run/user/11009': Permission denied
du: cannot read directory './run/sudo': Permission denied
du: cannot read directory './run/screen/S-bandit0': Permission denied
du: cannot read directory './run/screen/S-bandit25': Permission denied
du: cannot read directory './run/screen/S-bandit4': Permission denied
du: cannot read directory './run/screen/S-bandit9': Permission denied
du: cannot read directory './run/screen/S-bandit20': Permission denied
du: cannot read directory './run/multipath': Permission denied
du: cannot read directory './run/cryptsetup': Permission denied
du: cannot read directory './run/lvm': Permission denied
du: cannot read directory './run/credentials/systemd-sysusers.service': Permission denied
du: cannot read directory './run/systemd/propagate': Permission denied
du: cannot read directory './run/systemd/unit-root': Permission denied
du: cannot read directory './run/systemd/inaccessible/dir': Permission denied
du: cannot read directory './run/lock/lvm': Permission denied
du: cannot read directory './snap/core18/2679/etc/ssl/private': Permission denied
du: cannot read directory './snap/core18/2679/root': Permission denied
du: cannot read directory './snap/core18/2679/var/cache/ldconfig': Permission denied
du: cannot read directory './snap/core18/2679/var/lib/private': Permission denied
du: cannot read directory './snap/core20/1822/etc/ssl/private': Permission denied
du: cannot read directory './snap/core20/1822/root': Permission denied
du: cannot read directory './snap/core20/1822/var/cache/ldconfig': Permission denied
du: cannot read directory './snap/core20/1822/var/cache/private': Permission denied
du: cannot read directory './snap/core20/1822/var/lib/private': Permission denied
du: cannot read directory './snap/core20/1822/var/lib/snapd/void': Permission denied
du: cannot read directory './tmp': Permission denied
du: cannot read directory './dev/mqueue': Permission denied
du: cannot read directory './dev/shm': Permission denied
du: cannot read directory './etc/polkit-1/localauthority': Permission denied
du: cannot read directory './etc/multipath': Permission denied
du: cannot read directory './etc/sudoers.d': Permission denied
du: cannot read directory './etc/ssl/private': Permission denied
33	./etc/bandit_pass/bandit7
du: cannot read directory './root': Permission denied
du: cannot read directory './home/drifter6/data': Permission denied
du: cannot read directory './home/drifter8/chroot': Permission denied
du: cannot read directory './home/bandit27-git': Permission denied
du: cannot read directory './home/bandit31-git': Permission denied
du: cannot read directory './home/ubuntu': Permission denied
du: cannot read directory './home/bandit29-git': Permission denied
du: cannot read directory './home/bandit28-git': Permission denied
du: cannot read directory './home/bandit5/inhere': Permission denied
du: cannot read directory './home/bandit30-git': Permission denied
du: cannot read directory './var/cache/apt/archives/partial': Permission denied
du: cannot read directory './var/cache/private': Permission denied
du: cannot read directory './var/cache/pollinate': Permission denied
du: cannot read directory './var/cache/apparmor/e10c1cf9.0': Permission denied
du: cannot read directory './var/cache/apparmor/c47eabf7.0': Permission denied
du: cannot read directory './var/cache/ldconfig': Permission denied
du: cannot read directory './var/crash': Permission denied
du: cannot read directory './var/log': Permission denied
du: cannot read directory './var/snap/lxd/common/lxd': Permission denied
du: cannot read directory './var/tmp': Permission denied
du: cannot read directory './var/spool/cron/crontabs': Permission denied
du: cannot read directory './var/spool/rsyslog': Permission denied
du: cannot read directory './var/spool/bandit24': Permission denied
du: cannot read directory './var/lib/apt/lists/partial': Permission denied
du: cannot read directory './var/lib/polkit-1': Permission denied
du: cannot read directory './var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial': Permission denied
du: cannot read directory './var/lib/private': Permission denied
du: cannot read directory './var/lib/chrony': Permission denied
du: cannot read directory './var/lib/amazon': Permission denied
33	./var/lib/dpkg/info/bandit7.password
du: cannot read directory './var/lib/snapd/void': Permission denied
du: cannot read directory './var/lib/snapd/cookie': Permission denied
du: cannot read directory './var/lib/update-notifier/package-data-downloads/partial': Permission denied
```
Here, on the 4th last line we can see a file with name 'bandit7.password' and 33 bytes in size in the directory '/var/lib/dpkg/info/'.<br />
Let's change our directory to '/var/lib/dpkg/info/' with the 'cd' command:
```bash
bandit6@bandit:/$ cd /var/lib/dpkg/info/
```
And now let's check the owner and group of owner of the file 'bandit7.password' with the 'ls -l' command and filtering the output with the 'grep' command:
```bash
bandit6@bandit:/var/lib/dpkg/info$ ls -l | grep bandit7.password
-rw-r----- 1 bandit7 bandit6      33 Feb 21 22:03 bandit7.password
```
Here, we can see that the owner of the file 'bandit7.password' is 'bandit7' and the group of the owner is 'bandit6'.<br />
Therefore, the file 'bandit7.password' have all the required conditions:
* owned by user bandit7
* owned by group bandit6
* 33 bytes in size
<!-- -->
So, let's open the file with the 'cat' command:
```bash
bandit6@bandit:/var/lib/dpkg/info$ cat bandit7.password 
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
Here, we got the password for Level 7 of Bandit.<br />
So, our purpose is complete. Let's logout from the server using the 'exit' command
```bash
bandit6@bandit:/var/lib/dpkg/info$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
<br />
Password for Level 7 = z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
