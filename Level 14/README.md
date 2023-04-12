# Level 14
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.<br /><br />

Continued from Level 13....<br />
USERNAME = bandit13<br />
PASSWORD = fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq<br /><br />

Here, we've to submit the password of Level 14 to port 30000 on localhost to get the password of Level 15.<br />
Let's connect to port 30000 of localhost with 'telnet' command:
```bash
andit14@bandit:~$ telnet localhost 30000
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
```
Here we have to provide the password of current level, which is given above.<br />
After providing the password, we get the following response:
```bash
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

Connection closed by foreign host.
```
Here, we got the password for the Level 15 of Bandit.
So, our purpose is complete. Let's logout from the server using the 'exit' command (We have to use the exit command twice because we've opened User 'bandit14' from user "bandit13"'s shell)
```bash
bandit14@bandit:~$ exit
logout
Connection to localhost closed.
bandit13@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
<br />
Password for Level 15 = jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
