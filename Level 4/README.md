# Level 4
The password for the next level is stored in the only human-readable file in the 'inhere' directory.<br /><br />

HOST = bandit.labs.overthewire.org<br />
PORT = 2220<br />
USERNAME = bandit4<br />
PASSWORD = 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe<br />
SERVICE = ssh<br /><br />

To log on the server using ssh, we simply have to type the command:
```bash
ssh user@host -p port
```
So after substituting the values, we get the following command:
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
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

bandit4@bandit.labs.overthewire.org's password:
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

bandit4@bandit:~$
```
Lets check the current working directory with 'pwd' command:
```bash
bandit4@bandit:~$ pwd
/home/bandit4
```
Here, we see that we're in the home directory of the bandit4 user, in which the 'inhere' directory is stored.<br />
Here, lets type 'ls -l' command to check out the files and directories in the current directory.
```bash
bandit4@bandit:~$ ls -l
total 4
drwxr-xr-x 2 root root 4096 Feb 21 22:03 inhere
```
Let's change our directory to the 'inhere' directory with 'cd' command:
```bash
bandit4@bandit:~$ cd inhere/
```
Here, lets type 'ls -l' command to check out the files and directories in the current directory.
```bash
bandit4@bandit:~/inhere$ ls -l
total 40
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file00
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file01
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file02
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file03
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file04
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file05
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file06
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file07
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file08
-rw-r----- 1 bandit5 bandit4 33 Feb 21 22:03 -file09
```
Here we see that a total of 10 files are present with the name '-file0x', where x is in the range [0, 9]<br />
So let's open all those files with the cat command in the given format:
```bash
bandit4@bandit:~/inhere$ cat ./-file0x
```
We got the following output for the cat commands
```bash
bandit4@bandit:~/inhere$ cat ./-file00
=�M�Ð�EW�f
bandit4@bandit:~/inhere$ cat ./-file01
��.Y>*���{K����H��G��[�o�Q�G�*�
bandit4@bandit:~/inhere$ cat ./-file02
Y���~���d]��+S,�I�t^���\�9
bandit4@bandit:~/inhere$ cat ./-file03
�Q]#�1���_�&5B���d�0^�]�D$�H�
bandit4@bandit:~/inhere$ cat ./-file04
V���f���STA�܅�b�����U�k
bandit4@bandit:~/inhere$ cat ./-file05
5�?:�o�ҫ\ԑ2s��=n̩-�`C9��`V�_�
bandit4@bandit:~/inhere$ cat ./-file06
ЪF�`V��E+�sa��F�a\6n�0t��N+f
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$ cat ./-file08
d��
_8�o����W��[1m��)$�����R�
bandit4@bandit:~/inhere$ cat ./-file09
�"�_��)��!��Dg�H�H}�Xb���J
�
```
Here, we notice that only '-file07' is human-readable.<br />
So, we got the password for the Level 5 of Bandit.<br />
So, our purpose is complete. Let's logout from the server using the 'exit' command
```bash
bandit4@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
<br />
Password for Level 5 = lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
