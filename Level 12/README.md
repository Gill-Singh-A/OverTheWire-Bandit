# Level 12
The password for the next level is stored in a file named 'data.txt' which is a hexdump of a file that has been repeatedly compressed.<br /><br />

HOST = bandit.labs.overthewire.org<br />
PORT = 2220<br />
USERNAME = bandit12<br />
PASSWORD = JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv<br />
SERVICE = ssh<br /><br />

To log on the server using ssh, we simply have to type the command:
```bash
ssh user@host -p port
```
So after substituting the values, we get the following command:
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
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

bandit12@bandit.labs.overthewire.org's password:
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

bandit12@bandit:~$
```
Lets check the current working directory with 'pwd' command:
```bash
bandit12@bandit:~$ pwd
/home/bandit12
```
Here, we see that we're in the home directory of the bandit12 user, in which the 'data.txt' file is stored.<br />
Here, lets type 'ls -l' command to check out the files in the current directory.
```bash
bandit12@bandit:~$ ls -l
total 4
-rw-r----- 1 bandit13 bandit12 2573 Feb 21 22:02 data.txt
```
As given in the statement, 'data.txt' file contains hexdump data, so let's check this using 'cat' command:
```bash
bandit12@bandit:~$ cat data.txt
00000000: 1f8b 0808 8c3f f563 0203 6461 7461 322e  .....?.c..data2.
00000010: 6269 6e00 0134 02cb fd42 5a68 3931 4159  bin..4...BZh91AY
00000020: 2653 5953 6696 8100 001b 7fff fbdb effb  &SYSf...........
00000030: b41f 6efa a7cb ebee fff3 b7ad 897d f77f  ..n..........}..
00000040: 67bf beff bb6b aaff ff3b ff7b b001 3b5b  g....k...;.{..;[
00000050: 4100 00d0 3101 881a 0d34 01a0 000d 0006  A...1....4......
00000060: 10c4 d006 41b5 1a0d 0064 0340 64c8 3468  ....A....d.@d.4h
00000070: 1934 1a0d 1a68 da26 26d3 50e4 d0d3 40d0  .4...h.&&.P...@.
00000080: d001 a341 b500 0032 320d 0323 47a9 a683  ...A...22..#G...
00000090: 4346 9a00 3d40 36a0 0308 184d 0640 0068  CF..=@6....M.@.h
000000a0: 0c43 466a 0d34 6832 9a68 6430 40d3 4d34  .CFj.4h2.hd0@.M4
000000b0: d0d0 7a80 d0c2 69a3 268d 1a06 81a0 00d0  ..z...i.&.......
000000c0: c83f 5232 3400 c406 8da8 0680 3400 6800  .?R24.......4.h.
000000d0: 001a 0020 2823 e282 2299 1ae9 cfa4 8ea0  ... (#..".......
000000e0: 716d 6e03 9844 dd8b 7260 8c1e e05c d068  qmn..D..r`...\.h
000000f0: 9a86 f4d8 b355 8786 1723 3041 695d f96a  .....U...#0Ai].j
00000100: f8c0 503b 8df1 eac8 138b 82ed 21cb 9611  ..P;........!...
00000110: 6d6a e5c3 c7ca 637c 26d9 ed7e 107a 14a2  mj....c|&..~.z..
00000120: 6c54 8868 511f 481a 6412 bb95 a771 0401  lT.hQ.H.d....q..
00000130: 3ca4 96cf 7e08 0e31 d967 e4c4 4fee 206b  <...~..1.g..O. k
00000140: 8793 ec23 4da7 44ba 3ded 12e2 b947 9288  ...#M.D.=....G..
00000150: 7809 0ca2 6b04 5f0d e0b2 6717 7e87 0628  x...k._...g.~..(
00000160: 11a3 d282 9d61 f0a4 340c af19 d501 4ddd  .....a..4.....M.
00000170: 1a8c c27b 154c 531f 345c b6a2 7298 a20c  ...{.LS.4\..r...
00000180: e02d bb16 9127 5b42 30d6 634c b7cd 54ae  .-...'[B0.cL..T.
00000190: bb26 9494 2a19 33bc b233 0d8c a75a ccf8  .&..*.3..3...Z..
000001a0: 401c d5f4 bd06 7c43 cd73 32d3 84d0 c440  @.....|C.s2....@
000001b0: 004e b2e9 de84 8251 e080 1a1e f506 e546  .N.....Q.......F
000001c0: cf30 31af 361e b04c 8f5a f636 f1e7 4c24  .01.6..L.Z.6..L$
000001d0: e14b 456b 109e 1421 99e5 ead9 3840 038f  .KEk...!....8@..
000001e0: c1d8 c71a 9b5d 5435 afa0 5eca 34ca a83c  .....]T5..^.4..<
000001f0: 309e 6b5d 532f a0af 20e0 bc3f bb03 a680  0.k]S/.. ..?....
00000200: 6616 4b13 9d09 bf8b 3a93 6f16 b48a e6cf  f.K.....:.o.....
00000210: ccb9 084c 8a35 12a7 447d 8224 4491 e534  ...L.5..D}.$D..4
00000220: 0c71 2f36 fda1 8b54 0808 a144 9894 966f  .q/6...T...D...o
00000230: be74 2140 952c 0294 a1d6 841e 1658 756f  .t!@.,.......Xuo
00000240: 0d7f c5dc 914e 1424 14d9 a5a0 4043 a8c0  .....N.$....@C..
00000250: f434 0200 00                             .4...
```
Here, we can see the hexdump.<br />
So, let's reverse the hexdump using 'xxd' command:
```bash
xxd -r file_name > output_file
```
Here, -r indicates that we are reversing a hexdump file into the file itself.<br />
First, let's create a folder in the '/tmp' folder of the server, to uncompress the data.
```bash
bandit12@bandit:~$ mkdir /tmp/temporary_bandit12
```
Let's run 'xxd' command:
```bash
bandit12@bandit:~$ xxd -r data.txt > /tmp/temporary_bandit12/data.tar.gz
```
Let's change our directory to '/tmp/temporary_bandit12/' with 'cd' command:
```bash
bandit12@bandit:~$ cd /tmp/temporary_bandit12/
```
Run the following commands to get the final data:
```bash
gunzip data.tar.gz
mv data.tar data.tar.bz
bunzip2 data.tar.bz
tar -xvf data.tar
mv data5.bin data5.tar
tar -xvf data5.tar
mv data6.bin data6.tar
tar -xvf data6.tar
mv data8.bin data8.tar.gz
gunzip data8.tar.gz
```
It will finally give us a file named 'data8.tar'<br />
On opening 'data8.tar' with 'cat' command, we get:
```bash
bandit12@bandit:/tmp/temporary_bandit12$ cat data8.tar 
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```
Here, we got the password for the Level 13 of Bandit.<br />
So, our purpose is complete. Let's logout from the server using the 'exit' command
```bash
bandit12@bandit:/tmp/temporary_bandit12$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
<br />
Password for Level 13 = wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw


