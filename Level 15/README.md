# Level 15
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.<br /><br />

HOST = bandit.labs.overthewire.org<br />
PORT = 2220<br />
USERNAME = bandit15<br />
PASSWORD = jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt<br />
SERVICE = ssh<br /><br />

To log on the server using ssh, we simply have to type the command:
```bash
ssh user@host -p port
```
So after substituting the values, we get the following command:
```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
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

bandit15@bandit.labs.overthewire.org's password:
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

bandit15@bandit:~$
```
Here, we've to connect to Port 30001 of Localhost through SSL.<br />
Let's connect to it using the 'openssl' command:
```bash
bandit15@bandit:~$ openssl s_client localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Apr  7 17:20:00 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Apr  7 17:20:00 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Apr  7 17:19:00 2023 GMT; NotAfter: Apr  7 17:20:00 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEeXNjVzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwNDA3MTcxOTAwWhcNMjMwNDA3MTcyMDAwWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCH
iEgNQHIIkqW5+CJKSL6ukaIOPmKIM3RPhDk810SwyIsr5mIaIfs4ANx/S86q8SK2
qGa/Ks9y7vkLXvxJi0SFR2yXGDm3dUa3p3t7YXiOWT3IJDXPMkenAjql3QWe/jyw
neuxbOAshTIkEreLEX39yEbyFeo0YJ+mnKRTFarIiqxmzFp7ou5q6nt+jQP9iuFx
ymUiwkhjxvn8vIzHJMOXuZNY93RqDLSttUQmB1eGQkswxWJv2vHG5keTLo1DvdVG
8tD2J32IU9GxiHL0vfQmQ8mdJM3wsNhey+IwH8zVmbBbHzN7xYm6OKi3KBogyJ9O
HS6dWTsI4HfOfx6Q+ncRAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBz
aPeY6gCvQ8p92DbHLoODcEsj9lt/zciPhGyoyMesk7KnNiszr3f/BBl8w17lMcI7
vfluZCfw6cK1TGtBk3x5A01ljlUdKz7y32oGeXiMXIYuFNz0FUfh6qy0Y97e/zwx
6U9+MIioR/xAWj5Gp9BYyabrme9j0reieKYGtZZ62fpT8ehn+3sgjyzbxRpcSoXB
ZVOSK/aLNO1n0InRp96iXEcyLUyw1rx0cIvQuZ0Z2vIlkoOS2Bpf0Y4od2jg5ybN
JtqK2PO5OYBklV/fhbp1SPcBVnoGi1lUOEtP4kk0dsMVigo1vfyzOpBHjANCHnM0
AnDCZA0IQXG/ftTkAJDw
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: CC6DE83FE63DD1F8D6DB034725217B95850CF7BF635B9E8435ACD14BBAAB3DCB
    Session-ID-ctx: 
    Resumption PSK: 1441177B9F9EDF38974E578FF659636F19F90C70CB7E722B9517A8F7DD8FB57BB7938E092BFFFC723347374002974968
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 17 0d 2a 47 5d 3c 4b cd-12 5a 7b 7f 16 5f c7 f9   ..*G]<K..Z{.._..
    0010 - ca 33 d2 8a ff 09 8e b7-76 8c b8 54 a6 c6 51 b5   .3......v..T..Q.
    0020 - 35 2d 9c 80 e1 ef ac cb-6e f3 ff 3c 1b ba 47 90   5-......n..<..G.
    0030 - 90 9c 56 9b 34 0f f1 36-c0 a6 53 51 69 cf e2 b2   ..V.4..6..SQi...
    0040 - 33 60 61 86 3a 00 e9 b0-0d b5 ee da 12 cb 7b db   3`a.:.........{.
    0050 - ef b4 eb ea 73 a9 b3 55-8c 4b 31 87 d0 2d e1 24   ....s..U.K1..-.$
    0060 - ac 7c 30 36 eb 8f df eb-3a 13 65 af fa 0e 8b ae   .|06....:.e.....
    0070 - e9 44 28 a7 c4 43 0c 5e-7c 74 94 d4 ac d1 b8 17   .D(..C.^|t......
    0080 - a5 29 37 69 8c 11 5c 57-e4 40 c5 00 80 f2 19 9f   .)7i..\W.@......
    0090 - 91 26 3e 1f f6 e4 16 ce-3c b3 45 c3 ec 85 0e a8   .&>.....<.E.....
    00a0 - fa ca b3 8d e3 40 51 bb-cc 3b 71 d9 38 aa 37 79   .....@Q..;q.8.7y
    00b0 - 9f 17 0b e5 8c b0 83 f4-70 c4 ab 29 a3 ed dc 02   ........p..)....
    00c0 - d6 31 5e 54 f5 96 db 7f-b3 53 5e 87 f7 60 42 c2   .1^T.....S^..`B.

    Start Time: 1681258077
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: C1907EF3E426F5B7186F59BEF799FDDE00AF4F13A9E4C2C0016E88EDAE7D575C
    Session-ID-ctx: 
    Resumption PSK: 46FD8442B93A74B51C8DE7935E6FAA6B8BB69D4D6279CE6171B114AA70CF60EF4B2F0A1FE83F4368B11DC275C608DE08
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 17 0d 2a 47 5d 3c 4b cd-12 5a 7b 7f 16 5f c7 f9   ..*G]<K..Z{.._..
    0010 - 47 ec e7 7f f7 01 41 1a-51 13 26 31 f8 34 c1 63   G.....A.Q.&1.4.c
    0020 - 6a b4 83 07 f6 fc 62 d0-dc 49 05 44 37 44 50 72   j.....b..I.D7DPr
    0030 - 64 28 ff d3 08 f8 e2 db-df d6 db ab 53 1d c6 ed   d(..........S...
    0040 - f9 38 ce 8f 08 f2 4b 2b-a1 d8 5e 7d c7 6d d2 96   .8....K+..^}.m..
    0050 - ce b1 fd 68 66 5f 1b 4b-c4 b7 2b d8 d2 d2 e8 40   ...hf_.K..+....@
    0060 - c7 ca b2 ce af 7c 7e de-6f e3 8a 90 95 9b 6f 4e   .....|~.o.....oN
    0070 - 95 d5 42 d4 87 d3 44 f1-df 7a 21 d9 42 a6 1d af   ..B...D..z!.B...
    0080 - e4 32 0b e1 b8 22 c3 eb-05 98 b6 d5 2c f9 6f 9e   .2..."......,.o.
    0090 - 34 49 79 21 a1 ea 7d af-4e f6 85 dc fa 82 9f 04   4Iy!..}.N.......
    00a0 - f0 d9 36 38 8b 45 83 5d-36 81 b2 09 09 5f 80 07   ..68.E.]6...._..
    00b0 - 46 eb ea 74 a7 b2 0a 2d-4c e0 85 cc 78 a1 d2 73   F..t...-L...x..s
    00c0 - 1e 9f f1 a7 93 87 0b 6e-f3 3c ad 0c ea 87 62 16   .......n.<....b.

    Start Time: 1681258077
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
```
Here, We've to provide the password of Level 15 to get the password of Level 16.<br />
After providing the password, we get the following response:
```bash
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```
Here, we got the password for the Level 16 of Bandit.<br />
So, our purpose is complete. Let's logout from the server using the 'exit' command
```bash
bandit15@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
<br />
Password for Level 16 = JQttfApK4SeyHwDlI9SXGR50qclOAil1
