# Level 5
The password for the next level is stored in a file somewhere under the 'inhere' directory and has all of the following properties:
* human-readable
* 1033 bytes in size
* not executable

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
The first string, which is 10 characters long tells us that either that item is a file or directory and about the permissions related to that item.<br />
The first character of that string is either '-' or 'd'
* '-' : File
* 'd' : Directory
<!-- -->
The next 3 characters tells us about the permissions that the user have on that file.<br />
The next 3 characters tells us about the permissions that the group of that user have on that file.<br />
The next 3 characters tells us about the permissions that all the other users have on that file.<br />
Permissions (same order as that of given by 'ls -l' command):
* 'r' : read
* 'w' : write
* 'x' : execute
<!-- -->
If any one of the character is replaced by '-', then that specific user/group doesn't have that permission.


## Solution
HOST = bandit.labs.overthewire.org<br />
PORT = 2220<br />
USERNAME = bandit5<br />
PASSWORD = lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR<br />
SERVICE = ssh<br /><br />

To log on the server using ssh, we simply have to type the command:
```bash
ssh user@host -p port
```
So after substituting the values, we get the following command:
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
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

bandit5@bandit.labs.overthewire.org's password:
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

bandit5@bandit:~$
```
Lets check the current working directory with 'pwd' command:
```bash
bandit5@bandit:~$ pwd
/home/bandit5
```
Here, we see that we're in the home directory of the bandit5 user, in which the 'inhere' directory is stored.<br />
Here, lets type 'ls -l' command to check out the files and directories in the current directory.
```bash
bandit5@bandit:~$ ls -l
total 4
drwxr-x--- 22 root bandit5 4096 Feb 21 22:03 inhere
```
Let's change our directory to the 'inhere' directory with 'cd' command:
```bash
bandit5@bandit:~$ cd inhere/
```
Here, lets type 'ls -l' command to check out the files and directories in the current directory.
```bash
bandit5@bandit:~/inhere$ ls -l
total 80
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere00
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere01
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere02
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere03
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere04
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere05
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere06
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere07
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere08
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere09
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere10
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere11
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere12
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere13
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere14
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere15
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere16
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere17
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere18
drwxr-x--- 2 root bandit5 4096 Feb 21 22:03 maybehere19
```
Here, we see that there are 20 folders with name 'maybehereyx' where y is in the range [0, 1] and x is in the range [0, 9]<br />
So, changing directory to every file using 'cd' command and doing long listing using 'ls -l' command to get the size is too much work.<br />
So here we are going to use 'du' command to get the size of the files in all the directories and 'grep' command to filter out the required file.<br />
The 'du' command that we will run will be:
```bash
du -a -b
```
Where '-a' and '-b' are the arguments that means:
* '-a' : Run the command on all the files and folders present in the current directory and subdirectories
* '-b' : Display the size of files and folders in bytes
<!-- -->
After running this command, we get an output like this:
```bash
bandit5@bandit:~/inhere$ du -a -b
315	./maybehere03/-file1
2190	./maybehere03/spaces file1
6595	./maybehere03/-file2
3385	./maybehere03/spaces file2
2282	./maybehere03/.file3
8880	./maybehere03/.file2
8275	./maybehere03/-file3
9234	./maybehere03/spaces file3
9769	./maybehere03/.file1
55021	./maybehere03
6028	./maybehere01/-file1
4139	./maybehere01/spaces file1
288	./maybehere01/-file2
4543	./maybehere01/spaces file2
3792	./maybehere01/.file3
3070	./maybehere01/.file2
9641	./maybehere01/-file3
8834	./maybehere01/spaces file3
8944	./maybehere01/.file1
53375	./maybehere01
1052	./maybehere10/-file1
8269	./maybehere10/spaces file1
1991	./maybehere10/-file2
3570	./maybehere10/spaces file2
2961	./maybehere10/.file3
99	./maybehere10/.file2
1237	./maybehere10/-file3
2155	./maybehere10/spaces file3
7092	./maybehere10/.file1
32522	./maybehere10
9678	./maybehere12/-file1
2157	./maybehere12/spaces file1
251	./maybehere12/-file2
2460	./maybehere12/spaces file2
1022	./maybehere12/.file3
8244	./maybehere12/.file2
9076	./maybehere12/-file3
1639	./maybehere12/spaces file3
5815	./maybehere12/.file1
44438	./maybehere12
8794	./maybehere15/-file1
1623	./maybehere15/spaces file1
9499	./maybehere15/-file2
51	./maybehere15/spaces file2
742	./maybehere15/.file3
279	./maybehere15/.file2
6299	./maybehere15/-file3
1637	./maybehere15/spaces file3
2159	./maybehere15/.file1
35179	./maybehere15
5731	./maybehere06/-file1
4073	./maybehere06/spaces file1
1076	./maybehere06/-file2
4251	./maybehere06/spaces file2
2418	./maybehere06/.file3
8976	./maybehere06/.file2
3443	./maybehere06/-file3
8065	./maybehere06/spaces file3
1271	./maybehere06/.file1
43400	./maybehere06
1077	./maybehere08/-file1
215	./maybehere08/spaces file1
3825	./maybehere08/-file2
3693	./maybehere08/spaces file2
2217	./maybehere08/.file3
747	./maybehere08/.file2
2650	./maybehere08/-file3
9138	./maybehere08/spaces file3
8169	./maybehere08/.file1
35827	./maybehere08
3628	./maybehere09/-file1
5301	./maybehere09/spaces file1
774	./maybehere09/-file2
8716	./maybehere09/spaces file2
3798	./maybehere09/.file3
8517	./maybehere09/.file2
7961	./maybehere09/-file3
7569	./maybehere09/spaces file3
6763	./maybehere09/.file1
57123	./maybehere09
3801	./maybehere02/-file1
6746	./maybehere02/spaces file1
3511	./maybehere02/-file2
8488	./maybehere02/spaces file2
7953	./maybehere02/.file3
2577	./maybehere02/.file2
4932	./maybehere02/-file3
2275	./maybehere02/spaces file3
6351	./maybehere02/.file1
50730	./maybehere02
4277	./maybehere16/-file1
9773	./maybehere16/spaces file1
5301	./maybehere16/-file2
3146	./maybehere16/spaces file2
1148	./maybehere16/.file3
8472	./maybehere16/.file2
8085	./maybehere16/-file3
7509	./maybehere16/spaces file3
5426	./maybehere16/.file1
57233	./maybehere16
6302	./maybehere19/-file1
7186	./maybehere19/spaces file1
5594	./maybehere19/-file2
8785	./maybehere19/spaces file2
494	./maybehere19/.file3
4740	./maybehere19/.file2
7965	./maybehere19/-file3
2307	./maybehere19/spaces file3
7209	./maybehere19/.file1
54678	./maybehere19
4410	./maybehere04/-file1
5532	./maybehere04/spaces file1
2619	./maybehere04/-file2
2491	./maybehere04/spaces file2
142	./maybehere04/.file3
6144	./maybehere04/.file2
2117	./maybehere04/-file3
6002	./maybehere04/spaces file3
2440	./maybehere04/.file1
35993	./maybehere04
2346	./maybehere05/-file1
880	./maybehere05/spaces file1
5959	./maybehere05/-file2
2420	./maybehere05/spaces file2
4585	./maybehere05/.file3
5917	./maybehere05/.file2
2572	./maybehere05/-file3
8585	./maybehere05/spaces file3
3201	./maybehere05/.file1
40561	./maybehere05
3663	./maybehere07/-file1
4130	./maybehere07/spaces file1
2488	./maybehere07/-file2
9064	./maybehere07/spaces file2
1997	./maybehere07/.file3
1033	./maybehere07/.file2
3362	./maybehere07/-file3
1022	./maybehere07/spaces file3
3065	./maybehere07/.file1
33920	./maybehere07
1211	./maybehere11/-file1
3147	./maybehere11/spaces file1
4559	./maybehere11/-file2
503	./maybehere11/spaces file2
8261	./maybehere11/.file3
2501	./maybehere11/.file2
8854	./maybehere11/-file3
8845	./maybehere11/spaces file3
452	./maybehere11/.file1
42429	./maybehere11
4282	./maybehere14/-file1
1382	./maybehere14/spaces file1
8351	./maybehere14/-file2
871	./maybehere14/spaces file2
4821	./maybehere14/.file3
1503	./maybehere14/.file2
3756	./maybehere14/-file3
376	./maybehere14/spaces file3
3427	./maybehere14/.file1
32865	./maybehere14
1039	./maybehere00/-file1
6118	./maybehere00/spaces file1
9388	./maybehere00/-file2
6850	./maybehere00/spaces file2
4802	./maybehere00/.file3
7836	./maybehere00/.file2
7378	./maybehere00/-file3
1915	./maybehere00/spaces file3
551	./maybehere00/.file1
49973	./maybehere00
1359	./maybehere13/-file1
3952	./maybehere13/spaces file1
1423	./maybehere13/-file2
952	./maybehere13/spaces file2
6965	./maybehere13/.file3
8952	./maybehere13/.file2
3014	./maybehere13/-file3
4389	./maybehere13/spaces file3
5258	./maybehere13/.file1
40360	./maybehere13
1133	./maybehere17/-file1
8361	./maybehere17/spaces file1
1791	./maybehere17/-file2
3387	./maybehere17/spaces file2
5094	./maybehere17/.file3
8341	./maybehere17/.file2
4422	./maybehere17/-file3
6381	./maybehere17/spaces file3
895	./maybehere17/.file1
43901	./maybehere17
9697	./maybehere18/-file1
7334	./maybehere18/spaces file1
77	./maybehere18/-file2
6348	./maybehere18/spaces file2
154	./maybehere18/.file3
2084	./maybehere18/.file2
2306	./maybehere18/-file3
7040	./maybehere18/spaces file3
5702	./maybehere18/.file1
44838	./maybehere18
888462	.
```
So, let's filter the above output with the 'grep' command and look for '1033' because that the size of the file we're looking for.
So, after piping the output to the 'grep' command using '|', we get this output:
```bash
bandit5@bandit:~/inhere$ du -a -b | grep 1033
1033	./maybehere07/.file2
```
This tells us that there is a file '.file2', which has a size of 1033 bytes and is located in 'maybehere07' directory.<br />
So let's open that file with cat:
```bash
bandit5@bandit:~/inhere$ cat maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
```
Here, we got the password for Level 6 of Bandit.
So, out purpose is complete. Let's logout from the server using the 'exit' command
```bash
bandit5@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
<br />
Password for Level 6 = 'P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        '
### Note
Here, the single quotes are not in the password, they're just given to indicate the spaces in the password
