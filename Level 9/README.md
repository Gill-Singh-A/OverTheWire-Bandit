# Level 9
The password for the next level is stored in a file named 'data.txt' in one of the few human-readable strings, preceded by several '=' characters.<br /><br />

HOST = bandit.labs.overthewire.org<br />
PORT = 2220<br />
USERNAME = bandit8<br />
PASSWORD = EN632PlfYiZbn3PhVK3XOGSlNInNE00t<br />
SERVICE = ssh<br /><br />

To log on the server using ssh, we simply have to type the command:
```bash
ssh user@host -p port
```
So after substituting the values, we get the following command:
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
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

bandit9@bandit.labs.overthewire.org's password:
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

bandit9@bandit:~$
```
Lets check the current working directory with 'pwd' command:
```bash
bandit9@bandit:~$ pwd
/home/bandit9
```
Here, we see that we're in the home directory of the bandit9 user, in which the 'data.txt' file is stored.<br />
Here, lets type 'ls -l' command to check out the files in the current directory.
```bash
bandit9@bandit:~$ ls -l
total 20
-rw-r----- 1 bandit10 bandit9 19379 Feb 21 22:02 data.txt
```
Let's Open the 'data.txt' file with 'cat' command:
```bash
bandit9@bandit:~$ cat data.txt 
�x@��N�Z��m�d?I��f�YH1�`��tm ����
                                 J��<ߒo�����Gy�q99B�L�������G���H*�$������f8��L]�.͔~� �ݏ���P�\股��C:I5H�o�K����A���
                                                                                                                  �܎9����D��
                                                                                                                            �=�	�^�s���RD�'�F���
���r2Fx�-o%�:�#6j2�矉w���aY$�ˬSu��J!�ř��|�8�J�Sʓ�s�����dpjCkC�����F�߼���d��--\'�M��z�t8�i-}�cY�%��>�0:�ଙq��S��bj��"�T$d���G��N�wmZ�E�x�j���!_�N�Sz�yjD<'`#ªdS=57�`�L%��L�����-[Ȅͫ��WI[<�i� ;�=�&�����p��D���kf�
�w�1�Q��v�0^=�c�(�
9J�[��[�`^���fHK"��1yDD�ꠊ�q��
                             �Bv[B9;���Z'�{N?ܚfxL
                                                 l�l��GFVY橬:�;~,:�a�VņW�`=�ix�
                                                                               l�)��$�U���d��
F�j�>G{�(�_V�.��j��f��<��[�k+'B[8KXڼ�:����:>���G��*ڶݜ�&��8Rl�5�m��,���w�Z�~�l�粔�t��U���� �F8�-�5@���1��h����
p�K[�Vծ�Ϗ����-Iv'9LfLx"*�                                                                                    DP�w�o�B7�#�PXI�%>�l��u��'�%9�gJ�7w�Ar���;8�FK�i�/3���.إ(?�)�݄�������c
                         ��
                           N�,n:,i��0��b��u�c��uQٷKz}G�.������ة_�.E,���X���.�N���l�>#4��!��C�$�g����ۣ@�~9��>��		㧭�{˴;�iz��[��Z�jq�׀3D��/���K:��V�Q����^��~G��@}8k8��f����2k����E�.���-�����Fk��]qC`c(�ч��G����+D�ss�c��4�fs4l�Qc~���f========== theM�����3jB
�����uʰ��:A�]%�ՠKI�;�-�ؘkOg}��z��ѝg��ț�12�,YZ�u$�n�,����-&d9c��_)Z�|M��1���WA�L����#��E�S4r��6�Z�3�<�_�n��� ���9�E+Q�������/+��xe��Y�s,<)���p�ܼ�
                                                                      �{o��IB��$�h{W�Nh-м䁽[�
���z/�#/�8&>N�aQG�mvp��<k��[�*���K?3�4Y��/�r�g'�����vԠ��.2�7�];�/�����bۊ�=ɘ��m�0M�H��G�, �!z��ܓ�ZK󡻢 �@Y�*��֏|*K��b��V�qP� ��&Q��)ٮ'l
                                                                                                     �"Hmz�Sj`%Y|�u
����?��UD�@i�Y                                                                                                     ��z���b:\�����\�E�(,O��d�2/�J0sYA	�x�v+�����V�q��;
              KІZ�����qYmE��2��^77'p�Q1
                                       ���(]7_��'QO4	���>��o
�nkΞ6A�v�F)                                                    ǽ���UZ�6���I�p5�ȥ��w��M��r!oǗ��F!�Q�U�ȝ���|�_�苛V��mk=��"����
           �0��k�G��X+��#���]�Y���[���$as`R��syJ�
                                                 b�i)Te<Ȩ<�mTZc�|X�_���t�q����S����wR�D���1���%x��k/G$��dJ�ŌK��L+�F�XMR\��M;t��&��q$[�/K���v���c0mR�s��D�i��+�y�[*�
                                                                                                                                                                   ��S�0��-T�����A��W8����M����(K���o��ˈ,�d�	|��[����
                ��V����Eɍ�i6�`Uͷ��ţµ�����D�m���v. �Ə�X�z�c/f9代k�����)K�,��~I\U0f���i�c���|G�z4[X�4�J�#�s!���/;m�]S����'HO��-K)C���%s1-�XeH�n�2��NH�bC�Iq�	��f����&�8-=�5���£c*�\��1�N�z2'��<���Us_�y�����<�N��[ե�C�	AH���d�/��)
D�q�jv҈��{�Յ�F]���Dcx�<�#׫o$�#���qڋ��P�-.�C�7�S�@t��JloB�ڷPϜ6z�d1��Kmp*�Q���x�x�L#���:�O��D���|��_�=������L�w��З���#I���T�u�
                                                                                                                           �JP�1�6���,u8Wo$�����g�`!�v���*J�v�+cf�����0�#�w�mvhx���'&��}��g��z�x	�[��.�t�)���JT!
íR�.�ڊ���m0C3�H�2�?s����:�`�N�<*�ĸ�o�ؕ��%sIt�t�#�a��P
��Ǘ6i�:��������8zD�.�#���H��\���5^?v)�Jϙi�8@�������Ⱦ�����k.2~��㪥Q�~�H�
�/]/�A�¡������Ph�[�='�k�R]�t�E�\�4H!�r�K�޼7@���Y����Հg՛;���b�/3�Wv�a�A��P��x؈x�w��~g�4����
=Ξs��M-"c�ı�/��'b�*�Y
                     ����������|�ǡ�8Ƣ4����G=�X�=���8~�d�#�2x*���
Iŭ�y����s�����$OH�CH$�OР�b���~�H�=XeOh
h?�A������|���S�g�/D8e�ԿO�Vj�êz��=    ��"7+���bq���V9��|@�	r���	
                                  :q�"�Zzg����I�w���/å�L��\����G�-`��#�-1m
                                                                          �9}�������Ď���[��'-<'15�E<�.r�X1Q\�u�c(C�ۅ�,Q*��N�+�jL>�6�=vb`�|cW;ce��ۈ����?g���-�׻�Z�F�O!l�3c3���̋Mxǳ����a"/qY��f�Dk�L/R���\�C���/���K~�{��e�nJ�����q��;��o�<L$Y;8͛�'�h�X�f?tK�?����RL5��._�קO産���dv���U1����6c���M��g��c��#:��@`IrU�a���J[p�蹂��
8�h"3Id����/    RS�����Ъ��jXz�b�L�OP?fv���n9���14��ŰX�>o                                                         o�V�<�eZ
                                                        ���G̟эEE5?U|��x��p����'}��33�_��Lh�e�ĕXp��7�o@����m��Ff�^E
��XyU�X 辿�bc�S2�LrH�%�71�p!bө��S!O�7?��δ                                                                        9Y<��R�r���{*�p�<������"��<��K�����>LA
��4��?'���Na�紌}�*��>)>��K��7��7�k{k�KR�+�b�5��$��iC�{��!w�wA��/��Y�Q?�k���u�����⊴�{��U��A^Y��ϖA��F�w%��P�#o)��A�U���:����w2M��o2����*�[0���L�U�.�s��x�6/�{�w�Co�,<B�ۇ䑵R�n_���D��e�Q��
�U�2�����sW�����K��n�.x�-(̿�Y֎]:�a�̜H\>�c�lPg ��AP�

��ط4%Qz1���kR"��V�|��ͧ'9�а�w�����/v�AƦ�P��9l�+���k�ʨ��P��S�y��EuW�#O�#
                                                                      �B��4�5�N:��0�w=	���_
]�f���5��a����2���
al�@���NF>��N^(f�2��E�isPտ���%��u��W)K�m9����ʢ��Ym�x�s�+k���#���]X�G�}��EP�`91ڵ��'"����B՘nK�N��%vf�'+��Zt(�Z9T�
                               ����u������?<�Dh�㠄���՝阰�,~\��Lx	�[��<Ɠ����R���/j]�w�m�>L6���>

E�a�oQy�:�g|��B��99lR�j�^r��S�C	���0��r�Ys��a���R��IZ��y���p�*�<�:
                                                                  �:Z��g�m��aiw��X�h
                                                                                    �ɊzMy� p��W��x����K0��b�oz���@0�m(�g���O=Nq�;��o�����F�  3���cpM��<b�O��"?�X`�`[�aAk���$���	��ls��ӢJ)��>
                                                                                                                                                                                            �>)9d�>�~��p��k���xBU�Py�f�
            �mi
�Up�           ��[�{��g-pT,�{��=� ւ7��5�t�Aڣu����"]�f	/Ȼ��C$�՝ʄ�#0�p�C𡸵�Oy�n�1�"T��˽�;��؏{fV
    �X����6=I6a���hl�f�c�R�r28w�/���;q�|*�i�W�F.0�8=j�����|�mN�`�:�N(�t�mh)�ڔt���-f��ݥ�i�;����5��L�d]�[
                                                                                                       �\DgR��D܎d8l�
Y�;
   >1�Z��zu�%(���ת�=��{�_㍺�:"P^
.���������#�.�qt�4zf�[6�D�Y�ԂS;�
                                A|9wE���[R��^�========== passwordϧ��`+�{�0뾱'^
                                                                              `��ٴ*v�W�=N�)j;S2{�L��ǒ�H[/�|�q$��(��؁$TV��'Z���W��.��]~m�H�����c��3��T��r��Aj�`C�z�.��/t��n) ���~Z^�t�������m�m����C��_^�,1�
                                                                                                                                                                                                          Y��
  �Ia�ޓ�
        ׺ڰl�ڪ�\�WT��QT�^1���
��8��v: BF6T"�/��2)�P���7V��M~CVx_'�ȰBkS�E�Lc֭<�6"9ڭr#4F�����(八��U{�UT���-�P�M�s$z_6^E��W�>���F��O��j��K!S�M�b��
                                                     �j�1��;
                                                            �����Xt{�_`)�7���U�z��,�r;z�"�_I!�W[�ػ�/n��D�k����R��o�ּ�80��Y
��+C�E?�Y���ɯ#���
                 ��*���n��)Id%sYb�G^aJߐ���q~��/?��3
t1���8�x�{��K�e����f|�U�[                          袊�9��Nr��K%��?h����
                         )�M�����yt-���?�
                                         �&c0������
                                                   ��q�+z�l�D��qC �Vh:�?�6l&#��ω��Fd&�/�xANM���e�9��U�"�y��"N�D�����dWE8Z���-��c�n
                                                                                                                                  �������֡W�8g�V]�a�t�I1��-Y�`")�̲��Lޝ/$i(�/�Gas�G�P���_��$0`����]��y�J5��y�vus~ �R-�6�!�m3��Pq��6w6��X���Thx����p�-<�`Gx�$/�ح'���$�{�(i�4���?r0��ac��,8���:R@-tܳv��m�`&���p�[6����B.ek
��#��#k֣+��ۢ9�䦕Z�z
Q^�.x�H�.l��R��]��"HL1����\���O�?ym/�Ѕܣ�1�͏P\��Z��.�Gl��4o7�t�>�kY����ϕ8��X��ׂҖ�CM���C��wV���\P]N�/�]�^��3gJ�s;�G	<�h�A�S�Cu����n��|��&��L�C'_]�ZA��@�
�,_�bΓ-�ͬdJ�9Q'�0���g��0��ѳد��h֑���ͱ�����������@��q�5s8m�������G�(n>���E
0�f��;s���-��E��EDs��Il��՚���>��d� 9����>PH
�3�A'�X��=�QN=�HZ�$Y1nB�����8���P��h���;U7M�Wf�_���Pl�ł\pg�@�T�ʛ���6h�Pݙ���5����w�j��r'HI�<07/������� ������BcA�>0{MKqzdk�('�&�========== is�Mo����$���a��[�l/i
                                                 �H�Hp�CS���V�����i                                                                                            ��oɶ�f���ȉ>ܙ2�H���߷��M�
                                                                   �s�5}�G�p���A�xI��;��}z���WW�[o�b�Hh�z��S�"`��#aE,�]biʈ'I�|Ӡ�+�`�2?#$������.4�ޥSπܞt���W.�Lߒ�-�}QHށ�9h���3�&�A�:�c������}�K�u��X9W�S���1����i�zR��F'�C��LTEfe�s-�����#3�C3<�Dt�l2IB����u���n�6�L��y���ݾ1Ks<���7\�����O����}���^]�Y)~_yNQ`��w�F�_��M�q���ҳ�k��r���l�Y��I�~�l!�sE�;
�u��"6V-(�,�u�j��h޴e�:j���&��                                                                                                           �&���21��AT{��^*��ݩ_>��!u����f������_���J��ԗ�������$�Qw�o�x
.�Ƶ�y�b�#�'�(eXa�����[�^?�߻�
��x$��,�gŕ������l���}~�h��RX����a����Y�dk:xY�ę������K������{o��\W?�.�ۈ>�L:sVs�V�Ƿ��q�&�����-8�y+���z'U��p(�cR��c�n"�*�(���L��2�,[���?N�k7���|6L�
�ܯ�f̳�F�fʲ+����f          ���t����~��&Rd��
IMw�U�y5�d;�%��O�9W������1�
                           Q7�Y���8*���o�9S�_<s&��t<%P?hNO�V�A�Q���r�
�����q0�G�40�cG���m�tr��8����]��g��/�J��EW�O���C��IBd�lݴ� Q�         ��
                                                            �!�?�      =�Ȃ�K
�"������m`r�֪�+7y氏?�'^[��:�4                                     �)quKc2��Ll�ٳ��ǟTw9�e��2�Fhlo�wi���q��h��tf-��t^g��YCգ�8x7sDm��-�Z��8��+��&�"sunZf���2ώ2�ܢ�Q��J��L5
                            V�C�a@�#/,�t*�Y�Q�N�������^�,�                                                                                                          ���
                                                          ��9���aҽ                                                                                                     �:�X���rj�?��������8�"D"nb������o���;���7���w2��rܻ����~V���S:T                                        ��s�~Fh4�8P��Qc%d#���ם^v'�\�]�a��HV�vt��aťN�ȏ��Y�Ӫ8kM��`�E���H,�c��n�>VtL�%�+Ph�^�o�u�%���sfK���S,�&
��T�[�����0j��)���ĸ?��o+ѫ����3'FL�W�~�c+�'��6�-��z��U�<׭��0��;K�                                                                                                      "1�U��-CC	bp@(�$��b[��V\�j
�Q��j���Sh-6FCS�h��G|CO4{���i�����X�.Y��7�r����v�       1���ƫY^�φ����w+��OJ9���#��<�6;8ҰF���_�3����L�ǳ����5C��N{OV��=u=�*��M�1"m�I>��A  ��^l����ks��[t�,�W�gc�8_��詤r����/��R��^`�\�V���{��E&   !U���)s��*��Ex�·�M'�,��&c�D���3x��0�3%�                                                                                                                                                                 MMq.f�E
�                           l^�9����QO��!������<����P�"6W�3��5D��dX����                                                                                                                             ��42
$85xmS\T����~u�Q�90;C������E�g8�M$�Og��t���sU��Ĝ+z_B�RǉDO`IEů�x�SQ6�g7���g�$�G�0��Q'�S{pS*�\5:�?e�W�7*5�6ȕx��H�r%w�k� �P58�Y�$�9���X܇G!��VخD�`�����_�����wWiXz�#����ex�|_�_�2�e�
&����V4<:{��R�ӛ�� �Xc��X�@��x�#2�N(F�%d�f��c��UL���Ѧ�$�:昇�8
�r���嬕{�:b_���*�^���?%����Xs,�v��jj��U�b����7�f�(���K��!~^�Oxo�T�nf�_6�lO��B|�|;�_�ļʤ-N��JB��y�j=GDµ�W�K�t���Cƴ��R5�����JE&B��8�Dr��
                                                                                                            V��g�Z-�;`ahG^$�5$�&�\H\��NX)RSMOē2��j?��S���l?�?��'h���l�r$K�)R#u��W�1��c��MPr�TV��t���ƕ�oF�V��aG�]                                                                                                                                                                                          Ur���f<E��aW�M   D.�J�aI�F��u��W���mQb���q�#;���"E�Ĥ?s���Vӯ�n�����rx�X��d�H�Vy�~��?<q_�CP�ۦ��O+��s�&EÉ���G{��[�> AP��HݧH���OY^��մ8b��T���P��t���n�}���-�6�4�sC"V�}"�sqR��q���/Y����
e���M���'��B',�uXZ�P���qfY�KF�U����OeF��D5ZyT��$$l�?-�����[���Ψy��%�$B�_���3ç�����a�z��HEɏ�z��\Q�����Ӕ3?�Fd�6좩�ԧ�-k������ψ@TS4�`�����-�:�F �ٷ                         �H�
ww>۬W���Ϙ?�5��t�e�.��e/�9����w��O[�\��1���of���Ypr�T���UD6$�E��Y���L��� �nm�8�:Z�{�w��D�>�7��݃�QvX$A�|jD��b���
�����k��__�+na^�j�%�:M�`��=E��v���,c��� KbL����u#�.����{���V1i�<�+XT���3�O�Y��C6zE�H�2��{�Z���*|%���L�vw��dwL������Z�F����^3YF�M�ԅB�� ߸�i��D�8.����/��K<U��3���H����]I�jf�^b��<j-�[~���DS�BV���7���g1066NJ{�<�L�ܤa^�e�b2��(<�) ԗ[�G�$p�0q^�D�\I�H�`�A3                                                                                   �}:�2�s�T`��t�͏���ю0
���-Ycծn ���ϲ�^{�P,��]�2���E��/#�\�m�~����]���=��?.����1�ޝ���~!Z�9U$lG���S��e�%��Y3G                                                             �:�+���y��k����ڌ86�X���ŞO�}.D���8/��s0����Rr�7r�.�,��aK�A6v���^��z�d&:VCx����;��=�k-y̲2R��Ʉ[���d��5���fq����4x�����S?���jw��9�������pRԓS�i�iA4;�Y���¬��3W઻��=|,�r)���
                                                                                        �f�E4j�o{I�����x7����/���-b��t��<��ÛH~�d��X��f���C��G�\4�\���=��7�5����ѵ��4t��)]�Q�ds���c!_)��+������ пf��3�T���7$���ތ���$t�s��ո;i����3j�bZ���?n�yQ�Q1��U6 �:L�~ͣ�<���i��g��ſ                                                                          kظ%Af.Xr���!���%�YB���f`�3w��@�+)<ە��t�g�\������qG�Te�	7��J��15��%���n!%�=���                                              ���i%sS�^x�{Ȁ/]�V��~\pdM������6��?DG������ۍbq��+�t�w�B�=6V���!)Q�n&_�����AvLF����T�h
           "0��t�YP��#�,)���K��J���}"�޶����*��EX�q�/�-�L�PAۣ��۱����i�j�W��uv}�h�K��%a�_�f6�-�%�=���e�                                         ��Z53�����H����@�c��jo��aу'Ei�k��b ^�Of��C�1�$�6!�+0����t8�=�Xƻ�G�aa��`�L�ᏻ3h�PpqJ6M6z7lC]�M�P*�Lo��d.TVkA�d�5[�3����.�<���-��& ڥX-h�S�/k���a�\�gۘ�쉩�ʊ�Qo���j�W����?��^f1P�����V�ls��L�����Qj�����8�0~-�W��tX�=�獄I�5�����c�;�3���
                                                                                                                                                        � �         0"��I�N
�[��?�f��߻�Mv���Ik����+���A�y}:7�`!6h�p;�L]蒋�৭��Ǡ�lk������T^���d���)v�M�rzM��ݬ��R�9l�.�7��&�OZ�BW���H���M��+-���Q#���?���TLF�N�iI��Lv��3R��>�g�\��k�A�ȹQ�
%�~�h�I�����?�ޜޛY-՜O��Z�>8DUE���t��� �$Q��=��ڕ��9q�wXFΖ�Nb5��,�]����<�I��3�AuQ��'
i                     W�����Ȗ����Rκ����ޗCɲ?*(�-~A�ygb3��Mw��'�ލe��c6I�ܮ�:���+Q�sT��l[~�꺒`�kY�/���}(�Bi���-H��c3t���Հ��Hj����N��t�qk��6i삙���4��Jza�0��?��2�2�(�R�1��*͢lF�DH���;�!�+�A�e?wr�������-񪥃��~|	���ّc�v�� H0��F�@�[��"�5�F٤�TIm4e�i�А�u$gD�3)䝢�M��5�]��7������!����(�7��ɋ��<2<y��ϲtV:�(m��H�'���(��`^g�WE���V�<מ'�
  \b�y�S��1~=y                                                                                                 ��j�J,��~]��r�#���	����D�8��u~O�������54%neȚ�Y�{S��Γ��%�0W��s`/1��I��~@�<�����q�7�՗��8$�΃�.1�H�w�m�>��W��n�|��e��@�uJ(DB�k<��<<z�7�51/���q����H���[N&�m�&�h���r�N��*�|0�M���
                                      gh"�_��,5����ahbUf��)����1���V���               �Y�]
                                                                       r��Gf�ou;��{|�2 �����X{>�Yvi��E6P�Zmjz?~j�4���wv���"�Ӯo�b��3�웢�WlG�A�L6g����Y}@��ozZ��.��<�v�V��B*�	C���ӄc�.B�&�p4?��	'cPf��&��Rgm�t�i�!��Ol@�iVf�L�i'                                                                                                     D�
��B\��Қ�����g(�y)�|�C�G��#�׿J�$OE~M��bS��y�I���� mt�2��                                                                             ������/O��a�]l,���XϺx�ꬬ���d[K;+�0?F=(�aV�����a�]���S�t�P��ͥX�^�ń9�o����,Z��� �a|�b���{+s���wo��0�<>��Q�(�@3�${��.��g�sp�d��{N(�h�ٮJW��j�jZ��A/� �*��[��|ǲ�<Q���`&cl
Ғ�vJ��1 �$*�&l�D�3��c��x�0?.Ws1op>��j&LA��`Q��6C�O����$=�V��X#�KZs}v���f���>����<>��,_���1G�)[h��t}97��l�܀�{J<ձ瓓dBK���ϗ����;ʡ��N�$��i�\�v�&%�r��7�/��������i���'
U�ɃA�����3�;�}oB�`��W|�0g�j��/ܡD��j"�ߠ���f�?ɥН�uiki����g�<�Ų��T��n�Ha�Q�!�ەPvWӖ�^z��r�m,�G��k��wI���W���mu��>i�#�t��__���O���fJ~��sQ��b&�|(�er��A��_Y��H:7�v>hJ�/���q�%�LRq`��b�Ǩ�S8?l}^�R#���@��t|;g�\@89ŬE�X�A���Y�ng�a��ߢ�;��3��Fƹ����髳��"n%�Y������.K+��Ӛn��AS<��|a�q��"Χ�d�}��Y�����O�<a�l\��̭,���>�Ӡ���Q��R�Ͷ��l�������7(����͍�
                                                                                                                          �t�b;O�i�W#�ges��+IV֑��d6�y��Nq�����)g��x�]!t���u�'��oP1p��y3(�8K,1O����	��������}�#e6I�G
d���Q�(�!ٍ���)��ǃ��4�4�,��^�{�e��v$[����5���G�HKʌ����j L�W
                 z<�
                    ����E��n�D�.DX_/=���Tm�5'��h[!Ϋ$s>0���	���kCs�;�e��Q8��?+'g���bea��&�ּYu�bRz�:��ˡ�+N��ϵ�fP[[��jP���=V��-��X#R(�|�G!M��========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
@��
   ԞlU�n�G<*����,�jQ�(�S�?Uֱ"�߳7q�@`�X]��r�/�8w51�_~tVO���5��`�N�
���A3�[?x���vqHy돺�{�&][/�۾��ɳPX\�                            h<�+0��6u�=�vR�3/B��)ƼM?`��V�δv��[���LfC�M��n���W��b��i
                                   g�]��-������{
�����d#.�XUJęD��^v�<���ܳ%�'3�+q��aH�&q��9bd��0�i�D�u�1�%��n��` H�g��/��h9�б
                                                                          c��)*
�؜~V�%�2�Uy$HK��<�>���>US]b��ʺ�S���"!Þ�%�s�9��uZ�+*���>��W@S[S����γ����`I�2�zޏ°���V��@��w&���V��CJ���>��0�]I�F\ybŘҸ�im?�r�AG���ΧH�9
��`<�σl�]
         P;�����j�e�%_�ST��TGn�$L�7G�V/Y�Y�d4��n�w�6���TՈ���y!Q�Ϻ��=8T������v�+�\���Ϡ^6�ε�cL��<��������Rh�,������pP��v��GGvf�л��{m]�"�ϩ��Ȗ`O�
                                                                                                                                             �@��4��bo�E ��p�ip�'(��|H�y�Aq�zh;gG�{����e����Ѿ�G�r�#p��p���qI�]`�K�S���#<{p"5����L�ϘYm��
uהn`c�y�h��ST{J3��8eb/J�    �g�3����}��Ŏ�[�&>;<�\�~��9Z��`��y��X%���[&<���L�W�bѫ79O����7T/�[��h���@����V[h�=P%$8p����\9�H��1����
b�m�P�[���0�������F�TcȮ-����eI�9W0��m�7�������t�L圦toS\L��O�sh�Dj2ˇ�T��#�M�H��/Z2��G�oR�S��T�EU�O
�o4^cp�����?(0                                                                                   n|N�R�n�|<�ji��lj���Z�B���y?���6R���&�G����c�9G_	��9���=���i.���6�dpYm�BŖ۾�-MH����
              �@��,��P���F��5X���V.�A�T����?���<���h�t|K%��#�
�O�0�z6S�L  ��E#t��&��/�A�>�A���f�`��+cl�D��9�x�B1��RXOqǊU�  &+��3�J�~�c�0#��<5�?����e�*�;�_E������h�,�_�����Vq�
"e#�l��+:���߾j캾�i;��>�&�!;��~&��+��}7ā�&Ȼ�-k"!��k�N%��?���&OEaT�6�EC�tl�����,�-���A�[�             ��}�B#tOwa�ҩ��\�;��c;w��ye�%��v��K(X������eP�j	^�_H�c
                                                                                       ����@�$�����
                                                                                                   �ܕp�
㾔
  ��'P���Ra/��o�?Ќ���?�ru�bsI-Q��m�G׃=._�'������.���,tx�����
Դj'��+]!dl���r3��P�,ј��q�3iI(7ت�hڟ.�m�j_:XhS>�����hb�j�wB�T�|�$^c&��
                                                                    �ې�o1+��hP��w%�;e�꾨X��M�-B�ɈD�Y6�b�Ya����v:�g��>.�^���V��sG�i#F9�@;3A�!�g�[%ޝI}�$�[�dH����"fp����L3��I�A'����'M��5W06D�G�l��OY�֤�M���D�����`c�k�R�

           �>������^�`xZ���􋯙����4��H���mc1�g`��B��T+�I*i���ʲ7�	�W{K�����Ԭ���fd�+b����?4]l�>���T�"a��L5����R�-���⠭9������c���E,�c�b�"�?��T�C��ѹ�.Hw�+�⽙ߔZ.��/D-
                                                                                                                                                                -�m�~LA"J��s�������V��n�-����J�����I��/��7�{�8�r7�A�
         �n�;S_�#n��O�%��������`�ڂ��i���{�)�`Q�/�gpU��E�B$:���kj�q;�4��b5N�*�ew8���"u�zg�½��o��ʛ��f�	߾Mî2z�W���6��?x�
                                                                                                                        �Z�C�$l���XX��vo�x�������o��>�dNӳv<����6�z�Җ|�)�@�RJX�
                                                                                                                                                                              2woe}���1�-��d{RF��x�ҷ����8�xA/] !?h�H�)r��롚��`��s�[K�Ǔy��3o
����!</��	��%[�X�
                   O��\�{�X�{y/�-q�"���������}\uvn�W���'9�:
��Ca�hl�xodT`�0�d\'�i�s��	�>^��'���5	��I&���E�1�ti�e3W�=~��6Q�e�Y��@`@4.�Q
���븾����p%$������
_S�--�)�/�H�??X ��>����j~����ݼ�(
�d���/�5��@��m�f��Y)I��(�"��#�kFbp�ZV&���2��D_������y�(p�����A�pp{
                                      I�쏕�4sJ,|E?�IYt:�J����TLhY
                                                                 ��m��[;��/g���T���GE·�ioK
�x�����
       }n�7\��
              �c�隌K�sz�ʿ�E�ۡ.��2<��JD�v�!�L����������z����E�� �d3!*U��S�θ�b�����
                                                                                �����%3���ӛ�-��Tv@���*a�z;[|��,��e�\�).���zyR»E�[��]��-����\=����a}�
                                                                                                                                                    wL�p����e�m��گZ��HL�ia�K�.�5�sr�dI�&��%�u�cit
```
Here, we see that the output we get is not human readable and is in the form of some binary data.<br />
So, let's hexdump this file using the 'xxd' command:
```bash
bandit9@bandit:~$ xxd data.txt 
00000000: e078 40e0 d54e c25a b6a7 6da6 1c64 3f49  .x@..N.Z..m..d?I
00000010: fbfc 66ea 5948 31f3 b360 83b0 746d 20dc  ..f.YH1..`..tm .
00000020: d47f b7c1 1b44 4a9f d53c df92 6fe0 cbfe  .....DJ..<..o...
00000030: 838a 4779 ae71 3939 4285 4c8d 90ae b48f  ..Gy.q99B.L.....
00000040: e7f4 479f d3c7 482a f824 a883 ace2 d712  ..G...H*.$......
00000050: f766 38b9 984c 5dfb 2e18 cd94 7ec9 20dc  .f8..L].....~. .
00000060: dd8f a796 ab50 c31e 5ce8 82a1 f2d8 0043  .....P..\......C
00000070: 3a49 3548 c66f ec17 044b 8e91 c0bb 411c  :I5H.o...K....A.
00000080: f601 f4fb 0cb1 dc8e 39f6 e5d6 ff44 fb11  ........9....D..
00000090: da0b 9d3d e404 091a 5ee9 73cb f2ed 5244  ...=....^.s...RD
000000a0: e210 2713 a446 048c e0e1 0c38 ff49 6b43  ..'..F.....8.IkC
000000b0: 5fc3 7641 c819 68f0 6366 c853 a8e7 9ff3  _.vA..h.cf.S....
000000c0: fae5 0dc9 f505 d172 3246 7819 18e7 112d  .......r2Fx....-
000000d0: 036f 25c2 3ac0 2336 6a32 fae7 9f89 7712  .o%.:.#6j2....w.
000000e0: 82bb 18ea 1861 5924 94cb ac53 0f75 bd8f  .....aY$...S.u..
000000f0: 4a21 c616 c599 a2cf 7c91 38cb 4afb 53ca  J!......|.8.J.S.
00000100: 93a3 73e7 10c2 d0c7 f964 0570 6a43 6b43  ..s......d.pjCkC
00000110: a19c e0e4 e346 e4df bca2 a8df 1805 4708  .....F........G.
00000120: 1164 e28d e92d 2d5c 27f6 4d91 c27a da74  .d...--\'.M..z.t
00000130: 3885 692d 7d14 d263 59ec 25e9 bee7 3ed5  8.i-}..cY.%...>.
00000140: 303a 80e0 ac99 718d 07e5 08cb 0453 1da6  0:....q......S..
00000150: 18e0 626a 8003 cb22 8954 2464 8897 8747  ..bj...".T$d...G
00000160: fbcd 4efb 776d 5a97 45bc 0578 8e6a 85ac  ..N.wmZ.E..x.j..
00000170: 9521 5fe6 4e9f 537a c479 6a44 3c27 6023  .!_.N.Sz.yjD<'`#
00000180: c2aa 6453 3d35 d208 37a8 6099 4c25 a1e6  ..dS=5..7.`.L%..
00000190: 4cb2 abc6 03c1 cc2d 5bc8 84cd abd4 fc57  L......-[......W
000001a0: 495b b608 3ca2 1069 9620 3ba3 3d00 c826  I[..<..i. ;.=..&
000001b0: 8be2 c4c3 15b7 70f3 df12 448d f9b3 6b66  ......p...D...kf
000001c0: 1385 0ab6 77a1 31c7 0551 d0f2 76aa 305e  ....w.1..Q..v.0^
000001d0: 3df3 95bc 5208 63de 0428 c30a a7e0 b091  =...R.c..(......
000001e0: 6d0d 394a c25b 8abf 1d5b a51c 605e a1d9  m.9J.[...[..`^..
000001f0: c166 484b 22cd c406 310e 7944 4404 b1ea  .fHK"...1.yDD...
00000200: a08a 14c6 7106 949a 0cb1 4276 5b42 393b  ....q.....Bv[B9;
00000210: 1fd0 1adc 5a27 e27b 4e3f dc9a 6678 4c0c  ....Z'.{N?..fxL.
00000220: 6ce9 6ce1 f1ac 4746 5659 07e6 a9ac 3ae1  l.l...GFVY....:.
00000230: 3b17 7e2c 3ae0 a061 a156 c586 57d4 603d  ;.~,:..a.V..W.`=
00000240: c969 78e9 9b0c 6ceb 29a7 f3ae 2410 10c9  .ix...l.)...$...
00000250: 5596 fa83 64c5 c20a 4699 6aa5 3e04 477b  U...d...F.j.>.G{
00000260: ac28 1be6 9e89 905f 56e4 b72e bfe1 6ab1  .(....._V.....j.
00000270: 9666 bad7 3c93 d95b d607 6b2b 2742 5b38  .f..<..[..k+'B[8
00000280: 4b58 dabc ab3a ce1e 8486 e83a 3e11 0211  KX...:.....:>...
00000290: d7f8 8e00 1847 cd04 982a dab6 dd9c e78f  .....G...*......
000002a0: 26d9 fa38 5200 6cd3 35e4 ad03 6d8e 832c  &..8R.l.5...m..,
000002b0: 91e7 0e8d 77b0 5a94 7ece 6c8b e7b2 94ea  ....w.Z.~.l.....
000002c0: 74f5 9755 abf2 d500 1091 1420 b746 3897  t..U....... .F8.
000002d0: 2dbb 3540 1ab3 b531 aec3 688a be9d ec0b  -.5@...1..h.....
000002e0: 4450 c577 ab6f 1dea 4237 9823 b650 5849  DP.w.o..B7.#.PXI
000002f0: d225 1c3e d66c a8d9 1875 b391 27ff 2539  .%.>.l...u..'.%9
00000300: 9f67 4aea 3777 bc41 72be a71c ad3b 38ee  .gJ.7w.Ar....;8.
00000310: a68c b446 174b 1a69 9e2f 3394 84d2 2ed8  ...F.K.i./3.....
00000320: a528 3f90 29da dd84 82b9 a9fc 19b3 13e9  .(?.)...........
00000330: cb63 1b0d 8b32 a7a4 b94a 8090 b3c7 4c24  .c...2...J....L$
00000340: 27da 4fcf 9276 a813 d0bc 0355 3d41 0d70  '.O..v.....U=A.p
00000350: c04b 5bf0 56d5 aef7 cf8f f688 841c e22d  .K[.V..........-
00000360: 4909 2707 3913 154c 664c 7822 2a9f 180b  I.'.9..LfLx"*...
00000370: 15be 8d0b 1f4e fa2c 6e3a 2c69 19f3 98cb  .....N.,n:,i....
00000380: 30a8 f962 c188 751a 6314 badf 7551 d9b7  0..b..u.c...uQ..
00000390: 4b7a 7d47 e816 2eed e0ca d9e2 167f e5d8  Kz}G............
000003a0: a903 5f07 dd2e 452c 92ad f058 958c 8d2e  .._...E,...X....
000003b0: b74e cdf1 f56c 8714 3e23 34a4 c113 21c1  .N...l..>#4...!.
000003c0: e643 9c24 ff67 9b92 9d9c dba3 40b6 7e39  .C.$.g......@.~9
000003d0: c1e5 3eac c209 09e3 a7ad 8b14 7b13 cbb4  ..>.........{...
000003e0: 3b8d 697a ae01 bb5b a5e6 5ac7 6a71 b3d7  ;.iz...[..Z.jq..
000003f0: 8033 44c3 d213 2f9f b8bc 4b3a 91e1 56e6  .3D.../...K:..V.
00000400: 51b6 b4a8 de5e b510 eca8 7e47 bdf3 407d  Q....^....~G..@}
00000410: 1d38 6b38 a2e5 6695 86fc ba32 6b41 0408  .8k8..f....2kA..
00000420: d5d2 dfcb 4581 2eb9 d4ea 2da3 aef7 10d3  ....E.....-.....
00000430: 0ec8 466b d8fc 5d11 0271 4360 6328 d0d1  ..Fk..]..qC`c(..
00000440: 87a3 12b7 47dc c6ec c52b 4400 9973 7388  ....G....+D..ss.
00000450: 0463 10bc 8934 a366 7334 6cc8 5163 7e8e  .c...4.fs4l.Qc~.
00000460: bfad 663d 3d3d 3d3d 3d3d 3d3d 3d20 7468  ..f========== th
00000470: 654d 1f8d 90a7 e6b7 e5a3 336a 420b a53b  eM........3jB..;
00000480: e87b 2100 4b1d 232c 24fa 187a de31 108f  .{!.K.#,$..z.1..
00000490: 858f 5741 ae4c f9ef a2f7 ef23 e7f7 45f4  ..WA.L.....#..E.
000004a0: 5334 72cb ec36 f25a b733 15aa 3cb7 5fe2  S4r..6.Z.3..<._.
000004b0: 996e 1db6 e9c5 208c a0b1 39ba 452b 518b  .n.... ...9.E+Q.
000004c0: 8414 a39c fec3 10f7 2f2b acc5 7865 ac95  ......../+..xe..
000004d0: 59c7 732c 3c29 ddc2 981a 8c70 98dc bccd  Y.s,<).....p....
000004e0: 0daf f0eb 80d7 ca75 cab0 9d1a 3a41 d45d  .......u....:A.]
000004f0: 25e8 d5a0 4b49 ec3b aa2d 96d8 986b 1f4f  %...KI.;.-...k.O
00000500: 677d 05f7 9b7a f4f0 a111 15d1 9d67 1f9e  g}...z.......g..
00000510: 92c8 9b86 7f31 32f1 2c59 5ac2 7524 e2ab  .....12.,YZ.u$..
00000520: 6edc 2cce eace d52d 1426 1f11 6439 63e8  n.,....-.&..d9c.
00000530: c35f 295a af7c 4dbe 0302 be0b b07b 6f83  ._)Z.|M......{o.
00000540: 9d49 42bd c424 b268 7b57 da4e 682d d0bc  .IB..$.h{W.Nh-..
00000550: e481 bd5b 900b e3c3 4767 5941 b7fc ac40  ...[....GgYA...@
00000560: 0259 62b7 b8fe 10bc 07c6 0d25 623e 3c34  .Yb........%b><4
00000570: e969 d884 6856 ff69 9350 9b20 a482 3aeb  .i..hV.i.P. ..:.
00000580: e7d9 9831 a66d 0e23 d484 1ac4 12ef bdbd  ...1.m.#........
00000590: 93ba 20b3 d03b 0f58 7c8a 5ded 18b5 de5f  .. ..;.X|.]...._
000005a0: 5cd9 888a c015 06e7 23a4 38b8 4a44 6d2e  \.......#.8.JDm.
000005b0: eabe cbce 9ad6 aafa cc11 d739 d682 3818  ...........9..8.
000005c0: dc8b 47f4 7749 f18e 62db 8a2d 97e7 b2d1  ..G.wI..b..-....
000005d0: 764c 87ab a9b2 9bee 6b77 9819 5fe2 d8f4  vL......kw.._...
000005e0: ccff 3477 be99 f409 ca2a 9da5 d68f 7c2a  ..4w.....*....|*
000005f0: 4bb9 a562 01f6 8356 9471 50ab 20eb c426  K..b...V.qP. ..&
00000600: 5182 ac29 00d9 ae27 6c0d b184 ee7a 2fc1  Q..)...'l....z/.
00000610: 232f d238 0526 3e4e ff61 5147 fc6d 7670  #/.8.&>N.aQG.mvp
00000620: e387 e33c 6bbf ecac 5bfa 2afb b8d8 054b  ...<k...[.*....K
00000630: 3f33 7fe9 3459 e7c0 2f81 7f72 c067 279e  ?3..4Y../..r.g'.
00000640: a7ae ad99 76d4 a018 e9e6 2e32 9637 cc5d  ....v......2.7.]
00000650: 3ba8 2fca c31e e0d1 7f9e 0997 3dc9 98b8  ;./.........=...
00000660: d66d c930 4dc8 4817 aa98 47a3 2c20 d521  .m.0M.H...G., .!
00000670: 7a86 daee b9b2 dc93 1fd8 5a4b f3a1 bba2  z.........ZK....
00000680: 200c 1e00 de22 486d 7af7 536a 6025 597c   ...."Hmz.Sj`%Y|
00000690: 101d e575 0bbe b57a 99e1 fd62 3a5c 86ae  ...u...z...b:\..
000006a0: e6d7 f290 ac5c 8145 9228 062c 1be4 9412  .....\.E.(.,....
000006b0: 4fdc 04a0 649a 322f ff4a 3006 7359 4109  O...d.2/.J0.sYA.
000006c0: 8678 d176 2be5 e4b6 faab e656 f371 96e2  .x.v+......V.q..
000006d0: 3b0d a18b 98a4 3fd5 e655 44d2 4069 d959  ;.....?..UD.@i.Y
000006e0: 0b4b d086 5a1d f7c0 8bc6 c271 596d 0645  .K..Z......qYm.E
000006f0: 131e eff2 32fe 9d5e 3737 2706 70e9 1551  ....2..^77'.p..Q
00000700: 310b 17ae b1f5 285d 375f 8bd4 2751 4f34  1.....(]7_..'QO4
00000710: 0509 8b86 d83e befd 6f0b c7bd edd9 d255  .....>..o......U
00000720: 7f5a aa36 14a0 d1f7 49eb 8870 35c4 10c8  .Z.6....I..p5...
00000730: a5cc f177 9f9e 4d9a 9c72 0421 6fc7 971e  ...w..M..r.!o...
00000740: 92d3 4621 8d51 cf55 b1c8 9d90 af1a 7cf5  ..F!.Q.U......|.
00000750: 1e5f fee8 8b9b 56ef f16d 6b3d 02be e999  ._....V..mk=....
00000760: 22b6 96da d20d ae6e 6bce 9e36 419b 0e76  "......nk..6A..v
00000770: b346 290b e930 f0c3 6bab 47be ed58 2ba5  .F)..0..k.G..X+.
00000780: 9923 8b9a f05d fb1b 6259 8402 dcd7 5bef  .#...]..bY....[.
00000790: f6b6 2461 7360 52e1 9ddf 7379 4a80 0b62  ..$as`R...syJ..b
000007a0: a569 2954 653c 0ec8 a83c b26d 545a 6393  .i)Te<...<.mTZc.
000007b0: 7c58 945f acca 01fd 741f 9971 f505 8418  |X._....t..q....
000007c0: 99b2 1653 92d3 d5e9 7752 8044 a31f a8ca  ...S....wR.D....
000007d0: 31b5 c6f7 2578 d2f0 6b2f 4724 9802 fcf1  1...%x..k/G$....
000007e0: 0864 4a8a c58c 024b a0d0 4c2b d946 1b91  .dJ....K..L+.F..
000007f0: d358 4d52 5cab cd4d 3b74 eb9f d326 f00e  .XMR\..M;t...&..
00000800: ba71 1917 245b ab2f 4ba3 aabe 76ba bdff  .q..$[./K...v...
00000810: 6330 6d52 ad73 edeb 44cc 6999 ef2b 9e79  c0mR.s..D.i..+.y
00000820: 0119 cf03 5b2a fa0c ac13 ea53 b230 8aee  ....[*.....S.0..
00000830: b52d 549c 8600 c9f0 d641 9dd2 5738 fd88  .-T......A..W8..
00000840: f791 4d1d f0d3 fae2 284b a8bd 996f 1aee  ..M.....(K...o..
00000850: cb88 1c2c b664 f709 7cae 9d5b e1e9 02b2  ...,.d..|..[....
00000860: e70b 9cd8 56b6 948b 9c45 c98d c769 3692  ....V....E...i6.
00000870: 6055 cdb7 15a3 92c5 a3c2 b5bb a21e b6e2  `U..............
00000880: e244 906d 81d5 cf76 2e20 e9c6 8fc0 58d7  .D.m...v. ....X.
00000890: 7aa5 632f 6610 39e4 bba3 6bbb cb17 f49b  z.c/f.9...k.....
000008a0: dd29 4bea 2cbb 9b7e 495c 1055 3015 66c0  .)K.,..~I\.U0.f.
000008b0: c8f3 69e6 1c63 93e1 e6a9 7c47 dd7a 345b  ..i..c....|G.z4[
000008c0: 5813 c934 1b29 1d76 894a aa23 ec93 7321  X..4.).v.J.#..s!
000008d0: c706 c192 1c2f 3b6d 8b5d 5384 8d1a 9227  ...../;m.]S....'
000008e0: 484f e3fc 2d4b 2943 faf4 9525 1c73 0200  HO..-K)C...%.s..
000008f0: 312d fa58 6548 956e f432 07a3 e403 4e48  1-.XeH.n.2....NH
00000900: af62 43b4 4971 ecbb 1409 e2f3 66fa 8391  .bC.Iq......f...
00000910: d726 e538 2d3d a535 84e6 bf00 a3c2 a363  .&.8-=.5.......c
00000920: 102a e65c b99c 31c8 4eaa 7a32 27f5 de3c  .*.\..1.N.z2'..<
00000930: e9fe 1915 e555 1310 1773 5fa3 79eb 6ba6  .....U...s_.y.k.
00000940: c723 10c3 24a0 c390 007c da31 b80d dbee  .#..$....|.1....
00000950: e8e7 3ccf 4ee6 ea5b d5a5 0fc4 43e5 1409  ..<.N..[....C...
00000960: 4102 48b7 aaf4 649f 2f87 c129 0c8f ea92  A.H...d./..)....
00000970: 4772 0fd2 9944 d1e8 38ff 334d df86 1251  Gr...D..8.3M...Q
00000980: a103 c003 46d9 760d 1f44 9871 f56a 76d2  ....F.v..D.q.jv.
00000990: 88d5 16ec 7bde d585 b246 5d90 b098 4463  ....{....F]...Dc
000009a0: 789e 3ced 23d7 ab6f 24bc 23a4 d27f f971  x.<.#..o$.#....q
000009b0: da8b cbe1 50b1 2d2e fc43 d737 1ec0 53be  ....P.-..C.7..S.
000009c0: 4074 91a8 4a6c 6f1d 429c dab7 50cf 9c36  @t..Jlo.B...P..6
000009d0: 7aa4 6431 ed7f eb18 4b16 6d70 2ae6 5102  z.d1....K.mp*.Q.
000009e0: 0fb1 fc80 78c5 1e78 884c 239c 9ffe 3ad5  ....x..x.L#...:.
000009f0: 4f85 e644 b113 fbc4 7cfe cc5f 15aa 3df4  O..D....|.._..=.
00000a00: baab 9faa cf4c 9c77 c014 e4d0 9718 ddf5  .....L.w........
00000a10: d223 4985 a58a 54b6 75fe 0cd5 4a7f 500e  .#I...T.u...J.P.
00000a20: c67f 3180 3688 1581 9a2c 7538 1357 186f  ..1.6....,u8.W.o
00000a30: 24bf 81a4 b3c4 67ca 6021 f301 76fb fcc4  $.....g.`!..v...
00000a40: 1d2a 4abf 0276 efaf 2b07 6366 8af2 9efc  .*J..v..+.cf....
00000a50: a9fa 3007 13d7 238e 77cc 6d76 6878 cee9  ..0...#.w.mvhx..
00000a60: f306 2726 8d9c 7db4 f467 8c8a 157a 10bf  ..'&..}..g...z..
00000a70: 7809 895b f409 f22e 9374 b529 1d1a 8bf0  x..[.....t.)....
00000a80: ee83 831e 4a54 210b 9289 8515 dd65 94d8  ....JT!......e..
00000a90: 205c 01f8 1c46 94b0 fc0d 3058 c889 edae   \...F....0X....
00000aa0: ba46 bd6b 9457 594c 6085 8476 0165 26b1  .F.k.WYL`..v.e&.
00000ab0: 20c7 7203 f02b 0387 9db7 941d 8ce4 3441   .r..+........4A
00000ac0: 2d98 3d26 f8c6 1518 2573 4910 74cd 74e5  -.=&....%sI.t.t.
00000ad0: 23cd 619d 9650 0dc3 ad52 e32e f5da 8a85  #.a..P...R......
00000ae0: cef4 6d30 4333 ce48 8732 cc3f 7394 a5d7  ..m0C3.H.2.?s...
00000af0: c43a a860 1cca 4ec3 3c2a e9c4 b8ea 6fb2  .:.`..N.<*....o.
00000b00: d895 0ae2 7e78 ca2d 7c2a d72a 2325 4aa0  ....~x.-|*.*#%J.
00000b10: 4ac7 f3da 3e73 75ec 2b67 d778 e7a3 b578  J...>su.+g.x...x
00000b20: 90d4 aa2f f48b 08ed bacc 014c e523 f438  .../.......L.#.8
00000b30: 61f2 cae8 bda1 5d05 4ecf a3cb 0db6 c4c7  a.....].N.......
00000b40: 9736 69d5 3a97 a803 908f c8ff a697 387a  .6i.:.........8z
00000b50: 44e0 2efa 23ef e7e7 4888 f55c daf6 a535  D...#...H..\...5
00000b60: 7f5e 3f76 29ee 4acf 9969 c338 4080 b4f6  .^?v).J..i.8@...
00000b70: ab90 b8a0 c8be a7f6 a6d5 e76b 2e32 7eed  ...........k.2~.
00000b80: eb17 e3aa a551 be7e fb48 c80a 01d5 2f5d  .....Q.~.H..../]
00000b90: 2fec 4194 c2a1 e8d2 d7e7 0193 1883 5068  /.A...........Ph
00000ba0: ca15 5bcc 3d27 a96b 7fd5 525d ab74 b145  ..[.='.k..R].t.E
00000bb0: f295 bd5c d234 4821 d172 9b4b cbde bc37  ...\.4H!.r.K...7
00000bc0: 40c4 f3ee 59f5 ff99 88d5 8067 d59b 0e3b  @...Y......g...;
00000bd0: 9da1 c962 d72f 3384 7f57 760f 9761 9441  ...b./3..Wv..a.A
00000be0: c09e 5084 8f78 d888 78ed 7783 d87e 67ac  ..P..x..x.w..~g.
00000bf0: 3497 c8cc de0a 3dce 9e73 b7ba 4d2d 2263  4.....=..s..M-"c
00000c00: ebc4 b10e 912f adac 2762 e02a d259 0c91  ...../..'b.*.Y..
00000c10: 8fe4 ebdd e602 8594 f7e6 7c8d c7a1 8c38  ..........|....8
00000c20: c6a2 34b3 ffbd d747 3d98 58b6 3d02 f4ad  ..4....G=.X.=...
00000c30: 9c38 7ea9 6496 2391 3278 2a8b 1dee ac0f  .8~.d.#.2x*.....
00000c40: 830a 49c5 ad86 79ac a1d7 ee73 bdbd fa1a  ..I...y....s....
00000c50: a824 4f48 aa43 4824 b74f d0a0 f862 12cf  .$OH.CH$.O...b..
00000c60: e8ba e3b5 7ea4 488b 3d58 654f 680c fbd1  ....~.H.=XeOh...
00000c70: 2237 2b93 cac5 6271 a59f 07c1 5639 01e7  "7+...bq....V9..
00000c80: d57c 40db 0972 ac84 9009 0d68 3ffb 41b1  .|@..r.....h?.A.
00000c90: aed0 c1a1 987c b5b6 7fdd 5398 67ab 2f44  .....|....S.g./D
00000ca0: 3865 9fd4 bf4f a156 6aa5 05c3 aa7a e9a8  8e...O.Vj....z..
00000cb0: fc3d 0b3a 71b9 2287 025a 7a00 67ef d0dc  .=.:q."..Zz.g...
00000cc0: 0489 49c4 779c afa0 2fc3 a51a 4ceb 1fe1  ..I.w.../...L...
00000cd0: 965c 83f9 8bef bc47 ee2d 60e8 91c4 23a0  .\.....G.-`...#.
00000ce0: 2d31 6d0c 8c0e 3906 7de1 ea10 e2f8 f21f  -1m...9.}.......
00000cf0: e7d9 c48e 9b66 0896 8d5b 8ac9 2718 2d3c  .....f...[..'.-<
00000d00: 2731 35d9 453c d62e 72ec 5831 515c 9e75  '15.E<..r.X1Q\.u
00000d10: 8863 2843 9ddb 85f3 2c51 2aba e00f 4e9a  .c(C....,Q*...N.
00000d20: 2bcf 6a4c 1e3e 9136 19b6 3d76 6260 8f15  +.jL.>.6..=vb`..
00000d30: 7c63 573b 6365 9bf6 db88 01bf 84af 9d3f  |cW;ce.........?
00000d40: 6797 d0da 2deb 95d7 bbe2 5afb 4687 4f21  g...-.....Z.F.O!
00000d50: 196c c233 6333 bbce c7cc 8b4d 781e c7b3  .l.3c3.....Mx...
00000d60: bef4 dbef 6122 2f71 1d59 a681 669c 446b  ....a"/q.Y..f.Dk
00000d70: dc4c 2f52 83ee c65c b543 9f97 922f ecef  .L/R...\.C.../..
00000d80: b3ef 4b7e 997b ca08 96b8 6599 6e4a 1410  ..K~.{....e.nJ..
00000d90: 0006 fdd8 c8cc e1bc 71a6 f33b 82a9 1c6f  ........q..;...o
00000da0: e73c 4c24 593b 38cd 9b07 ac27 04ed 68a6  .<L$Y;8....'..h.
00000db0: 58d6 663f 744b d23f a41c 1ac6 e452 4c35  X.f?tK.?.....RL5
00000dc0: 9ef7 2e5f c1d7 a74f e794 a398 91e9 b164  ..._...O.......d
00000dd0: 76a3 c7c9 5531 de17 e115 8d9c 3615 63db  v...U1......6.c.
00000de0: d7f3 4dbc a767 bc87 63b5 e123 3ab6 f740  ..M..g..c..#:..@
00000df0: 6005 4972 55b0 61a8 bec8 4a5b 7001 b9e8  `.IrU.a...J[p...
00000e00: b982 90d3 0b6f 9856 cf3c fe65 5a0d 38ab  .....o.V.<.eZ.8.
00000e10: 6822 0233 4964 8cf7 b584 2fc2 8b09 0352  h".3Id..../....R
00000e20: 5399 9ab1 97b9 d0aa a2ac 6a58 7aed 9162  S.........jXz..b
00000e30: e44c f61d 4f50 3f66 76c0 deeb 6e39 5408  .L..OP?fv...n9T.
00000e40: 8996 b231 1d34 f7a8 c5b0 58d6 3e6f 0c99  ...1.4....X.>o..
00000e50: e090 47cc 9fd1 8d45 4535 3f55 7ccb d478  ..G....EE5?U|..x
00000e60: e1d4 7000 baa9 c1ff 0f13 277d ac9e 3333  ..p.......'}..33
00000e70: 9a5f fcf6 4cee 1808 68d6 65af c495 5870  ._..L...h.e...Xp
00000e80: e49d d837 e16f 40b3 beac f26d eff8 4666  ...7.o@....m..Ff
00000e90: ed5e 4502 0b39 593c 8a83 5207 b272 9416  .^E..9Y<..R..r..
00000ea0: 87c0 7b2a ec70 e43c b3b6 9917 04a2 f9ee  ..{*.p.<........
00000eb0: 22a5 b814 3c18 c5e8 4be3 111b d8de 1d19  "...<...K.......
00000ec0: 1981 9ea8 3e4c 411d 0d87 e85f 7838 40ee  ....>LA...._x8@.
00000ed0: c50d bfc7 5879 55c5 5820 e8be bfa3 6263  ....XyU.X ....bc
00000ee0: c453 328c 4c72 48f5 0025 e737 3182 1319  .S2.LrH..%.71...
00000ef0: 7021 62d3 a903 86a6 5321 4fe8 0537 3fe0  p!b.....S!O..7?.
00000f00: 14c3 01ce b40c a964 f50d f713 36d2 6253  .......d....6.bS
00000f10: ed24 f7d6 c9e3 109c 49aa 16e9 40eb 5056  .$......I...@.PV
00000f20: 9eeb c920 f541 8ac1 4064 3b58 27b6 4d02  ... .A..@d;X'.M.
00000f30: 8c13 9764 2ac5 c76f 9864 aeae 852e 321f  ...d*..o.d....2.
00000f40: fa82 5507 f74e ee3c 73ed 1535 233e 5e10  ..U..N.<s..5#>^.
00000f50: 00e0 2efa 6045 d87f a562 301a 01f3 b895  ....`E...b0.....
00000f60: e08d ee4f b411 5d8a e785 3c8c 499c 729f  ...O..]...<.I.r.
00000f70: ae75 9995 e7a4 87f1 04ff 4b09 5714 1099  .u........K.W...
00000f80: caac b0d7 a1c0 785f dee6 2fc2 ee8f d129  ......x_../....)
00000f90: 016c f3e3 c402 49ca f5d9 d0f5 b604 fecd  .l....I.........
00000fa0: 4219 db1c 154c 9eab 60bd 8dc1 2ab1 5b30  B....L..`...*.[0
00000fb0: 8b9f 854c dd55 9f2e dc73 f1b0 b8ed 78ec  ...L.U...s....x.
00000fc0: b51e 0736 012f 957b d177 9e43 6fb4 2c1e  ...6./.{.w.Co.,.
00000fd0: 3c42 f489 1edb 87e4 91b5 52ee 6e5f bbf0  <B........R.n_..
00000fe0: d044 d507 8b65 db51 abe7 0df9 8634 a594  .D...e.Q.....4..
00000ff0: 3f27 abcc e64e 61ee e7b4 8c7d d42a bee2  ?'...Na....}.*..
00001000: 3e29 3ecf db4b bab6 37a0 ef37 806b 1e7b  >)>..K..7..7.k.{
00001010: 6b7f 9e4b 521c fc07 2ba7 62ed 35a9 e324  k..KR...+.b.5..$
00001020: 8b98 6943 ac7b 8e9b 1e21 77d8 7741 b4ea  ..iC.{...!w.wA..
00001030: a92f 96d3 59f4 513f c86b 1a97 d875 fde1  ./..Y.Q?.k...u..
00001040: f89e ffe2 8ab4 9b7b 1610 81d0 551c 9395  .......{....U...
00001050: 4101 5e59 ffee 92cf 9607 41b7 fd46 9a77  A.^Y......A..F.w
00001060: 2582 108b 5083 236f 29b8 9541 9655 e1e5  %...P.#o)..A.U..
00001070: 92c5 3a95 c41f e8d3 7732 4de3 ef6f 32df  ..:.....w2M..o2.
00001080: 0a6d 8bb7 c9c3 42a2 4974 bfd6 d18b a456  .m....B.It.....V
00001090: 7339 e8a1 5c52 e30d dd55 a732 110e a8b1  s9..\R...U.2....
000010a0: 9dbf 9a73 578b 9ba2 88bb 004b d8fa 6ea7  ...sW......K..n.
000010b0: 2e78 ac2d 2815 ccbf b759 d68e 5d3a 8b61  .x.-(....Y..]:.a
000010c0: c6cc 9c48 5c3e e063 a96c 1c18 5067 1e20  ...H\>.c.l..Pg. 
000010d0: e5c6 4150 bd0a 0bcc e2d8 b734 2551 7a31  ..AP.......4%Qz1
000010e0: f213 8c1f f36b 5222 f9b6 0306 56b9 7c97  .....kR"....V.|.
000010f0: 89cd a719 2739 84d0 b08e 77b0 1601 ac1a  ....'9....w.....
00001100: ae88 ee9e 902f 7685 41c6 a6bf 50a5 fc39  ...../v.A...P..9
00001110: 6cfa 2b81 8dd4 6bf0 b4ca a89a 8050 96fc  l.+...k......P..
00001120: 538d 7990 8145 7557 da23 164f 9623 0bb4  S.y..EuW.#.O.#..
00001130: 42db 7f88 349c 358a 4e3a 0e95 d030 ec77  B...4.5.N:...0.w
00001140: 1d3d 09b0 b198 5f0a 5da5 66a0 94f1 35ca  .=...._.].f...5.
00001150: 11e5 61b7 a1ff a832 b2f1 fa0b 189a da52  ..a....2.......R
00001160: 141f c1c0 4a9c 005b 2684 d6d3 36a7 75fd  ....J..[&...6.u.
00001170: 9857 294b d36d 39a7 afb4 b9ca a2fd e959  .W)K.m9........Y
00001180: 6d01 dd78 ff73 dd2b 6bf1 ec80 e923 ded9  m..x.s.+k....#..
00001190: e95d 58ce 47b8 1f7d d6ef 4550 e4bb 0360  .]X.G..}..EP...`
000011a0: 3931 dab5 b0de 2722 99f4 e18d e242 d598  91....'".....B..
000011b0: 6e4b e54e f0ed 2576 6684 272b f3de 195a  nK.N..%vf.'+...Z
000011c0: 7428 b95a 3954 9e0d 616c f38a 40be d2c6  t(.Z9T..al..@...
000011d0: 4e46 3e00 8df8 0f4e 7f5e 2866 9e32 a0f1  NF>....N.^(f.2..
000011e0: 8f45 e269 7350 d5bf dccc e425 cd1b 44c5  .E.isP.....%..D.
000011f0: 04ad 8fe7 7581 8a17 fdfb f113 a812 3f3c  ....u.........?<
00001200: f113 4468 91e3 a084 b6e5 f5d5 9de9 98b0  ..Dh............
00001210: aa2c 7e5c eedf 4c78 09b5 5bf7 e211 3cc6  .,~\..Lx..[...<.
00001220: 93ac a9fe de52 e506 e6fe 1f2f 6a5d eba2  .....R...../j]..
00001230: 77d6 6dbe 3e17 4c36 0ed5 ddf9 d408 3e0a  w.m.>.L6......>.
00001240: 0b62 f6b6 a727 6c50 8b31 42bc 6436 84c1  .b...'lP.1B.d6..
00001250: 331c b33d 0fb2 de4c ac74 8077 0d45 f261  3..=...L.t.w.E.a
00001260: c56f 5179 fb3a 8f67 7ccf cb0f 42f9 ab39  .oQy.:.g|...B..9
00001270: 396c 52f2 6ad3 5e72 97d1 53ff 4309 9fac  9lR.j.^r..S.C...
00001280: c530 a4c3 72ff 5973 ffbf 61da e28d dc52  .0..r.Ys..a....R
00001290: 9dd0 495a c3fc 79e0 1be7 1b25 4982 e370  ..IZ..y....%I..p
000012a0: a32a eb3c e1b5 3a0c cf3a 5a97 aa67 ac6d  .*.<..:..:Z..g.m
000012b0: b9c3 6169 7783 f19e 58ca 680c e5c9 8a7a  ..aiw...X.h....z
000012c0: 4d79 e120 701d c714 b51e 1557 abc1 788b  My. p......W..x.
000012d0: ba9b e4b2 4b30 bff4 62e1 956f 7aa0 1902  ....K0..b..oz...
000012e0: 83a5 4030 ff14 6d28 18b3 6719 1af8 e24f  ..@0..m(..g....O
000012f0: 3d4e 7199 3b92 9f6f 1eed cee7 fdf5 46d3  =Nq.;..o......F.
00001300: 2020 33e0 eae3 6370 4dc0 933c 62ce 4fce    3...cpM..<b.O.
00001310: d422 3f82 5860 1289 605b f461 416b b9b5  ."?.X`..`[.aAk..
00001320: e3a0 2487 1ded c609 97b6 196c 73b1 f6d3  ..$........ls...
00001330: a24a 29e7 f73e 0b86 3ebf 0829 3964 c33e  .J)..>..>..)9d.>
00001340: ac7e 18bd e170 04b9 dc6b 8087 12a3 7842  .~...p...k....xB
00001350: 5598 5079 8066 820b ae6d 690b 91cd 5be5  U.Py.f...mi...[.
00001360: 7b03 e7f2 672d 7054 2cc2 7bae da13 3d86  {...g-pT,.{...=.
00001370: 20d6 8237 a1b1 3507 8f74 c941 daa3 75eb   ..7..5..t.A..u.
00001380: fed2 e3a2 225d b866 1409 032f c8bb c60e  ...."].f.../....
00001390: 8643 24ab d59d ca84 b923 30eb 70d4 43f0  .C$......#0.p.C.
000013a0: a1b8 b511 9105 4f79 e91c 1e6e 9b31 8e18  ......Oy...n.1..
000013b0: 2254 bdf0 cbbd 9f3b d6fa d88f 7b66 560d  "T.....;....{fV.
000013c0: eb55 70c5 1c0c e558 84e4 a816 bec2 1bca  .Up....X........
000013d0: 3660 1808 3d49 3661 9dba c368 6cec 0166  6`..=I6a...hl..f
000013e0: b463 b352 8f72 3238 77fc 2fed e4b5 c33b  .c.R.r28w./....;
000013f0: 71ec 947c 2abd 0169 9657 c146 2e30 bd38  q..|*..i.W.F.0.8
00001400: 3d6a a1ab a8a8 b77c e66d 4ed5 6095 3a38  =j.....|.mN.`.:8
00001410: 0894 4e28 d274 f76d 6829 e59f da94 7490  ..N(.t.mh)....t.
00001420: f6ba 2d66 a2a6 dda5 b469 c23b 85a3 b2bc  ..-f.....i.;....
00001430: 000f 35e9 c24c e8bd 645d af5b 1d07 0ba7  ..5..L..d].[....
00001440: 5c44 6752 e1d5 44dc 8e64 386c d90a 59d4  \DgR..D..d8l..Y.
00001450: 3b0c 3e13 31b6 5a1e fcc6 7a75 e325 28e5  ;.>.1.Z...zu.%(.
00001460: dbe8 d7aa e13d 9cd4 7bf1 9704 5fe3 8dba  .....=..{..._...
00001470: ba3a 2250 5e16 140a 2e91 e6f6 988e cbfe  .:"P^...........
00001480: cfe8 23f0 2ea4 1071 0374 f634 7a66 bc13  ..#....q.t.4zf..
00001490: 5b36 e507 448d 597f bad4 8253 3baa 0b41  [6..D.Y....S;..A
000014a0: 7c39 7745 a7f4 a35b 52ca d75e 8e3d 3d3d  |9wE...[R..^.===
000014b0: 3d3d 3d3d 3d3d 3d20 7061 7373 776f 7264  ======= password
000014c0: cfa7 9f87 602b c87b f030 14eb beb1 275e  ....`+.{.0....'^
000014d0: 0b60 a6ed d9b4 2a14 768c 57a7 3d0e 4ef9  .`....*.v.W.=.N.
000014e0: 296a 3b53 327b bf4c eafb c792 e148 5b2f  )j;S2{.L.....H[/
000014f0: af7c 8971 24dd ca04 281c aced d881 2454  .|.q$...(.....$T
00001500: 56ff b127 5aa3 dbfb 57aa a52e f4b6 5d7e  V..'Z...W.....]~
00001510: 6db9 48eb db00 c0fe 05da 63f7 b433 f4e6  m.H.......c..3..
00001520: a854 87ba 72b3 d941 6aaa 6043 f29e 7ab6  .T..r..Aj.`C..z.
00001530: 2ebe 1b8a 0185 2f74 ad9e 046e 2920 93f2  ....../t...n) ..
00001540: d87e 5a5e ab74 1d95 8dff f8ba d406 ea6d  .~Z^.t.........m
00001550: 996d 93a3 f980 43f0 cf5f 5ea8 2c31 0ee2  .m....C.._^.,1..
00001560: 040c 59b2 e50b dc49 6112 c9de 9396 0cd7  ..Y....Ia.......
00001570: bada b06c e3da aaf6 5ccb 5754 978e 1c51  ...l....\.WT...Q
00001580: 54e5 5e31 cbe2 d30b 06a3 c66d 81c7 d159  T.^1.......m...Y
00001590: 1171 81cc c64e 492f b9ce 9694 374a 8ed4  .q...NI/....7J..
000015a0: 024c e678 5b34 46b5 87a1 a0d3 28e5 85ab  .L.x[4F.....(...
000015b0: 05de 1a55 7bd1 5554 88a1 c62d 8250 fe4d  ...U{.UT...-.P.M
000015c0: 8773 2404 7a5f 361b e6a4 81b9 085e 45a1  .s$.z_6......^E.
000015d0: a757 f23e 0387 b117 cd46 beb8 4ff3 bef8  .W.>.....F..O...
000015e0: 6a81 b54b 2153 9903 4d01 e5a0 62bb b20d  j..K!S..M...b...
000015f0: a71d d304 38b0 a376 3a09 4246 3654 2280  ....8..v:.BF6T".
00001600: 2fe1 03ef 3229 a950 9da3 e837 0156 93f4  /...2).P...7.V..
00001610: 4d7e 4356 785f 27c3 c8b0 426b 53c9 4590  M~CVx_'...BkS.E.
00001620: 4c63 d6ad 3ce8 3622 390f daad 7202 230b  Lc..<.6"9...r.#.
00001630: d86a e131 aca4 3b0b dbdd f4a8 fe58 747b  .j.1..;......Xt{
00001640: b25f 6029 be37 a9b7 a455 8c7a aed3 2ca0  ._`).7...U.z..,.
00001650: 1172 3b7a ed22 ca5f 4921 a057 5b96 d8bb  .r;z."._I!.W[...
00001660: 9c2f 6ea7 0393 44b1 6b01 c08b b2ab 528b  ./n...D.k.....R.
00001670: f06f c3d6 bce6 3830 c7c0 591e 0ad8 c32b  .o....80..Y....+
00001680: 43de 453f ed9c 5981 04b6 f1c9 af23 88f8  C.E?..Y......#..
00001690: d20b fea2 2a15 8ef9 c86e 1af0 2949 6425  ....*....n..)Id%
000016a0: 7359 62d9 475e 6102 4a17 1edf 90e9 0fda  sYb.G^a.J.......
000016b0: c971 7ebe 1ef2 2f3f 87c0 330b e8a2 8ac0  .q~.../?..3.....
000016c0: 39d6 d84e 7281 a44b 0425 b20f e03f 6806  9..Nr..K.%...?h.
000016d0: 90e8 deff 0d74 31f4 06f7 15b6 3801 009a  .....t1.....8...
000016e0: 781f ad7b f61b 8098 4be4 65e6 10bf 9db5  x..{....K.e.....
000016f0: 667c fb55 ca5b 0c15 29b3 4dbd 00f0 f6c8  f|.U.[..).M.....
00001700: d479 742d b4f1 f007 153f ab00 0cca 2663  .yt-.....?....&c
00001710: 3094 f2ec db00 aa8f 0bd7 d171 b92b 7a95  0..........q.+z.
00001720: 6ca9 44e2 1590 7143 20ae 5668 3ad9 3f82  l.D...qC .Vh:.?.
00001730: 366c 2623 d518 e59a cf89 8e1a 4664 26e0  6l&#........Fd&.
00001740: 2f82 7841 4e4d d7ff 8c65 9339 1384 d555  /.xANM...e.9...U
00001750: 8a22 c579 e11d fd22 4ec4 44bc a999 07fc  .".y..."N.D.....
00001760: 8064 5745 3801 5abe 8bee 9f2d f0eb 63fe  .dWE8.Z....-..c.
00001770: 6e0b 86ca fdc2 93ff 89f6 e3d6 a157 bb38  n............W.8
00001780: 67eb 565d 0ee2 61f1 74b0 1649 7f31 ffc9  g.V]..a.t..I.1..
00001790: 2d59 9a60 2229 f5cc b21f f2a5 b2f4 040f  -Y.`")..........
000017a0: 004c de9d 2f24 6928 ff2f 911c 4719 6116  .L../$i(./..G.a.
000017b0: 7385 0547 b850 f8c9 e95f ab9b 2430 608e  s..G.P..._..$0`.
000017c0: bc1a c95d caf6 791a 4a35 83cd 79c5 7675  ...]..y.J5..y.vu
000017d0: 737e 20c1 522d f336 bb21 9b6d 33ca e950  s~ .R-.6.!.m3..P
000017e0: 1d71 ece4 3677 36aa a516 58e9 fb00 eaa9  .q..6w6...X.....
000017f0: 5468 788a 86ad 16ed 9370 e22d 3c9e 601c  Thx......p.-<.`.
00001800: 4778 f524 2fd0 d8ad 27d5 f207 a210 2419  Gx.$/...'.....$.
00001810: 907b 9d28 691e 8934 82f0 d51d 3f72 8108  .{.(i..4....?r..
00001820: 3018 a3db 6163 c4e7 2c1d 388d fc8a 3a1f  0...ac..,.8...:.
00001830: 5240 2d74 dcb3 769c 866d ba60 26d7 f817  R@-t..v..m.`&...
00001840: 05fc 7081 5b15 3605 8dc9 cbf5 422e 656b  ..p.[.6.....B.ek
00001850: 0ab0 b723 c4c2 236b d6a3 2bb2 cadb a239  ...#..#k..+....9
00001860: 87e4 a695 5aad 7a0b 759e 17c4 71c4 ef6c  ....Z.z.u...q..l
00001870: 6f03 8321 09b6 e2ee add6 fb17 08d5 f52a  o..!...........*
00001880: ac3e b1f1 7657 5983 a0d0 c56b be6f c464  .>..vWY....k.o.d
00001890: 3a56 7987 6d60 69f9 5972 36ba ea09 6c10  :Vy.m`i.Yr6...l.
000018a0: 5ce1 d5d5 aeed b455 22d0 d743 d10e bc77  \......U"..C...w
000018b0: 56fc 91c2 155c 505d 4eeb 9d2f ad5d 9b5e  V....\P]N../.].^
000018c0: 8de8 3367 4ae9 733b c747 093c 17b4 68f3  ..3gJ.s;.G.<..h.
000018d0: 41c0 53f0 1c43 75b4 a6b7 1ec7 6eec f27c  A.S..Cu.....n..|
000018e0: 9da4 2617 a2b5 4cee 4327 5f5d a75a 4187  ..&...L.C'_].ZA.
000018f0: a213 40ee 0d9a d23e 02e0 b2b0 f5c2 885f  ..@....>......._
00001900: d16d b2ac 1b2d 1e67 e5d3 4315 c6b8 d5d7  .m...-.g..C.....
00001910: b4a7 3523 9b6f b19e 4828 8711 2e88 8e76  ..5#.o..H(.....v
00001920: 01bf e2a0 0d51 5e98 2e78 f348 9b2e 6cf5  .....Q^..x.H..l.
00001930: 1097 52f7 965d e9cf 2248 4c31 d0c3 d904  ..R..].."HL1....
00001940: b25c daf1 e44f 8e3f 796d 2f94 d085 dca3  .\...O.?ym/.....
00001950: 0931 14b1 cd8f 505c b38d 5ad5 de2e 9e47  .1....P\..Z....G
00001960: 6cbb 028b 346f 37b1 7489 3e9d 6b7f 59e5  l...4o7.t.>.k.Y.
00001970: f5d7 eacf 9538 9a04 cb58 eedd d782 d296  .....8...X......
00001980: af17 4312 4dfc 7f0a 26f1 7ae0 8b50 2bcd  ..C.M...&.z..P+.
00001990: 4a55 5ec7 c69b 877d 2a16 ffa4 93dc d169  JU^....}*......i
000019a0: c729 3549 6312 5f47 836c e8cc 044d 8a2b  .)5Ic._G.l...M.+
000019b0: 39bb 1178 6ea6 50f6 e38b 1589 971b 2b6d  9..xn.P.......+m
000019c0: 876b 103a 69a0 3c49 5369 1130 2468 d7aa  .k.:i.<ISi.0$h..
000019d0: b9bc eb63 db6e 3e17 dcf5 d145 0dc2 ba9c  ...c.n>....E....
000019e0: 1679 b96d e364 0dbc 8735 fd05 b7c6 1859  .y.m.d...5.....Y
000019f0: 0c9c 5abf 2da6 ac45 d4ea ae45 4485 6d31  ..Z.-..E...ED.m1
00001a00: 3ab3 d01b d41f 227c a365 4177 4875 8615  :....."|.eAwHu..
00001a10: 28c2 58a9 ddc4 c63e 5048 0d30 a519 6688  (.X....>PH.0..f.
00001a20: 07ee 813b 7370 0894 9c0a 4b81 ecf3 b2b2  ...;sp....K.....
00001a30: 74a1 7519 dbf2 c86a a91f 5a24 119a 73c2  t.u....j..Z$..s.
00001a40: dcff 2e0d af10 dc9a 3832 f4a4 5889 228c  ........82..X.".
00001a50: c3d6 e195 3446 e6fd 3947 792d 055c b51b  ....4F..9Gy-.\..
00001a60: 921a fa92 8185 fe3c f196 4d32 11a7 0e6f  .......<..M2...o
00001a70: a434 8335 9d55 d9c7 2cec ad70 cb3a 4c3e  .4.5.U..,..p.:L>
00001a80: 2bc0 6ce6 c582 5ca9 8bb2 234d f560 72ef  +.l...\...#M.`r.
00001a90: 4a3c 2cfe 4813 0f5f 5ac8 5efa 55b5 b99c  J<,.H.._Z.^.U...
00001aa0: b7ee f06f 448b 73b5 2ed8 a294 f40d e333  ...oD.s........3
00001ab0: e241 2709 d13d 8751 4e3d b904 0548 5ac9  .A'..=.QN=...HZ.
00001ac0: 2459 0218 316e 429e 81fa dddd 38bb 84e0  $Y..1nB.....8...
00001ad0: 50b4 9f68 d467 8401 07bf 2cd0 1e01 6b45  P..h.g....,...kE
00001ae0: 0659 6143 a01d 23d7 ec4d 1b08 4b50 1209  .YaC..#..M..KP..
00001af0: 7067 d540 cf54 f4ca 9bf3 dfde 3668 9f50  pg.@.T......6h.P
00001b00: dd99 eccd d335 dcfb f817 ed03 77e1 6a84  .....5......w.j.
00001b10: 9a72 2748 1949 b43c 3037 2f06 b3ff a7b9  .r'H.I.<07/.....
00001b20: e09f fa20 f817 10b5 9e82 10e8 1182 4263  ... ..........Bc
00001b30: 4182 3e30 7b4d 4b71 7a64 6bd1 2827 1e9c  A.>0{MKqzdk.('..
00001b40: 26ef 3d3d 3d3d 3d3d 3d3d 3d3d 2069 7318  &.========== is.
00001b50: e04d 6ff6 fb85 8524 c1d9 f861 d7c7 5bcd  .Mo....$...a..[.
00001b60: 6c06 2f69 0be0 a298 bea5 6fc9 b6ea 66ca  l./i......o...f.
00001b70: 1c82 99c8 893e dc99 3203 a648 bafb 9ddf  .....>..2..H....
00001b80: b7fa be12 4dfe 0c62 fcf9 4836 c778 e809  ....M..b..H6.x..
00001b90: 3202 c8f2 497a dd9d d933 df09 c7de 2daa  2...Iz...3....-.
00001ba0: fcb8 4d78 a9bf b4e8 b4e5 472f 017f 579c  ..Mx......G/..W.
00001bb0: 48cd 49b8 bb7e 923c e244 d4ce 729a c8bb  H.I..~.<.D..r...
00001bc0: dbc9 0416 2ce8 5cfa a8d4 b065 b788 d43b  ....,.\....e...;
00001bd0: ad1e cdcf 5f28 036b 9c66 979e 1fdc 64fb  ...._(.k.f....d.
00001be0: 8520 29c0 9c73 c65b f0ed 7b5b e4c7 9c65  . )..s.[..{[...e
00001bf0: e963 bc5b eb40 091c 9e77 5675 f9bc 4d60  .c.[.@...wVu..M`
00001c00: c73e 9ed5 c3fb 1e02 c249 5a69 b631 7c7e  .>.......IZi.1|~
00001c10: 8965 a94d 3f1a a607 bdf5 d2b3 1d97 5999  .e.M?.........Y.
00001c20: 2601 72fa e5c1 6cef ba59 b0e1 8549 be7e  &.r...l..Y...I.~
00001c30: 06a3 6c21 e673 4585 3b0b 8f26 f695 1ff8  ..l!.sE.;..&....
00001c40: 3231 1a84 4154 7be7 12f1 935e 2aa7 e4dd  21..AT{....^*...
00001c50: a95f 3ea5 bd21 751e a8ab a1b5 1266 b2bc  ._>..!u......f..
00001c60: 8dfb a1ca 5ffd d6f2 4ab5 a0d4 97d6 c2e3  ...._...J.......
00001c70: 07ae ebed e024 a051 77b8 6fdb 780d 5c7d  .....$.Qw.o.x.\}
00001c80: baff 6b85 b08f 40e4 c3cd 75b0 6afb a568  ..k...@...u.j..h
00001c90: 7f18 deb4 65d2 3a6a 9f98 a626 8bd1 0dd6  ....e.:j...&....
00001ca0: 75e7 0e1e fc22 3656 2d28 9b2c 0a0b dca6  u...."6V-(.,....
00001cb0: 8d26 44d3 3414 b717 131c 1bc7 8107 e44b  .&D.4..........K
00001cc0: 57d3 8dc1 c158 88a5 b7e0 a59d ed6f 4b02  W....X.......oK.
00001cd0: b043 d9fb 0b8e 82e9 9e07 7405 99c0 e30e  .C........t.....
00001ce0: eb1c 7ef9 a126 5264 a283 0aa2 e6ed 1061  ..~..&Rd.......a
00001cf0: d158 43b0 3e96 5f0d 494d 77fe 55f6 7935  .XC.>._.IMw.U.y5
00001d00: 8164 3b82 2589 ab63 fe8f 5a07 629e ef47  .d;.%..c..Z.b..G
00001d10: 4772 009e 03b7 0c9b 2b50 1b77 866c 2838  Gr......+P.w.l(8
00001d20: 41ec bd13 c7f5 426f 8239 539e 5f3c 7326  A.....Bo.9S._<s&
00001d30: aa85 743c 2550 3f68 4e1d 4ff6 5610 fc41  ..t<%P?hN.O.V..A
00001d40: fc51 edc3 cf72 a60c 8613 117f a00b 3d1c  .Q...r........=.
00001d50: d4c8 82c2 4b0a f480 22df 18ac 8ab6 8aed  ....K...".......
00001d60: 6d60 7285 d6aa ab16 2b37 79e6 b08f 143f  m`r.....+7y....?
00001d70: ec0e 275e 5ba0 973a 9334 7f0b 56d1 43a7  ..'^[..:.4..V.C.
00001d80: 6140 c410 232f 2c9e 742a 8759 eeb9 51c8  a@..#/,.t*.Y..Q.
00001d90: 4e81 bae3 d5d6 cdde 5e9d 2c9d 0ba6 8839  N.......^.,....9
00001da0: 0280 a6ff 61d2 bd08 0bde d073 fb02 7e02  ....a......s..~.
00001db0: 4601 6834 fb38 50a9 9f51 6325 6423 ed15  F.h4.8P..Qc%d#..
00001dc0: bcd7 d79d 5e10 7615 2780 5cc4 5de9 6181  ....^.v.'.\.].a.
00001dd0: e148 5613 1403 8676 749b 8c61 c5a5 4e9f  .HV....vt..a..N.
00001de0: c88f f6ad 59ab d3aa 386b 4d9c a660 058f  ....Y...8kM..`..
00001df0: 4502 b08c e183 482c f563 b49c 6efc 3e56  E.....H,.c..n.>V
00001e00: 744c e925 b42b 5068 905e 0ed8 6fee aeae  tL.%.+Ph.^..o...
00001e10: eb75 ee25 83ab fc73 664b b000 ebe3 0153  .u.%...sfK.....S
00001e20: 2cd8 0e01 260c 2231 e155 89a5 172d 4343  ,...&."1.U...-CC
00001e30: 0962 7040 1d28 c224 bdc8 625b b4a8 565c  .bp@.(.$..b[..V\
00001e40: 8f6a 0c21 55cf c6ed 2973 9ab6 2aff d745  .j.!U...)s..*..E
00001e50: 78e5 ce87 9d4d 27ee 2c0f 1fe5 17d1 2663  x....M'.,.....&c
00001e60: 9744 93fc e033 78e6 e130 f033 2595 0c6c  .D...3x..0.3%..l
00001e70: 5e10 d114 39f4 b513 e80e b451 4fea 92f4  ^...9......QO...
00001e80: 21b3 9b11 abba e219 933c 8396 14d9 cf50  !........<.....P
00001e90: fd22 3611 57de 33fa 9e35 1244 8515 f364  ."6.W.3..5.D...d
00001ea0: 58c3 fb96 9410 0b31 0e87 e315 482e e6d6  X......1....H...
00001eb0: dfec b18d a554 b688 f99a dade fd82 ad98  .....T..........
00001ec0: b861 663f 8b2f 4e49 43ee 0f5b 3a69 d0d7  .af?./NIC..[:i..
00001ed0: a049 498b 009d 0813 4425 7809 8e7b ac5e  .II.....D%x..{.^
00001ee0: 6a52 bd0e f939 cb7c 4edb a176 77f0 93e9  jR...9.|N..vw...
00001ef0: 0598 84a4 eb1a 8bab cd96 b5b9 155b 87bf  .............[..
00001f00: 6c9f af06 18ab 6509 4300 42d7 73ee 3a63  l.....e.C.B.s.:c
00001f10: 6a4a 51b9 ed72 5665 9f0a 3863 e240 1d5f  jJQ..rVe..8c.@._
00001f20: c49c 018a b39b 42bf fa89 b09f f144 7fe4  ......B......D..
00001f30: b7c4 018d 892a 87eb e316 60c7 c3b6 375f  .....*....`...7_
00001f40: bdfa 8f33 d70e b27c f38b 085b 6b6e 1584  ...3...|...[kn..
00001f50: fc69 f2d4 a5ce 0798 2599 869e 10da fc28  .i......%......(
00001f60: 1a0a 8a22 a3a9 8deb d55c f69d d82f 1511  ...".....\.../..
00001f70: 4115 ecfd e7cf ff32 5c3a 3dbe 87a8 c2f9  A......2\:=.....
00001f80: 46ec bf67 07fe 5deb e366 65b0 97a4 7a97  F..g..]..fe...z.
00001f90: e604 65e1 7d82 1fca 7e1d ccc4 3abd dc11  ..e.}...~...:...
00001fa0: 86f9 5aa7 d0de 9dfc f241 f2fb d499 5c47  ..Z......A....\G
00001fb0: 5db7 8cf6 4ae6 6be3 e39f 9f33 be0d da91  ]...J.k....3....
00001fc0: dc6f 5fe4 e854 3497 6fe0 be9e 2e97 be15  .o_..T4.o.......
00001fd0: 2334 71ec 2325 4aca 92be 92b9 6ae5 2f7f  #4q.#%J.....j./.
00001fe0: ef2e 84d4 dc33 d547 9a64 73a8 c944 a0c9  .....3.G.ds..D..
00001ff0: a81b cc91 873a 1444 f98a f56e 89b0 6d36  .....:.D...n..m6
00002000: c219 3cf5 9680 cdff 6fe5 e0e4 1b33 4c65  ..<.....o....3Le
00002010: 4ade 753d 5d54 9e90 8c4a 9f6e b02c 8663  J.u=]T...J.n.,.c
00002020: 09c6 711a c2f9 ac96 8769 9e4b e16b 7059  ..q......i.K.kpY
00002030: 1134 34c9 9e34 dd9a ead1 43c6 b4e0 8852  .44..4....C....R
00002040: 35a1 e2c2 9047 c6af 52f1 8ac2 10de a3d3  5....G..R.......
00002050: bf8c 7f91 d79d 0385 f31c 6361 6568 6ce9  ..........caehl.
00002060: b266 930d fa61 b268 81bc 9a05 cdf5 1013  .f...a.h........
00002070: 2861 0d26 55d0 6bcf 5338 a7dc 14f7 3e35  (a.&U.k.S8....>5
00002080: 3198 68c1 3af0 20ef 863c ffc1 2b8d 26e1  1.h.:. ..<..+.&.
00002090: 97b3 9e50 c666 4fe1 4587 f8cf 262e 461d  ...P.fO.E...&.F.
000020a0: 6c38 8ea9 ff06 0a6c e5ee 72e3 0dea b66a  l8.....l..r....j
000020b0: 4b4b 4837 d8b6 1cb6 cca9 0111 fb36 add4  KKH7.........6..
000020c0: 3816 ee33 c970 7c81 b897 156e 5153 96d5  8..3.p|....nQS..
000020d0: 71e2 4de8 7aa7 7ce0 cd7b 81a8 4ad6 806a  q.M.z.|..{..J..j
000020e0: c43d d811 1699 6b85 8932 d09b 42a1 9db3  .=....k..2..B...
000020f0: 68fd b2a8 3dca b667 067f 0f02 580b c325  h...=..g....X..%
00002100: 27dc 828e bd08 ed8f 4b7c 8f8e 4394 f5a2  '.......K|..C...
00002110: 2ef7 4b7c a2d5 7bd2 b4bc 45e2 71f7 c9d7  ..K|..{...E.q...
00002120: da51 62ec 3a51 bcea 8af3 ab5d 9ebf cc88  .Qb.:Q.....]....
00002130: 3a41 eeaa dcd2 d8b9 bd10 5344 9aca 3ef8  :A........SD..>.
00002140: 01ad e4b4 0583 3079 0bb7 dcbf 003c afd3  ......0y.....<..
00002150: 4277 2ccc d7b1 47f5 65b3 d7b3 9485 22ef  Bw,...G.e.....".
00002160: db0d db5b f061 4903 357e 5254 72a6 ac68  ...[.aI.5~RTr..h
00002170: c881 3e17 1b7a bff8 17df 4a45 0126 42f3  ..>..z....JE.&B.
00002180: b9b2 e438 06f0 4472 1ea0 f00c 6429 7fa9  ...8..Dr....d)..
00002190: 9530 2422 6604 7c17 1bda 1191 fd71 7606  .0$"f.|......qv.
000021a0: 446e 04df 0861 85b0 dcda 0288 ed13 4ea3  Dn...a........N.
000021b0: e7d2 2277 2a84 635a b982 2790 5c91 7ff2  .."w*.cZ..'.\...
000021c0: d6c5 43b5 b530 7a33 98c9 045d 04ca 112a  ..C..0z3...]...*
000021d0: 3f11 73e9 6400 f672 b512 1774 82fc fcc6  ?.s.d..r...t....
000021e0: 95aa 6f46 c656 afe0 6147 895d 0cd8 bab8  ..oF.V..aG.]....
000021f0: cbd2 a906 ba61 49b3 1d46 cce0 7514 e1b8  .....aI..F..u...
00002200: c157 1387 f5ad 6d51 1362 f5bd a171 1fba  .W....mQ.b...q..
00002210: 233b 1be5 c6f9 e922 45f0 c4a4 3f02 7307  #;....."E...?.s.
00002220: cccb d656 d3af b56e 8aad b0fc a072 7898  ...V...n.....rx.
00002230: 58a3 a964 c548 a9d6 0856 1c79 05e6 b6c2  X..d.H...V.y....
00002240: 98ce 51fe 646f 3a56 215a 31ff 5adc 3d2b  ..Q.do:V!Z1.Z.=+
00002250: 8b7e 802c bf27 7bee c47e fac9 bc3d 43c0  .~.,.'{..~...=C.
00002260: 3dc7 3761 1ba8 7e92 d03f 3c0f 715f fe43  =.7a..~..?<.q_.C
00002270: 50a9 dba6 cbe6 4f2b afbb 73af 2645 c389  P.....O+..s.&E..
00002280: cbc9 cb03 477b be89 5be2 3e20 4110 50b4  ....G{..[.> A.P.
00002290: a948 dda7 48f3 e3e7 4f59 5ee7 9f12 8fd5  .H..H...OY^.....
000022a0: b438 62b0 d954 e29a f9d3 5082 9674 13e4  .8b..T....P..t..
000022b0: bbe1 ef6e f48d 7dd0 eefe 2df3 36b4 34db  ...n..}...-.6.4.
000022c0: 7343 2256 9d7d 22e6 7371 52a8 c112 71e5  sC"V.}".sqR...q.
000022d0: a7c1 d22f 59a0 e201 87a4 0cf1 48da 0d33  .../Y.......H..3
000022e0: ca25 0bbb f538 9c9d e961 2138 6e02 9b89  .%...8...a!8n...
000022f0: 6f81 60bf b527 4977 17ed 2f36 e679 3ea3  o.`..'Iw../6.y>.
00002300: a1c5 09ea 53b1 8163 d85b f642 a04d caea  ....S..c.[.B.M..
00002310: f555 141e 44f9 4e19 8776 774f 9df1 8783  .U..D.N..vwO....
00002320: a359 116c 7005 09ac d2b5 10c4 31f1 993a  .Y.lp.......1..:
00002330: 5ad1 fdf3 8a10 22ef bac0 5569 3ef2 379a  Z....."...Ui>.7.
00002340: dcdd 8394 5116 7658 2441 d37c 6a44 d0f6  ....Q.vX$A.|jD..
00002350: 62a7 b391 0c40 7aab 6a09 07fe 45c8 1392  b....@z.j...E...
00002360: 99f6 a54d b6d4 8542 96a5 20df b88e 69a9  ...M...B.. ...i.
00002370: 13b9 44e6 382e c8e1 f0ba a3fb 5708 2f8c  ..D.8.......W./.
00002380: 1bbe e34b a408 3c55 a5c2 33a8 b9ea b948  ...K..<U..3....H
00002390: b696 f1f3 5d49 1dc9 6a66 855e 62af 973c  ....]I..jf.^b..<
000023a0: 6a06 2dda 5b7e b1f8 e744 1853 dd42 5699  j.-.[~...D.S.BV.
000023b0: 92e2 37af b2b2 111f 6731 3036 364e 4a7b  ..7.....g1066NJ{
000023c0: 60af e80e 9886 3f10 7fba 438b a83f 0797  `.....?...C..?..
000023d0: abce d76b 88d8 15a0 efa4 9a08 32cd d581  ...k........2...
000023e0: 6153 9e7a 70ee 06a2 5ef2 9071 b878 0df4  aS.zp...^..q.x..
000023f0: 0e3c da4c ebdc a461 5ebc 1565 0ec8 6232  .<.L...a^..e..b2
00002400: f884 283c a929 1920 13d4 975b a147 9824  ..(<.). ...[.G.$
00002410: 70da 3071 0944 e45c 051c 49bc 4899 6093  p.0q.D.\..I.H.`.
00002420: 4133 0aa9 f3ab 009a 2d59 63d5 ae6e 2098  A3......-Yc..n .
00002430: e512 04bd cfb2 e55e 7b8c 502c aec0 5db3  .......^{.P,..].
00002440: 329d b4be 45ff ed2f 23c1 5c82 6dab 7e82  2...E../#.\.m.~.
00002450: d3f8 b65d 10d2 178b ba1c 3dc8 e03f 2eea  ...]......=..?..
00002460: 12a5 b993 31ff de9d 9e93 1ce7 7e21 5acb  ....1.......~!Z.
00002470: 0439 5524 026c 47c3 faf8 0053 81f1 65e1  .9U$.lG....S..e.
00002480: 2585 8859 3347 0c97 6f72 263e a00d 722b  %..Y3G..or&>..r+
00002490: 6ff3 5725 3a17 4fcd 23a2 dfe2 c103 a17a  o.W%:.O.#......z
000024a0: 2c71 2d29 a16c 862f dc5b 6130 502e 26fc  ,q-).l./.[a0P.&.
000024b0: b6e2 ddb5 6830 6710 64c3 d504 ac07 468a  ....h0g.d.....F.
000024c0: b79a 253f 7e1e 5f2e 2204 58dc 6067 451a  ..%?~._.".X.`gE.
000024d0: 5298 d798 e182 a09f 744a 9af6 1774 bd22  R.......tJ...t."
000024e0: a93f aadb 1c33 43ee b129 4577 6804 077a  .?...3C..)Ewh..z
000024f0: 1fdc 66cc 9323 21c1 7d0b 1dd2 66c0 4534  ..f..#!.}...f.E4
00002500: 6aaf 6f7b 4996 8689 b0cf 7837 e7e5 536d  j.o{I.....x7..Sm
00002510: 46c8 4554 f68e 116b a993 24b7 5912 1479  F.ET...k..$.Y..y
00002520: a0d7 241e ac16 c7e1 7e99 ea0b 6bd8 b825  ..$.....~...k..%
00002530: 4166 2e58 72ea dee2 211e 8099 d025 971e  Af.Xr...!....%..
00002540: 5942 0ed6 e1c4 6660 bc33 77b1 a740 d82b  YB....f`.3w..@.+
00002550: 293c db95 ef12 141a 749a 67cb 1d5c 13b2  )<......t.g..\..
00002560: a780 afd3 d571 47cc 5465 d309 3797 1eb5  .....qG.Te..7...
00002570: 4abc 15a7 3135 e6eb 25bf bac8 6e21 2513  J...15..%...n!%.
00002580: ed2f 083d 87d6 071f fb0c 2230 cc7f cb74  ./.=......"0...t
00002590: a259 509c eb23 842c 29c5 d4c2 4bef c84a  .YP..#.,)...K..J
000025a0: cbe7 1119 e87d 229d deb6 ddf5 c7ee 9f2a  .....}"........*
000025b0: 1593 aa45 589d 71d8 2f9a 2d19 ff4c f250  ...EX.q./.-..L.P
000025c0: 41db a3c6 d7db b1f5 83c6 1fd7 699f 6a89  A...........i.j.
000025d0: 57d8 d575 767d a268 994b fde6 1325 61a0  W..uv}.h.K...%a.
000025e0: 5f85 6636 ab2d fa25 b63d 90ba e865 e281  _.f6.-.%.=...e..
000025f0: 0b4d 1cb0 708c e996 3c86 1aae b2ce 9ed1  .M..p...<.......
00002600: 6738 20a6 01a4 04e8 6488 7d3b 941b e072  g8 .....d.};...r
00002610: dbf3 4a9d 204d a571 92f2 257e be39 7a10  ..J. M.q..%~.9z.
00002620: c4a4 2ce0 d794 3be7 6cad aaf4 9f72 a6c0  ..,...;.l....r..
00002630: 8200 ef99 02c4 6391 3b9e 3301 cb1f aeec  ......c.;.3.....
00002640: 0c30 2213 e6dd 49b4 4e0a b38a 7e14 2541  .0"...I.N...~.%A
00002650: 4d5f 393d c3ea 8ad8 d93c f383 26de 5edd  M_9=.....<..&.^.
00002660: bd60 8b0e 2f5b 27b0 cc7d 0f1c 13d5 4e9b  .`../['..}....N.
00002670: 5953 52bf fec7 2e93 fdf8 4aad 89fb 26bd  YSR.......J...&.
00002680: 4ac1 d1d8 7be1 f49d 8c83 ad88 c84c 5c50  J...{........L\P
00002690: 8ce2 dd00 ed35 c9cd 4aa3 7f2a 4f47 d0f7  .....5..J..*OG..
000026a0: eb39 24d7 5f7b ad32 5b69 7c7a 10ce e104  .9$._{.2[i|z....
000026b0: c262 de9b 77ea ed8f c62a 1424 70db cb23  .b..w....*.$p..#
000026c0: a00e b54d 9a83 2b2d e11b 869a 0e81 5123  ...M..+-......Q#
000026d0: e0f2 cb01 3ff6 9484 7f54 4c46 ba4e 8969  ....?....TLF.N.i
000026e0: 4999 fc4c 76d2 f633 52a7 bf3e 1b5c a667  I..Lv..3R..>.\.g
000026f0: cc5c 1497 ac6b 8a41 b2c8 b951 d90d 3206  .\...k.A...Q..2.
00002700: 5b27 5636 98a2 d8ad bc1b d32f 19d4 4604  ['V6......./..F.
00002710: ecb1 f649 203e 6ae4 8bc8 48fc d9d3 892a  ...I >j...H....*
00002720: 2952 5008 76ea 0645 3b01 960e 4e8b 4b5b  )RP.v..E;...N.K[
00002730: 6c24 02d2 d457 4cf5 95b9 b014 faa9 6f4b  l$...WL.......oK
00002740: 9742 ac9c a87e 3384 8d92 faaa 2073 2a33  .B...~3..... s*3
00002750: 0adb 471e 22b1 a68a 350e d704 cafb e3be  ..G."...5.......
00002760: dae6 b224 953f cc2e 6a57 642b 3213 0d5b  ...$.?..jWd+2..[
00002770: 4088 649f d658 a8a3 41e5 8a07 3cb6 528a  @.d..X..A...<.R.
00002780: 774e 89f1 4053 e5a4 0b57 b3a1 05ec 8ac5  wN..@S...W......
00002790: c6c8 96b4 fcaa 07ec 521b 78ce baf9 e2b8  ........R.x.....
000027a0: cbf1 de97 43c9 b23f 2a28 9119 022d 047e  ....C..?*(...-.~
000027b0: 4111 f779 6716 0f62 33a8 a708 b74d 7781  A..yg..b3....Mw.
000027c0: fd1c 27ec a11c 1f00 de8d 65b6 dc63 3607  ..'.......e..c6.
000027d0: 4980 1000 dcae e63a 8782 ba2b 51be 7354  I......:...+Q.sT
000027e0: dbf2 6c5b 0e7e 9bea ba92 6089 6b59 de2f  ..l[.~....`.kY./
000027f0: 8fbb c27d 289d 4269 c09d 8b1b c32d 48f2  ...}(.Bi.....-H.
00002800: 08d6 ec63 3374 929c ead5 808f ae48 6a94  ...c3t.......Hj.
00002810: a0ce 6308 9f4e 8782 1874 c207 7114 6be7  ..c..N...t..q.k.
00002820: 10eb 3669 ec82 990e f6fb 13e3 3402 99bd  ..6i........4...
00002830: 4a1c 147a 61eb 9230 fa93 3f9b d832 a332  J..za..0..?..2.2
00002840: 8428 ba1f 52f3 3183 dc2a cda2 6c46 9844  .(..R.1..*..lF.D
00002850: 4816 1ad4 c63b ba21 a42b f1a6 4106 fa1b  H....;.!.+..A...
00002860: cba7 653f 7772 85fd d3f6 fcd6 fa2d f1aa  ..e?wr.......-..
00002870: a583 19b0 b97e 7c09 ae87 11de 02d9 917e  .....~|........~
00002880: 8a36 54ac cad7 4824 2265 84cc 66f7 a63b  .6T...H$"e..f..;
00002890: ad43 e268 be2a 7d33 93d7 622c da35 02d9  .C.h.*}3..b,.5..
000028a0: 82d1 3d23 fb79 0388 8535 aea5 c709 015c  ..=#.y...5.....\
000028b0: 1a2a 5a22 8156 563c 4678 e6fa b8c8 bcd0  .*Z".VV<Fx......
000028c0: 596e e923 898d b158 5932 436b 9af3 a143  Yn.#...XY2Ck...C
000028d0: 79f8 39a7 c2af 537e 54d9 136d 7d0d 6358  y.9...S~T..m}.cX
000028e0: 0c5c 621a 79e5 53d5 c931 7e3d 790b 996a  .\b.y.S..1~=y..j
000028f0: 6b6a c227 69b5 1362 8292 3ce1 76d2 11f5  kj.'i..b..<.v...
00002900: 3171 8018 aef8 8bac 740e 9d3c 3c7a 9d37  1q......t..<<z.7
00002910: 9b35 312f f6a8 e889 71ac a7e4 f748 047f  .51/....q....H..
00002920: bdb4 c95b 4e26 18c4 6dd6 26d3 68ae a7be  ...[N&..m.&.h...
00002930: 72b0 4ecc de2a e38a 7c30 c84d ccff be0c  r.N..*..|0.M....
00002940: ee59 c25d 0b1e 8d95 2a3b 2617 0047 b6a9  .Y.]....*;&..G..
00002950: bfeb 987f 7c47 7fd6 61f5 2d59 b4fb 042c  ....|G..a.-Y...,
00002960: ada1 be3e 8f11 cc18 96b3 4ec0 9867 dafa  ...>......N..g..
00002970: fe31 44eb b2ed 83de 33e0 ec9b a2e6 576c  .1D.....3.....Wl
00002980: 471d f941 a64c 1d36 678a ecf4 8415 c059  G..A.L.6g......Y
00002990: 7d40 f0c6 6f7a 5a8b eb2e bbd2 3cc0 76ce  }@..ozZ.....<.v.
000029a0: 1e56 e5c0 422a 8509 43c3 0ee4 e6d3 8412  .V..B*..C.......
000029b0: 6317 8c2e 42ce 26e1 7034 063f b796 0927  c...B.&.p4.?...'
000029c0: 4a1a 0863 5066 cf13 e526 e6c0 5267 6de0  J..cPf...&..Rgm.
000029d0: 74b9 69f4 21a8 d74f 6c1e 0640 05ca 6956  t.i.!..Ol..@..iV
000029e0: 66b4 4cfc 0669 270a 9315 1a42 5cc1 a601  f.L..i'....B\...
000029f0: d29a c19d bfb1 9a67 281a 7929 907c cb43  .......g(.y).|.C
00002a00: a147 9d90 23cf d7bf 4aa8 0224 4f45 7e4d  .G..#...J..$OE~M
00002a10: b4a5 6253 e011 d479 f549 dbfd c8fc 206d  ..bS...y.I.... m
00002a20: 74d2 32bb 930a f63e 4f6f c596 c71a 9e82  t.2....>Oo......
00002a30: b4e3 e57d b9a7 7e48 d175 7728 fdc0 18e7  ...}..~H.uw(....
00002a40: e7be 24d1 63b5 b73f dadf fe70 3e2a 213a  ..$.c..?...p>*!:
00002a50: e93b c102 ae03 513d 3928 9264 e6c9 7b4e  .;....Q=9(.d..{N
00002a60: 28d7 68fe 06d9 ae4a 5713 81bf 6a17 d36a  (.h....JW...j..j
00002a70: 5a13 9d16 ce41 2fcb 20ad 2ae2 91c3 5b8d  Z....A/. .*...[.
00002a80: a07c c7b2 f83c 1207 51ef e6e4 6026 636c  .|...<..Q...`&cl
00002a90: 0af3 1757 e96b ea2b fd4d 3178 233b 2d58  ...W.k.+.M1x#;-X
00002aa0: 9099 c982 a53b 0be2 3338 3a9a 9b45 aaa5  .....;..38:..E..
00002ab0: 0dd5 f607 8921 58da ec28 311d ffeb b0d8  .....!X..(1.....
00002ac0: c37d 6f42 ae60 ace2 577c b930 6785 6ac9  .}oB.`..W|.0g.j.
00002ad0: fa2f dca1 1544 a8bf 6a22 e0df a087 b7f5  ./...D..j"......
00002ae0: 66a2 3fc9 a5d0 9dc7 7569 6b69 cdd6 d7cd  f.?.....uiki....
00002af0: 67e3 3cba c5b2 afa2 541b 8ee9 bac9 6ecf  g.<.....T.....n.
00002b00: 4861 9351 e704 0621 87db 9550 7657 d396  Ha.Q...!...PvW..
00002b10: b65e 7aa6 ee72 b86d 2c03 f147 9ffc 6bd1  .^z..r.m,..G..k.
00002b20: d577 4917 a7f8 c457 88e8 0690 6d00 75a4  .wI....W....m.u.
00002b30: 9b3e 69bf 23db 74f3 d67f 5f5f acf9 d04f  .>i.#.t...__...O
00002b40: 8d90 ec66 4a07 7ebf b373 1412 518d 0feb  ...fJ.~..s..Q...
00002b50: 9e62 26a2 7c28 c065 72b5 f341 a791 5f59  .b&.|(.er..A.._Y
00002b60: b6b2 483a 37ac 763e 684a ed2f 9d2e 32db  ..H:7.v>hJ./..2.
00002b70: dead e752 fd64 cb67 7301 f6d3 103c e8e4  ...R.d.gs....<..
00002b80: 81fe 116b d719 56b4 019a 120e 46e1 0034  ...k..V.....F..4
00002b90: 9674 6d1b 4723 23bb f88f 1d25 0682 5bad  .tm.G##....%..[.
00002ba0: 1850 9dd6 a407 0870 0d55 f380 c983 41c4  .P.....p.U....A.
00002bb0: c7cd f1c4 33b7 3b1b 38c2 37a3 d799 e436  ....3.;.8.7....6
00002bc0: 4a8d 119e 7ba5 189f 8f86 3a5f e066 c954  J...{.....:_.f.T
00002bd0: 3211 40e9 4a8c 6b2e 41a4 4dfc 8e60 ed02  2.@.J.k.A.M..`..
00002be0: c377 c220 9d72 8712 1a75 710d 2891 611f  .w. .r...uq.(.a.
00002bf0: dab8 2e38 8749 3c4e 7404 68d8 064b e695  ...8.I<Nt.h..K..
00002c00: 6461 0391 ca67 b2e1 3080 8bd1 b3d8 afe4  da...g..0.......
00002c10: f468 d691 05aa 9bbc cdb1 fda9 acb2 15bb  .h..............
00002c20: b4fb 9591 eeef 9640 80cb 719b 3573 386d  .......@..q.5s8m
00002c30: b918 1af8 b488 f9fa 477f 8c28 0dc6 2c5f  ........G..(..,_
00002c40: da62 ce93 2dc1 cdac 644a b939 5127 a830  .b..-...dJ.9Q'.0
00002c50: cc19 ad1f 040c 1473 93d1 496c 8b11 8115  .......s..Il....
00002c60: 06d5 9a1e de11 c08c 1e3e eaac 1ff6 64cf  .........>....d.
00002c70: 2039 aa0b b9c0 3b55 374d 8d57 66a8 5fe4   9....;U7M.Wf._.
00002c80: 0b99 481c ff48 70f7 4353 b78a ff56 b085  ..H..Hp.CS...V..
00002c90: a9c1 e869 0bf6 73bc 357d e447 c270 8b1a  ...i..s.5}.G.p..
00002ca0: b341 f719 7849 d4d0 073b ced3 7d7a e4c5  .A..xI...;..}z..
00002cb0: 129a 5757 c45b 6fd8 62b9 4868 c57a b3c3  ..WW.[o.b.Hh.z..
00002cc0: 53f6 7908 2260 bd98 7f23 6145 2cb0 5d12  S.y."`...#aE,.].
00002cd0: 6269 ca88 2749 c57c d3a0 04f0 2bc4 6088  bi..'I.|....+.`.
00002ce0: 323f 2324 fa93 aaea d6f5 2e34 efde a553  2?#$.......4...S
00002cf0: cf80 dc9e 0474 fbe3 ed57 2e82 4cdf 92c7  .....t...W..L...
00002d00: 2dc5 7d51 48de 819e 3968 acff 02d1 331a  -.}QH...9h....3.
00002d10: 26bf 4198 3a1e ec96 63d7 fcc6 c1a6 867d  &.A.:...c......}
00002d20: a74b c875 e9f9 5839 5799 53e6 dace 31ef  .K.u..X9W.S...1.
00002d30: 0e54 21cc d3c8 b292 3a72 e5a6 8859 c4b5  .T!.....:r...Y..
00002d40: 9e0e d600 d711 c648 6d58 3e19 9333 c349  .......HmX>..3.I
00002d50: 50ba 621b d430 adc8 a627 e40f 1294 2a54  P.b..0...'....*T
00002d60: 85d6 df7a e3a8 b5a1 4ca6 b52d 5d88 1900  ...z....L..-]...
00002d70: 8ac9 5463 e772 d760 cecc 0fdc 0741 f3dd  ..Tc.r.`.....A..
00002d80: be31 4b73 3c90 e3b1 1e8a 375c d7e9 11e0  .1Ks<.....7\....
00002d90: ff82 4fec 1918 9a91 c07d 05a0 06a1 1a5e  ..O......}.....^
00002da0: 5dee 5929 7e5f 794e 5107 0460 abf2 77b3  ].Y)~_yNQ..`..w.
00002db0: 46e7 5ff5 984d f316 7109 c16b a4df 0d89  F._..M..q..k....
00002dc0: f9a4 0669 01ad 7a52 e6ac dd46 27a2 4397  ...i..zR...F'.C.
00002dd0: c44c 5445 6665 eb73 2d89 8288 a3c9 2333  .LTEfe.s-.....#3
00002de0: a516 431e 0f33 3ce4 4474 e06c 3249 4216  ..C..3<.Dt.l2IB.
00002df0: b3b2 96ef 7589 99fe 6e9e 36b8 124c d9e2  ....u...n.6..L..
00002e00: 8a79 938f 13a9 0a95 0b68 c6b5 ec79 993c  .y.......h...y.<
00002e10: 7719 2234 9518 bf17 641d b69f 8d2d 0d2e  w."4....d....-..
00002e20: bd09 c862 e623 cf27 1500 a628 6558 1661  ...b.#.'...(eX.a
00002e30: 8c96 b1fc 8a5b ae5e 060f 3f95 dfbb e3b1  .....[.^..?.....
00002e40: 0b64 470d d5f6 7824 dcff 002c a167 c595  .dG...x$...,.g..
00002e50: f6a6 8fb6 e099 6c8a aa0f e5b6 7d7e ef68  ......l.....}~.h
00002e60: e1be dd52 581b 213f 0f81 0682 84a3 61f0  ...RX.!?......a.
00002e70: 8bee a59c 99af 598a 646b 3a78 590e 9bc4  ......Y.dk:xY...
00002e80: 997f f719 d307 95b6 f3f8 4b03 13b1 f9b0  ..........K.....
00002e90: aaee e3a1 7b6f 0505 16f7 bf01 5c57 3fd7  ....{o......\W?.
00002ea0: 2e93 db88 3e1b 1685 9f4c 3a73 5673 e156  ....>....L:sVs.V
00002eb0: 9bc7 b7ed a771 f426 c103 ab84 13f5 ec2d  .....q.&.......-
00002ec0: 38ce 792b cbcc fb7a 1627 55c0 de70 289a  8.y+...z.'U..p(.
00002ed0: 6352 9aa7 63eb a66e 22e5 012a a328 18b7  cR..c..n"..*.(..
00002ee0: c0e1 4cb0 b532 0217 1195 021b 02ed 2c5b  ..L..2........,[
00002ef0: 1bc0 82c2 c33f 4eb1 6b37 b29f ad7c 364c  .....?N.k7...|6L
00002f00: dc0a e6dc af83 66cc b398 46a6 1666 cab2  ......f...F..f..
00002f10: 2bb8 b212 bbc5 1566 040c 4f9c 3957 b4a5  +......f..O.9W..
00002f20: 89ff 1b17 31e2 e1aa 3192 030c 1851 37a8  ....1...1....Q7.
00002f30: 5987 baa7 382a e2cd f90a 8301 91b7 19c1  Y...8*..........
00002f40: d271 30ac 1047 bb34 30f1 6347 c6d2 d06d  .q0..G.40.cG...m
00002f50: e674 7215 958d 3819 eed2 1af7 5de7 87f7  .tr...8.....]...
00002f60: 6797 c22f 1d9d 1c4a e701 bf45 57cd 4f96  g../...J...EW.O.
00002f70: 89fd 4395 d31b d249 4264 c202 6cdd b400  ..C....IBd..l...
00002f80: 9c20 51f8 0b8a 219b 3f99 0cc8 2971 754b  . Q...!.?...)quK
00002f90: 6332 a58a 4c6c 1291 d9b3 ffc4 ec08 c79f  c2..Ll..........
00002fa0: 5477 39ff 1265 dcd1 32bb 4668 6c6f ef77  Tw9..e..2.Fhlo.w
00002fb0: 691d b3b0 e471 b9ad 68cc e874 662d c3cc  i....q..h..tf-..
00002fc0: 745e 67da 0688 5943 d5a3 b838 7837 7344  t^g...YC...8x7sD
00002fd0: 6d9d 962d aa5a a582 38cb f2bc 2bd2 12a6  m..-.Z..8...+...
00002fe0: 26a2 2273 756e 5a66 ccd7 f632 cf8e 32d8  &."sunZf...2..2.
00002ff0: dca2 bd7f 51bc c44a d1dd 4c35 0ba3 8dec  ....Q..J..L5....
00003000: 0bfd 3abe 0f04 58f6 821d cd72 6a83 3fb3  ..:...X....rj.?.
00003010: c9d7 daca 1ae9 16ae 38fc 2244 226e 62c0  ........8."D"nb.
00003020: 18b0 c5e6 e5ef 9b6f ba97 c23b 9aea e537  .......o...;...7
00003030: 9ccc f277 329f 8303 72dc bb87 0596 f814  ...w2...r.......
00003040: be7e 5694 b185 533a 541f 0bab 345c d9dd  .~V...S:T...4\..
00003050: ae95 017c 9969 b1b1 c0ae 9752 59d7 dbd8  ...|.i.....RY...
00003060: e685 56ea c2b9 f70d 544c fae3 b0c1 360d  ..V.....TL....6.
00003070: 0d92 f754 9b5b bef0 fbad 19bb 306a 16ba  ...T.[......0j..
00003080: c229 07fc d1df c4b8 193f 9fda 6f15 2b1d  .).......?..o.+.
00003090: 1cd1 ab84 ebc4 f385 3327 1546 4cb5 57ea  ........3'.FL.W.
000030a0: 9a7e 10bc 632b af27 f2cd 36e4 125c 082d  .~..c+.'..6..\.-
000030b0: 8094 7ac2 8f9c 12c5 5589 073c d7ad a98f  ..z.....U..<....
000030c0: 3083 ef11 3b4b e902 130b 3466 f81e de09  0...;K....4f....
000030d0: 0daa 5110 e98a dc6a 8cf1 ed8f 5368 2d36  ..Q....j....Sh-6
000030e0: 1246 4353 fa68 9abe 477c 434f 347b b1f1  .FCS.h..G|CO4{..
000030f0: 96f8 69c4 0790 a3fb 01da 58c2 2e59 a2ad  ..i.......X..Y..
00003100: 37f0 72a4 041b e41a e2f6 7610 d009 3182  7.r.......v...1.
00003110: fbec a1c6 ab59 5e9c cf86 abe7 cfdf 1977  .....Y^........w
00003120: 2b07 e913 fd4f 4a39 9b96 b123 fcfd 3c0f  +....OJ9...#..<.
00003130: b336 193b 0638 d2b0 46f5 e5cb 5fc0 3399  .6.;.8..F..._.3.
00003140: ebcf d14c 91c7 b3e2 1ae4 dd35 439a 944e  ...L.......5C..N
00003150: 7b4f 5610 c107 bd3d 753d 962a f1eb 4ddf  {OV....=u=.*..M.
00003160: 3122 6d83 493e e8ac e68b 4109 e0dc 5e6c  1"m.I>....A...^l
00003170: 849b e091 6b73 92a7 5b74 c52c df57 811e  ....ks..[t.,.W..
00003180: 6763 b538 5f8a 1386 e8a9 a472 1218 9eaa  gc.8_......r....
00003190: b186 2f92 c352 c7ff 5e60 e65c c656 d1f0  ../..R..^`.\.V..
000031a0: c87b b495 4526 0c4d 4d71 2e66 7fb3 450c  .{..E&.MMq.f..E.
000031b0: abd8 1034 0532 0dd1 0cbd 20c6 0e50 3f40  ...4.2.... ..P?@
000031c0: afb4 2ace e372 07b3 6e79 96eb 2206 5702  ..*..r..ny..".W.
000031d0: 9952 66da b0d8 a872 b33e d50d 2438 351f  .Rf....r.>..$85.
000031e0: 786d 0553 5c54 b61a 9b86 7e75 c051 bc39  xm.S\T....~u.Q.9
000031f0: 303b 4390 b3bc 87dc c545 cb67 38ef 4d24  0;C......E.g8.M$
00003200: 884f 0314 679f bc74 f111 ff14 c273 5506  .O..g..t.....sU.
00003210: e9fc c49c 2b7a 5f42 ba11 52c7 8944 4f60  ....+z_B..R..DO`
00003220: 4945 c5af fa78 9a53 5136 ed67 3788 d2f9  IE...x.SQ6.g7...
00003230: 67fc 24c8 47a6 3013 1fc1 de51 277f de53  g.$.G.0....Q'..S
00003240: 7b12 7053 2adf 5c35 3a82 3f65 fd57 a319  {.pS*.\5:.?e.W..
00003250: 372a 35da 36c8 9578 a77f e948 15f2 721c  7*5.6..x...H..r.
00003260: 2577 c16b 8a20 1efc 501f 3538 c859 d624  %w.k. ..P.58.Y.$
00003270: a839 e919 d4c2 58dc 8747 2183 8c56 d8ae  .9....X..G!..V..
00003280: 44ad 60a9 b396 bcf1 5f98 be09 e477 5769  D.`....._....wWi
00003290: 587a 7f87 23bf bdf4 b865 78e4 7c5f 128e  Xz..#....ex.|_..
000032a0: 1bed 8f5f f732 9d0a 0026 12d2 15f5 abb3  ..._.2...&......
000032b0: 5634 3c3a 1c7b a18e 52f2 d39b d0ea 20ff  V4<:.{..R..... .
000032c0: 5863 86d6 58e9 40fc 8278 1de8 2332 c34e  Xc..X.@..x..#2.N
000032d0: 2846 f0b9 2564 8266 eef6 63e6 f1a3 554c  (F..%d.f..c...UL
000032e0: 8395 b4d1 a6a0 24cb 3ae6 9887 1da2 387f  ......$.:.....8.
000032f0: 0a83 72e1 ac7f 928b e5ac 957b a202 3a62  ..r........{..:b
00003300: 5fda f5f1 8d2a a45e 13d0 f7f9 3f25 89fd  _....*.^....?%..
00003310: ee00 7f1e 1ce4 ad58 7305 2cca 7610 f0d4  .......Xs.,.v...
00003320: 6a6a d1f3 0355 ff1e 62fb bbc4 f607 3718  jj...U..b.....7.
00003330: 8066 b528 ebc2 1e19 c74b edd7 217e 5eea  .f.(.....K..!~^.
00003340: a54f 7816 6f82 54bb 6e66 f65f 36b4 6c4f  .Ox.o.T.nf._6.lO
00003350: 02a5 9242 7c00 ad7c 1f3b 950f 5fce 02c4  ...B|..|.;.._...
00003360: bcca a42d 4e82 bb4a 42f5 b979 be6a 3d47  ...-N..JB..y.j=G
00003370: 44c2 b5ae 57a7 4bc6 74ef 089c 0b56 c01f  D...W.K.t....V..
00003380: d967 8c5a 2dc5 1f3b 6061 6847 5e24 9535  .g.Z-..;`ahG^$.5
00003390: 24bf 26ec 8a5c 485c 157f fddf 4e58 2952  $.&..\H\....NX)R
000033a0: 534d 4fc4 9332 f5e3 186a 3fd5 c753 bb96  SMO..2...j?..S..
000033b0: ae6c 3ffb 3f83 8e27 68a8 dfe6 0e6c db72  .l?.?..'h....l.r
000033c0: 244b b929 1752 2375 9d93 57af 3104 b996  $K.).R#u..W.1...
000033d0: 1f16 63d7 094d 5072 df54 56c5 0c55 72b8  ..c..MPr.TV..Ur.
000033e0: f0a6 e766 3c45 b191 6157 fb4d 0944 2e9c  ...f<E..aW.M.D..
000033f0: 4a0c 148b 4f3a 99bc 3ada 2bb3 2e7c ca4d  J...O:..:.+..|.M
00003400: 45e6 597c 67c7 58e9 76d9 4d42 4909 d3f3  E.Y|g.X.v.MBI...
00003410: 03c7 53e9 1de3 6ba3 adf2 e14c 84e6 7618  ..S...k....L..v.
00003420: b6ab 9f48 ee00 2f5c cea8 79d7 c725 e024  ...H../\..y..%.$
00003430: 42a1 5f82 f5ff 33c3 a795 8ace ee02 1fed  B._...3.........
00003440: 9012 61c2 1e7a a91d ee88 1848 45c9 8fa5  ..a..z.....HE...
00003450: 7a8b 9e5c 51ab 88a7 bd8a d394 333f ab02  z..\Q.......3?..
00003460: 4664 dd36 eca2 a9f2 d4a7 c12d 6be7 bbc0  Fd.6.......-k...
00003470: c4c6 f0e4 cf88 4054 5334 c960 fe17 b8a2  ......@TS4.`....
00003480: c08f 2df1 3aff 4620 e3d9 b70d ffbd 7f47  ..-.:.F .......G
00003490: 3288 d036 a2f7 b046 38b0 6c09 dc05 50ca  2..6...F8.l...P.
000034a0: 173c 3164 18ef 7192 efe6 e92c 7c8d bbdd  .<1d..q....,|...
000034b0: 583d db4e 41cc 8da3 2067 c3cb 0131 f7e8  X=.NA... g...1..
000034c0: 1380 d2b8 246c 973f 2d88 9aa5 d0d4 5b92  ....$l.?-.....[.
000034d0: a88a 0dcb 65c7 9a54 3a87 d3be 9b08 3d45  ....e..T:.....=E
000034e0: 7712 207c 79ab d00d 6586 8c95 4d1e 8db7  w. |y...e...M...
000034f0: b227 e0c7 4227 2cef 7558 5a18 fc50 1fcf  .'..B',.uXZ..P..
00003500: 1a1a 0966 59f3 9b4b 4687 5511 b0ef bde1  ...fY..KF.U.....
00003510: 9df4 4f65 46f1 e193 4435 5a79 54a4 d424  ..OeF...D5ZyT..$
00003520: 0a77 773e dbac 57e9 930e a9af cf98 3fa4  .ww>..W.......?.
00003530: 35f5 ecb1 74ad 65bd 2eba d565 102f dc39  5...t.e....e./.9
00003540: edc0 e1e6 7786 eb1c 151e 4f19 0f5b ff5c  ....w.....O..[.\
00003550: e6d2 31df 01cf c96f 66e0 b8dd d159 7072  ..1....of....Ypr
00003560: a454 0936 24e0 4596 e859 a5ff cc4c 8288  .T.6$.E..Y...L..
00003570: 8420 ff6e 6dcb 3809 7bf3 77f0 d244 a30b  . .nm.8.{.w..D..
00003580: 1afc 71db ac56 9904 b4eb b1f3 2a0d bda4  ..q..V......*...
00003590: 9216 f586 6b9a bc5f 5f19 c52b 1f6e 615e  ....k..__..+.na^
000035a0: aa6a fe25 e33a 4dab 60b6 fb3d 4583 811c  .j.%.:M.`..=E...
000035b0: 76cb edc7 2c63 821d 96ae 204b 624c b78d  v...,c.... KbL..
000035c0: bbad 1375 23ef 2eff a3c1 f77b 86a9 9c56  ...u#......{...V
000035d0: 3106 69aa 3cc2 2b58 a008 54c8 f8f3 33ac  1.i.<.+X..T...3.
000035e0: 4f9c 599d 8443 367a 45d3 48e0 32de db7b  O.Y..C6zE.H.2..{
000035f0: 9f5a 98fd cc2a 7c25 b0a3 a84c 9376 7786  .Z...*|%...L.vw.
00003600: ee64 774c c1b4 97a9 e997 e85a cd46 9d9b  .dwL.......Z.F..
00003610: d9f1 83b5 5e33 5946 0c8c 7d3a 101a 3212  ....^3YF..}:..2.
00003620: 8573 b454 60f1 de7f 7400 e1a6 cd8f b5cf  .s.T`...t.......
00003630: d3d1 8e30 1bcb 0cbc 3aa4 2b1d 7fef f8d7  ...0....:.+.....
00003640: 1d79 7f8e 8a6b e195 01f3 bef6 ccda 8c38  .y...k.........8
00003650: 36b8 588f acc7 c59e 4fb3 7d2e 449c fbf3  6.X.....O.}.D...
00003660: 382f 0fd5 5f08 de73 3095 a99a c352 7286  8/.._..s0....Rr.
00003670: 3772 a12e d62c fdaa 614b e141 3676 c4f0  7r...,..aK.A6v..
00003680: ff5e d6d6 7a97 6426 3a56 4378 a8b0 b887  .^..z.d&:VCx....
00003690: 3b8e a33d f816 6b2d 79cc b203 3252 c0e4  ;..=..k-y...2R..
000036a0: c984 5bb8 e4fd 64c1 e21c 3581 caf0 6671  ..[...d...5...fq
000036b0: a610 b689 fe04 3478 e50f c5dd e4f4 533f  ......4x......S?
000036c0: 9481 fb6a 77df ee39 0413 ef9f 958b 8198  ...jw..9........
000036d0: 959e e2eb 7052 d493 53e0 6993 6941 343b  ....pR..S.i.iA4;
000036e0: 159a 590f ccf5 f9c2 ac8d e433 57e0 aabb  ..Y........3W...
000036f0: 93eb 3d7c 1314 2ce4 7212 2990 c1b2 0ca9  ..=|..,.r.).....
00003700: c42f f98c e0a5 2d62 a2fa 74a9 db3c f9d4  ./....-b..t..<..
00003710: c39b 487e f464 ecc4 580f a0f0 6601 ccf1  ..H~.d..X...f...
00003720: ec43 91ef 47f5 5c34 ebb0 5c06 b784 973d  .C..G.\4..\....=
00003730: ecf9 1d37 171b 1320 1c6a ca1d 35a4 a0a5  ...7... .j..5...
00003740: cbd1 b5bc d434 74be de29 1f5d 9651 c164  .....4t..).].Q.d
00003750: 73e6 ef8a fc63 215f 299a 942b 90bd a1db  s....c!_)..+....
00003760: 14cf ca20 d0bf 66f6 b333 00af 54aa fdc9  ... ..f..3..T...
00003770: 3724 99a1 bfde 8ce3 93e5 a413 8224 74d8  7$...........$t.
00003780: 7389 e0d5 b83b 69f7 9092 f433 6a8c 625a  s....;i....3j.bZ
00003790: fc00 a498 3f6e f579 51a2 6e08 5131 bdd5  ....?n.yQ.n.Q1..
000037a0: 5536 09fa 3a4c f47e cda3 ae3c b695 cb7f  U6..:L.~...<....
000037b0: 69ba 9e67 ace1 c5bf 0c8c bf04 a469 2573  i..g.........i%s
000037c0: 5318 fd11 5e78 997b 1cc8 802f 5d92 56f2  S...^x.{.../].V.
000037d0: da17 7e5c 7064 4dfa 8f8e 8db4 d636 ebd9  ..~\pdM......6..
000037e0: 3f44 47a2 f8d1 f987 a4db 8d10 6271 8ce8  ?DG.........bq..
000037f0: 6108 2bb4 1374 c777 f142 853d 3656 81af  a.+..t.w.B.=6V..
00003800: 8221 2951 de6e 265f 19c1 9abe c1ce 4100  .!)Q.n&_......A.
00003810: 764c 469a 7fed a6c2 5494 1968 0c19 edea  vLF.....T..h....
00003820: 5a1b f635 3392 bee3 fb8c 4819 c8f8 a794  Z..53.....H.....
00003830: 4001 05ad 0463 b2c6 6a10 6f0f 9db4 61d1  @....c..j.o...a.
00003840: 8327 4569 f26b a3f0 6220 5eb9 4f66 adef  .'Ei.k..b ^.Of..
00003850: 43d0 3184 0324 bc36 21e4 b02b 30ee 0089  C.1..$.6!..+0...
00003860: c2f3 9974 38a7 3df1 1758 c6bb c147 e861  ...t8.=..X...G.a
00003870: 61d1 f760 944c f7e1 8fbb 3368 8650 7071  a..`.L....3h.Ppq
00003880: 4a36 4d36 7a37 016c 4316 5dea 4dc8 1150  J6M6z7.lC.].M..P
00003890: 2a89 4c0e 6ffe 8164 2e54 566b 0541 b864  *.L.o..d.TVk.A.d
000038a0: e5b7 355b f605 33af 97df 00e9 2eb3 3c83  ..5[..3.......<.
000038b0: 8aa5 2d2a 08e1 b2ea 0426 20da a558 2d68  ..-*.....& ..X-h
000038c0: b053 a92f 6bdb 04fa ec61 fb5c 9f67 db98  .S./k....a.\.g..
000038d0: 90ec 89a9 baca 8abe 1f51 6fa1 b0e9 6a94  .........Qo...j.
000038e0: 57fc ebfd ae3f a8bd 5e1f 6631 5086 b8cd  W....?..^.f1P...
000038f0: ebfb 5699 6c73 dccc 4cdf d510 eccd e351  ..V.ls..L......Q
00003900: 6a91 7ffd d5ff f538 1603 9014 3009 2d14  j......8....0.-.
00003910: fc57 f9d3 7458 9b3d c6e7 8d84 499f 359e  .W..tX.=....I.5.
00003920: 0c05 a320 cc0a fa4e 9662 3d66 46d5 2f3a  ... ...N.b=fF./:
00003930: 2ed4 87ba 8ddd a90d d05b acf3 3fb2 66d1  .........[..?.f.
00003940: c1df bb94 08ae 4d76 b091 ce49 6b0f a7d9  ......Mv...Ik...
00003950: ffd5 2bfb 8e12 c541 9879 7d16 3a37 e960  ..+....A.y}.:7.`
00003960: 2115 3668 bb70 3bcc 4c5d e892 8bd8 e0a7  !.6h.p;.L]......
00003970: adf1 d210 c7a0 c66c 6bbb 99ac f598 d554  .......lk......T
00003980: 5ec0 f4ee 64d9 1784 d129 0e76 ea17 4dd8  ^...d....).v..M.
00003990: 727a 4d88 dddd acea 86eb 52de 396c d12e  rzM.......R.9l..
000039a0: e937 f9e5 26ca 4f5a 9d1b 3042 57ba b9e9  .7..&.OZ..0BW...
000039b0: 48ab 8c0a 25e4 817e fb68 9801 49a1 b288  H...%..~.h..I...
000039c0: d6d0 123f 109a de9c de9b 592d d59c 4f86  ...?......Y-..O.
000039d0: de5a b515 3e38 4455 4580 9980 74a9 b0af  .Z..>8DUE...t...
000039e0: 20a4 2451 8cfd 153d 8aaf 1eda 9595 8839   .$Q...=.......9
000039f0: 71db 7758 46ce 96ad 4e62 3583 fb2c 985d  q.wXF...Nb5..,.]
00003a00: fa0e a7f9 e511 3c05 f149 dfef 3393 4175  ......<..I..3.Au
00003a10: 0ed5 0508 5193 f0ae a727 0a69 0bc1 76f7  ....Q....'.i..v.
00003a20: cd20 4830 d0c8 46f5 40cf 5bbd 8022 6f08  . H0..F.@.[.."o.
00003a30: ebbf 35e4 0246 d9a4 d954 496d 3465 8769  ..5..F...TIm4e.i
00003a40: c7d0 90e1 7524 6744 c733 1229 e49d a2e7  ....u$gD.3.)....
00003a50: 4dea c635 ac5d 8c14 c737 9fd3 c0b3 eda6  M..5.]...7......
00003a60: 21a6 c9ca f228 ab37 d1fe c98b 07ce 13e6  !....(.7........
00003a70: 813c 1832 1617 3c79 81bf cfb2 7456 1415  .<.2..<y....tV..
00003a80: 3aa7 286d 9e90 48e6 9627 f780 f628 6308  :.(m..H..'...(c.
00003a90: f4f1 605e 671a 5711 1845 8cfa 9956 dd3c  ..`^g.W..E...V.<
00003aa0: d79e 011b 9527 870c 82da 6a83 4a2c 97f2  .....'....j.J,..
00003ab0: 7e5d a98a 72d3 1423 8687 b009 c6d4 e6c9  ~]..r..#........
00003ac0: 1044 cd38 97df 757e 4fec c9f7 901a 8dc0  .D.8..u~O.......
00003ad0: 3534 1f25 6e65 1ec8 9ae5 59cd 117b 53d9  54.%ne....Y..{S.
00003ae0: f5ce 93b7 9225 c830 5781 8373 602f 31fa  .....%.0W..s`/1.
00003af0: 8849 e5b2 e97e 4099 3cac e87f f811 9acc  .I...~@.<.......
00003b00: 71ea 37bf d597 cae5 bf38 2411 c203 ce83  q.7......8$.....
00003b10: 1a2e 310e a648 9877 976d 12ae 1e3e e20e  ..1..H.w.m...>..
00003b20: fd57 bb87 6efb 157c f4e9 65f5 ee85 40be  .W..n..|..e...@.
00003b30: 754a 2844 4298 6b1f 1c3c e20c 6768 2299  uJ(DB.k..<..gh".
00003b40: 5fd3 d92c 35ab f0c4 05d2 6168 6214 551f  _..,5.....ahb.U.
00003b50: 66a9 8b29 8dc0 e900 e831 beb4 9156 06f4  f..).....1...V..
00003b60: 98e9 0c72 9ce2 4766 9b6f 1375 3b92 8814  ...r..Gf.o.u;...
00003b70: 7b1e 7ccf 3220 bfad 0ea6 d9da 587b 3ea2  {.|.2 ......X{>.
00003b80: 5976 69a9 f345 3650 dc14 5a6d 6a7a 3f7e  Yvi..E6P..Zmjz?~
00003b90: 6ab5 34fa 9492 7714 76f6 c2e2 ab18 22bf  j.4...w.v.....".
00003ba0: 06d3 ae6f e762 cad2 0b44 b60c f582 c1a3  ...o.b...D......
00003bb0: c2c3 2f4f 89e3 61d6 5d03 6c2c b0a5 fa58  ../O..a.].l,...X
00003bc0: cfba 788e eaac acba 87f1 b664 105b 4b3b  ..x........d.[K;
00003bd0: 2bc7 303f 463d 28ea 6156 828b aa1a b461  +.0?F=(.aV.....a
00003be0: fb5d 84e0 db53 8274 1bcd bec5 5093 8acd  .]...S.t....P...
00003bf0: a558 037f e65e e88b c584 391a 6f91 a39d  .X...^....9.o...
00003c00: bb2c 5a81 9bb8 20e3 617c e962 ffa2 d97b  .,Z... .a|.b...{
00003c10: 2b73 cfef e377 6fd5 0096 1e16 30d1 3c3e  +s...wo.....0.<>
00003c20: a4c9 51ed 9c28 9340 33e0 247b b407 0e0f  ..Q..(.@3.${....
00003c30: fe2e aeea b967 ae73 70ce 0ad2 92f0 764a  .....g.sp.....vJ
00003c40: a2fd 3120 8a24 2aa5 266c 1dab 4414 e533  ..1 .$*.&l..D..3
00003c50: f8bd 63a5 b978 f430 053f 2e57 7331 6f70  ..c..x.0.?.Ws1op
00003c60: 3ebe a96a 264c 4196 ef60 51f1 e536 43fd  >..j&LA..`Q..6C.
00003c70: 4ff6 b4ad ee24 3db1 56a4 db58 1223 ab4b  O....$=.V..X.#.K
00003c80: 5a73 7d76 fb95 ed81 6687 abd5 3edf d3f6  Zs}v....f...>...
00003c90: e23c 3ef8 a92c 5f89 9cd4 1314 3147 a429  .<>..,_.....1G.)
00003ca0: 5b68 b0bb 747d 3937 bbc9 6c9f dc80 8b7b  [h..t}97..l....{
00003cb0: 4a3c d5b1 e793 9364 424b 7fd6 f61a 06cf  J<.....dBK......
00003cc0: 979a e88d e8bf f13b caa1 aecc 4ecb 08bd  .......;....N...
00003cd0: 24e4 9fd2 69cd 5c83 768a 2625 fe72 12b5  $...i.\.v.&%.r..
00003ce0: ee37 eb2f a797 1793 9e94 06f4 12f1 f869  .7./...........i
00003cf0: 8c97 9a27 0c8c be9a 71ee 988e ba25 a34c  ...'....q....%.L
00003d00: 5271 609b eaa7 62f5 c7a8 af53 3810 3f6c  Rq`...b....S8.?l
00003d10: 7d5e b852 23a8 cbfa 40e8 cc74 7c3b 67ca  }^.R#...@..t|;g.
00003d20: 5c11 4038 3909 c5ac 45f8 58d9 41c2 d0ef  \.@89...E.X.A...
00003d30: 1313 5984 6e01 679a 61ba 85df a2c3 3b9d  ..Y.n.g.a.....;.
00003d40: e533 8ca8 4610 c6b9 d3c2 c8fc e9ab b3e9  .3..F...........
00003d50: ff22 6e25 c17f 59f7 f681 a613 bfbe 2e4b  ."n%..Y........K
00003d60: 2b94 1ad3 9a6e 8d8f 4112 533c 99fd 7c61  +....n..A.S<..|a
00003d70: 8e71 b6a1 2216 7fce a79f 64b1 7de2 c659  .q..".....d.}..Y
00003d80: f8a0 1ffd f7db 4ff2 173c 61e0 6c5c e1f7  ......O..<a.l\..
00003d90: ccad 2cf3 1c9e ee3e c1d3 a0d6 1ee2 d951  ..,....>.......Q
00003da0: f9ca 52e5 cdb6 87e0 a76c f3f0 848f a4b2  ..R......l......
00003db0: 8337 28f1 84a3 eef0 c6cd 8d18 a50c e274  .7(............t
00003dc0: cc62 3b4f be69 f957 23b0 6765 73fe ef2b  .b;O.i.W#.ges..+
00003dd0: 1949 1856 d691 fca3 6436 ba79 e4c5 4e71  .I.V....d6.y..Nq
00003de0: a9a9 ddcd 10fc 2967 9aef 78ee 5d21 74aa  ......)g..x.]!t.
00003df0: b6ca 75a4 27f8 f86f 5031 7097 8679 3328  ..u.'..oP1p..y3(
00003e00: c300 381d 4b2c 314f 930e 1480 fa8a 09c9  ..8.K,1O........
00003e10: 1df2 f107 9c07 90cd e7bc eb7d c023 6536  ...........}.#e6
00003e20: 49b3 470c e4f6 9152 61e0 340f a2f1 eabf  I.G....Ra.4.....
00003e30: 8456 957f 249e ba4f 07d9 b2df 35fd 7385  .V..$..O....5.s.
00003e40: 85e3 da3f 756f c144 41a1 6f19 ac0d 5abb  ...?uo.DA.o...Z.
00003e50: 815f 27cf d58c f54f 565e bc04 04e2 a8fd  ._'....OV^......
00003e60: 0980 af34 ec34 f52c af9d 5e0f da00 7bec  ...4.4.,..^...{.
00003e70: 65cd c476 245b f6a6 e0aa fb35 a69c fb47  e..v$[.....5...G
00003e80: bf48 074b ca8c a110 b488 816a 0520 4cbc  .H.K.......j. L.
00003e90: 577f 0d64 9606 dcd0 51f9 28e6 ad21 d98d  W..d....Q.(..!..
00003ea0: 9c83 8229 adfe c783 a70c 7a3c f40b f3cc  ...)......z<....
00003eb0: 10e5 c245 998e 026e 9444 e92e 4458 5f2f  ...E...n.D..DX_/
00003ec0: 3d83 fad8 546d 8935 27aa 8268 7f00 5b21  =...Tm.5'..h..[!
00003ed0: ceab 241f 733e 30d8 c8f2 8609 be82 00fd  ..$.s>0.........
00003ee0: 6b43 73eb 3bb9 65f4 e051 38f9 1f98 3f2b  kCs.;.e..Q8...?+
00003ef0: 2767 b2a7 ae62 657f 61e7 8412 d126 a1d6  'g...be.a....&..
00003f00: bc59 758d 6252 117a c03a a8e6 07cb a186  .Yu.bR.z.:......
00003f10: 2b4e 10ae 92cf b5b1 6650 5bc1 085b b719  +N......fP[..[..
00003f20: ed6a 500e 91bd 8b3d 5690 e42d 8ddc 5823  .jP....=V..-..X#
00003f30: 5214 28e8 007c fd47 214d b1fe c294 3d3d  R.(..|.G!M....==
00003f40: 3d3d 3d3d 3d3d 3d3d 2047 3777 384c 4969  ======== G7w8LIi
00003f50: 364a 336b 5462 3841 376a 394c 6772 7977  6J3kTb8A7j9Lgryw
00003f60: 7445 556c 7979 7036 730a 40a7 bb0b 7fd4  tEUlyyp6s.@.....
00003f70: 9e6c 55ef 6ebe 1c47 3c2a 011b 4812 93f3  .lU.n..G<*..H...
00003f80: edf2 b02c cd6a 51c9 28ec 53a0 3f55 d6b1  ...,.jQ.(.S.?U..
00003f90: 0e18 22d2 dfb3 3771 8340 60d2 585d e316  .."...7q.@`.X]..
00003fa0: bb72 b22f f138 7735 31bf 5f7e 7456 044f  .r./.8w51._~tV.O
00003fb0: 86ea d935 e406 a060 a24e d90c 683c dd2b  ...5...`.N..h<.+
00003fc0: 3097 9636 75a6 0f07 3d8e 7652 e5a7 332f  0..6u...=.vR..3/
00003fd0: 4281 c729 c6bc 4d3f 609a f456 c2ce b476  B..)..M?`..V...v
00003fe0: 97d5 1d5b 188b a8ae 4c66 0f43 904d 89c8  ...[....Lf.C.M..
00003ff0: 6ec5 1ffe b657 fc8f 1c62 81f0 690d fec2  n....W...b..i...
00004000: 1b89 9241 33fc 7f5b 3f78 9e9a e876 1271  ...A3..[?x...v.q
00004010: 0048 79eb 8fba e47b 1cfc 265d 5b2f c5ee  .Hy....{..&][/..
00004020: 8d98 dbbe ab98 c9b3 5058 035c 020f 990b  ........PX.\....
00004030: 1f67 a85d bea9 2df9 b2eb 9cca 15b2 f17b  .g.]..-........{
00004040: 0aa1 1900 8dae 948a 640f 232e 8658 554a  ........d.#..XUJ
00004050: c499 44c7 efb0 5e76 e83c e1a6 c09d dcb3  ..D...^v.<......
00004060: 25ef 2733 fd2b 71dd c961 4892 2671 93e8  %.'3.+q..aH.&q..
00004070: 3962 64e9 ec30 c069 be44 16b1 751c f931  9bd..0.i.D..u..1
00004080: f725 fa9c 6ec5 1b83 e260 2048 a667 8e98  .%..n....` H.g..
00004090: 2f93 ec68 0639 d0d0 b10b 63bd b429 2a0a  /..h.9....c..)*.
000040a0: 9ed8 9c7e 5619 a425 b532 a655 7924 1503  ...~V..%.2.Uy$..
000040b0: 481b 964b aef1 3cd5 3ed2 1797 a93e 5553  H..K..<.>....>US
000040c0: 5d62 c9c0 caba 06b0 53aa e99c da07 2221  ]b......S....."!
000040d0: c39e e71d 2595 73ef 39ff c575 5a96 2b2a  ....%.s.9..uZ.+*
000040e0: abb3 de3e ff17 bf57 4053 5b53 da02 f618  ...>...W@S[S....
000040f0: f913 acce b3d7 0f89 87c8 6049 c832 e683  ..........`I.2..
00004100: 7ade 8fc2 b08c 950e b656 e9ce 4084 b877  z........V..@..w
00004110: 26e7 aaf2 98dc 561a 9543 4aa0 b8b5 3eab  &.....V..CJ...>.
00004120: fe30 dd5d 4989 465c 7962 05c5 98d2 b8c1  .0.]I.F\yb......
00004130: 696d 3fa8 72ac 1c41 47a7 b881 cea7 4885  im?.r..AG.....H.
00004140: 1739 0ace e299 603c d4cf 836c 04d4 5d0c  .9....`<...l..].
00004150: 503b bd1c 96b0 e2bc e66a e865 9925 5f00  P;.......j.e.%_.
00004160: e819 5354 bdf2 8554 1747 6eae 244c 179b  ..ST...T.Gn.$L..
00004170: 1937 0247 e056 2f59 9959 f2ae 9f64 34a3  .7.G.V/Y.Y...d4.
00004180: e21f 6ec4 77c8 36a5 dff0 54d5 88fa a0e6  ..n.w.6...T.....
00004190: 7921 51f7 cfba e3eb 3d38 54b1 c4ff f2d7  y!Q.....=8T.....
000041a0: ef76 1a2b e75c 9ef6 f7cf a05e 36d1 ceb5  .v.+.\.....^6...
000041b0: 8563 4c87 13f1 3cb5 faa3 d4f0 8b99 9052  .cL...<........R
000041c0: 68b8 2cff d8f4 bdaa 9370 50b3 c476 c7ee  h.,......pP..v..
000041d0: 4747 7666 fb02 d0bb a416 e27b 6d5d d122  GGvf.......{m]."
000041e0: 15ae cfa9 fa1a c896 101b ca96 604f ea0c  ............`O..
000041f0: da40 9d8c 34b8 d662 6ff9 4520 b09d 70b6  .@..4..bo.E ..p.
00004200: 6970 d727 288f cf7c 48a2 79ff 4171 b37a  ip.'(..|H.y.Aq.z
00004210: 683b 6747 f37b bdea d9f7 658d e4c2 edd1  h;gG.{....e.....
00004220: beda 4717 9f72 ed23 7018 f996 708e abb4  ..G..r.#p...p...
00004230: 7149 ff5d 60d7 4be9 53f8 a7e3 233c 7b70  qI.]`.K.S...#<{p
00004240: 1c22 35da cce0 db4c 92cf 9859 6dd6 d10c  ."5....L...Ym...
00004250: 8b67 c533 cd0f fcf2 1290 7dc4 7fa5 004f  .g.3......}....O
00004260: cc86 1097 5bef 263e 3b03 033c b95c 0e96  ....[.&>;..<.\..
00004270: 7e9b d939 5a14 b0f4 8760 bde2 bb79 f2d0  ~..9Z....`...y..
00004280: 5825 83c6 de5b 263c dde2 fb11 4ca3 5791  X%...[&<....L.W.
00004290: 62d1 ab37 394f a5d8 d01e ef37 5417 112f  b..79O.....7T../
000042a0: a35b bd12 8568 be8c e040 9d96 a3f0 9a56  .[...h...@.....V
000042b0: 5b68 9d3d 5013 2515 0224 3870 bb8b 9088  [h.=P.%..$8p....
000042c0: 5c39 be18 48bc e3b9 31bf eb9f d0df 0d75  \9..H...1......u
000042d0: d794 6e60 63b3 79ca 68fb cd53 547b 4a33  ..n`c.y.h..ST{J3
000042e0: 8cf1 3865 622f 4abb 0b00 236e b04b a400  ..8eb/J...#n.K..
000042f0: 07cf d36f bff3 21a9 57d9 a819 1c24 2ade  ...o..!.W....$*.
00004300: 72a9 237a 58bb f93c edb9 1056 c464 3db8  r.#zX..<...V.d=.
00004310: 6b5e bf96 6ff4 9efa 66ab eb2e 572b a908  k^..o...f...W+..
00004320: 1c3d 8b7b 5f05 eaf2 1b39 687c 505d 8547  .=.{_....9h|P].G
00004330: 93b4 3390 90ca 2ced 3e41 0d62 936d e750  ..3...,.>A.b.m.P
00004340: f45b dbcb dc30 c6fe b0f9 f082 cd46 9354  .[...0.......F.T
00004350: 63c8 ae2d 84a9 17f0 05f2 6549 9710 1139  c..-......eI...9
00004360: 5730 92c1 6da0 37c8 17c1 ffb3 a8c0 12d9  W0..m.7.........
00004370: 1074 964c e59c a674 6f53 5c4c 82b4 4fdd  .t.L...toS\L..O.
00004380: 0018 0e14 7368 c844 6a32 cb87 03c9 5412  ....sh.Dj2....T.
00004390: 1ac7 23fc 4d9c 08f9 48c5 d52f 5a32 f9ee  ..#.M...H../Z2..
000043a0: 478b 6f52 f953 e01c d554 a645 55ef 144f  G.oR.S...T.EU..O
000043b0: 1e0c 6e7c 4eb6 0352 1a6e 967c 3ce8 6a69  ..n|N..R.n.|<.ji
000043c0: 98e9 6c6a faae ac5a fa42 dbe8 e379 3f86  ..lj...Z.B...y?.
000043d0: af9f 3652 8cba ae26 e547 d4f0 8298 63e8  ..6R...&.G....c.
000043e0: 3947 5f09 a41a 1239 a585 bb3d 9201 96a3  9G_....9...=....
000043f0: 692e b01a fd36 d764 7059 1c6d c742 c596  i....6.dpY.m.B..
00004400: dbbe af2d 4d48 1690 ec17 f79f 7f0d fd6f  ...-MH.........o
00004410: 345e 6370 eacd f2fa e113 133f 2830 0ce1  4^cp.......?(0..
00004420: 40fa f92c dae5 50b5 a5b9 4697 570f 08f9  @..,..P...F.W...
00004430: 3558 d217 fddb 562e ff41 10b3 54a3 b6af  5X....V..A..T...
00004440: d003 3fa7 d3d6 3c8f afd0 6813 8f74 7c4b  ..?...<...h..t|K
00004450: 25c2 c923 d60b 262b ffef b0b4 fce9 3f5c  %..#..&+......?\
00004460: 558f 372f 923d 7db1 326b 9305 c191 23bf  U.7/.=}.2k....#.
00004470: 428a 2d85 68a6 aa37 c6ba 7a55 8e01 6558  B.-.h..7..zU..eX
00004480: 6868 1bac 18f1 8b08 8f2c 01f2 99b5 5ff8  hh.......,...._.
00004490: 1795 d11b 7cc0 c456 7110 d91c 0dce 4f8a  ....|..Vq.....O.
000044a0: 30cf 7a36 53a8 4c17 09a1 ce45 2374 9615  0.z6S.L....E#t..
000044b0: e226 fb8a 2fb6 41d7 3e84 41e6 e4c5 0666  .&../.A.>.A....f
000044c0: 1f93 601b b714 dbdb 2b63 136c 9744 069d  ..`.....+c.l.D..
000044d0: d939 02ce 78f7 4231 92c6 5258 104f 71c7  .9..x.B1..RX.Oq.
000044e0: 8a55 b809 cf33 f04a 0ff1 7eb4 63b5 0130  .U...3.J..~.c..0
000044f0: 23b5 eb3c 35cb 3fec 9afd 9f9a 0365 e82a  #..<5.?......e.*
00004500: fa3b ee5f 1d45 1a95 1dd3 f8a4 c90b 2083  .;._.E........ .
00004510: e27d ef42 2374 4f0e 7761 aed2 a98b de5c  .}.B#tO.wa.....\
00004520: 973b 9a95 633b 77f5 da79 65d7 2586 c807  .;..c;w..ye.%...
00004530: 1076 8eb9 4b28 581a 9b02 1ca2 7fdb c3f1  .v..K(X.........
00004540: 0065 50bd 6a09 5ed6 5f48 9863 0d22 651b  .eP.j.^._H.c."e.
00004550: 8223 de07 6c18 ebe1 042b 3ae8 d31c 99df  .#..l....+:.....
00004560: be6a ecba be87 693b f2ee 3eed 2696 213b  .j....i;..>.&.!;
00004570: deda 0f7e 26b9 ae2b abd2 7d0e 37c4 8191  ...~&..+..}.7...
00004580: 26c8 bbf9 2d6b 1c22 2191 b56b a04e 259d  &...-k."!..k.N%.
00004590: ee3f b017 9197 264f 4561 5496 36b2 4543  .?....&OEaT.6.EC
000045a0: 9b74 056c b09e ebe8 a4c4 2ceb 2d82 97a6  .t.l......,.-...
000045b0: 4196 5b11 ff0b 87f8 95fb 40dc 24a1 8ad6  A.[.......@.$...
000045c0: d3e3 b60c b6dc 9570 9c0a e3be 940c d0d1  .......p........
000045d0: 2750 04e2 15aa d952 612f cac6 6fe7 3fd0  'P.....Ra/..o.?.
000045e0: 8c9a baec 3fd9 1b56 7275 9b62 0e73 492d  ....?..Vru.b.sI-
000045f0: 51e5 08a2 b56d bb47 d783 3d2e 5ffa 27ff  Q....m.G..=._.'.
00004600: edb2 8c94 bf2e aaed 91f0 2c74 78e1 fedd  ..........,tx...
00004610: f117 9e0a a69b 36b2 1d16 96b6 35ad 164e  ......6.....5..N
00004620: bf2b df76 0dd4 b46a 27b3 812b 5d21 646c  .+.v...j'..+]!dl
00004630: e7f0 e072 3304 b71d 1ba2 eb50 802c d198  ...r3......P.,..
00004640: a119 bc71 f233 6949 2837 d8aa fb68 da9f  ...q.3iI(7...h..
00004650: 2eb8 6db1 6a5f 3a58 6853 3eb8 9207 a981  ..m.j_:XhS>.....
00004660: b068 62fd 6a87 7742 c354 1fc7 7cbf 245e  .hb.j.wB.T..|.$^
00004670: 6326 f6cc 100c b9db 90bd 6f31 2b05 becb  c&........o1+...
00004680: 1268 5019 b4b9 7719 25e0 3b11 65ae 7fea  .hP...w.%.;.e...
00004690: bea8 58bb b54d a32d 428e c988 448c 5936  ..X..M.-B...D.Y6
000046a0: c762 c859 7f61 a8bd fcb0 763a 9567 f989  .b.Y.a....v:.g..
000046b0: 0f3e 2ee3 5ef7 d1c7 56eb afe5 a673 47cb  .>..^...V....sG.
000046c0: 6923 4639 b540 3b33 4198 21c8 1767 bc5b  i#F9.@;3A.!..g.[
000046d0: 2514 de9d 497d df24 875b ac1d 6448 c3e0  %...I}.$.[..dH..
000046e0: 8a94 1c22 6670 9e11 1ae4 adc8 4c33 0392  ..."fp......L3..
000046f0: e581 49c2 9098 9e22 3028 66d4 50c5 01ee  ..I...."0(f.P...
00004700: 71e3 230c b0c1 fd26 93b1 cd29 1133 0a9b  q.#....&...).3..
00004710: 1f3c 0a50 7dfc 1376 75f5 a3a6 14c2 4d8f  .<.P}..vu.....M.
00004720: e2a4 571b fad6 4127 e4fa 829a 1727 4de6  ..W...A'.....'M.
00004730: c035 5730 3644 bd47 e96c 8caa 4f59 12f2  .5W06D.G.l..OY..
00004740: d6a4 804d f5bd 8d44 e8c2 f7c5 e960 639b  ...M...D.....`c.
00004750: 6b96 52f0 ae0c 0ba6 3e0f d703 82a5 81c6  k.R.....>.......
00004760: c55e ca7f 7f60 785a 841c ae93 f48b af99  .^...`xZ........
00004770: 9ffd 87ec 3486 fd48 eadd e2a4 6d63 1531  ....4..H....mc.1
00004780: db67 60a6 9a42 e58c dd54 2b97 492a 6980  .g`..B...T+.I*i.
00004790: f492 cab2 0337 e109 f419 577b 4bf8 fc9d  .....7....W{K...
000047a0: 19b4 cad4 acfa a7f3 6664 e62b 62fa d705  ........fd.+b...
000047b0: 82c7 3f34 5d05 6ce7 3ed3 dbd4 54bc 2261  ..?4].l.>...T."a
000047c0: b0f4 4c35 8dfb a4f7 c708 7f52 f32d 8ecf  ..L5.......R.-..
000047d0: cae2 a0ad 39e7 d3f2 049a bc97 63f8 8b9a  ....9.......c...
000047e0: 452c ca63 da62 c413 22c3 3fec 9ec3 5418  E,.c.b..".?...T.
000047f0: 8043 a8a2 d1b9 fe2e 4877 c32b 8715 e2bd  .C......Hw.+....
00004800: 99df 945a 2eeb eb2f 442d c284 2dfa 6db9  ...Z.../D-..-.m.
00004810: 7e4c 4116 1f22 4a9c 8d73 9dac ebcc e9e6  ~LA.."J..s......
00004820: e456 a993 6e1c ce2d add4 fda9 4a92 c3c3  .V..n..-....J...
00004830: 1aef 8249 b3ed 2fa3 9237 bf7b aa38 8472  ...I../..7.{.8.r
00004840: 37e8 41d1 0ce1 6ed5 3b53 5fe4 b705 236e  7.A...n.;S_...#n
00004850: 0fc7 ea4f b625 049c bf8e adfb 87d3 e960  ...O.%.........`
00004860: 0189 da82 81b1 69d0 f581 7f1e 7bf2 29e5  ......i.....{.).
00004870: 6051 c22f 06d0 6770 55f6 d845 b542 e508  `Q./..gpU..E.B..
00004880: 243a a2f1 ee6b 6abf 713b b934 cd05 e662  $:...kj.q;.4...b
00004890: 354e ae2a c165 7738 cf08 eec1 e722 7590  5N.*.ew8....."u.
000048a0: 7a67 dfc2 bdd4 ea6f a8dc ca9b e5e4 1866  zg.....o.......f
000048b0: c309 dfbe 124d c3ae 327a e057 b3c6 f136  .....M..2z.W...6
000048c0: aa97 3f78 f10c 059c 5a14 1ee5 43f7 246c  ..?x....Z...C.$l
000048d0: 94c0 d258 58b7 1a12 766f 8878 9707 d616  ...XX...vo.x....
000048e0: e0c0 18ae b3be 6fb0 dc3e b264 4ed3 b376  ......o..>.dN..v
000048f0: 3c87 94d0 fc36 06fe 7ad5 d296 7ce0 29e6  <....6..z...|.).
00004900: a040 a94a 0852 4a58 f3b1 0c32 776f 657d  .@.J.RJX...2woe}
00004910: 13f2 d4d4 31e0 2d15 95bf 647b 5246 a7e6  ....1.-...d{RF..
00004920: ae78 c718 d2b7 ba97 f2d9 3801 c978 412f  .x........8..xA/
00004930: 5d20 213f 6895 48a9 2906 72f0 c4eb a19a  ] !?h.H.).r.....
00004940: d5c9 6085 bc73 cc5b 4b9a c793 1d79 9fbb  ..`..s.[K....y..
00004950: 336f 0abd ae19 bbeb 213c 2fce ef7f 0986  3o......!</.....
00004960: de25 5bea 58d8 1b0c 31d2 864f ab05 1c95  .%[.X...1..O....
00004970: 5cd0 7b9c 58ee 7b79 2fb8 2d71 fd22 adcb  \.{.X.{y/.-q."..
00004980: ce05 f3fb d5df 12fc e18a 7d5c 7576 6eaa  ..........}\uvn.
00004990: 5702 91be a227 391e fb3a 0b0d a9d7 4361  W....'9..:....Ca
000049a0: db68 6ce7 b078 6f64 5460 8d30 8c64 5c27  .hl..xodT`.0.d\'
000049b0: c669 ef73 07aa a809 b43e 5e10 8288 27f4  .i.s.....>^...'.
000049c0: d810 e135 09ee c649 26be f7b6 45b5 318b  ...5...I&...E.1.
000049d0: 7469 8013 6533 57f4 3d7e c09b 3651 af65  ti..e3W.=~..6Q.e
000049e0: 9a59 81d2 4060 4003 342e c551 0acb 177f  .Y..@`@.4..Q....
000049f0: ac9e ebb8 bee8 f7bd c670 2524 94b4 f5d2  .........p%$....
00004a00: e7b2 d50c ed49 cbb5 050d 5f53 e02d 2d17  .....I...._S.--.
00004a10: c429 8e2f fa48 933f 3f58 1c09 a0c6 3ea1  .)./.H.??X....>.
00004a20: 1294 8f8a 6a7f 7ec0 9601 f0b4 1add bcf8  ....j.~.........
00004a30: 280b 56bd 4519 6554 2ac8 d4e2 9032 e1a7  (.V.E.eT*....2..
00004a40: 121e 9344 5f0e a5d5 f9ba f788 798a 2870  ...D_.......y.(p
00004a50: e3de 014e 08fb 9eb3 41db 7070 7b0d b964  ...N....A.pp{..d
00004a60: 96fa a22f bc35 a2a3 4095 8a6d fc66 0ebc  .../.5..@..m.f..
00004a70: cb59 1f18 2949 a58a 1e28 a022 aeb2 23f5  .Y..)I...(."..#.
00004a80: 6b06 4662 70a0 1e5a 5626 0c49 c5ec 8f95  k.Fbp..ZV&.I....
00004a90: ae34 734a 2c7c 453f 1e9f 4959 1e74 3aa8  .4sJ,|E?..IY.t:.
00004aa0: 4aa5 03c2 1618 7f94 9c54 4c68 590c cddc  J........TLhY...
00004ab0: 6de6 d65b 3b04 ea16 c12f 67a5 ba84 54ca  m..[;..../g...T.
00004ac0: e61a 4745 c2b7 bb69 6f4b 0a9d 7898 8e82  ..GE...ioK..x...
00004ad0: fbfa 190b 7d6e 8d37 5ca5 8b0c e763 f097  ....}n.7\....c..
00004ae0: e99a 8c4b 8673 7a1d 8eca bfc5 45a4 dba1  ...K.sz.....E...
00004af0: 2eb6 a532 3cfa 1a00 4a44 af76 8e21 b04c  ...2<...JD.v.!.L
00004b00: fbf4 d7cb 0791 17b3 ecf9 f7d9 7ae2 f311  ............z...
00004b10: 8402 ba45 e3e4 20ee 6415 1c33 212a 55e1  ...E.. .d..3!*U.
00004b20: ef1e 53ea ceb8 9f62 e001 9d1d a4b6 d00b  ..S....b........
00004b30: cefa aee4 d625 33c0 c2d4 d39b b216 2dbb  .....%3.......-.
00004b40: dc54 7640 a117 b29c 2a61 1fcd 7a17 113b  .Tv@....*a..z..;
00004b50: 5b1c 7c82 fd02 2c10 86e0 6506 e05c cd29  [.|...,...e..\.)
00004b60: 2ea9 fa87 7a07 7905 52c2 bb45 a15b 97a5  ....z.y.R..E.[..
00004b70: 5d93 af2d c0c3 f4c1 5c3d 991f a7de c861  ]..-....\=.....a
00004b80: 7d9d 0b77 4cfd 70a1 89e1 c565 d06d bab3  }..wL.p....e.m..
00004b90: daaf 5acc e148 4cce 6961 f44b a72e df35  ..Z..HL.ia.K...5
00004ba0: bf73 728b 6449 1a07 2697 14ac 25be 75ef  .sr.dI..&...%.u.
00004bb0: 6369 74                                  cit
```
Here, we see that the file is in much better condition now.<br />
Let's see where the '=' sign is and let's take 5 of them, because it's given in the statement that the password is preceeded by several '=' signs and by using single '=' we can mess up as there are other lines too where a single or double '=' is present.<br />
And let's also given the line numbers using the 'nl' command (because it would be useful if the password is split in multiple lines):
```bash
bandit9@bandit:~$ xxd data.txt | nl | grep =====
    71	00000460: bfad 663d 3d3d 3d3d 3d3d 3d3d 3d20 7468  ..f========== th
   332	000014b0: 3d3d 3d3d 3d3d 3d20 7061 7373 776f 7264  ======= password
   437	00001b40: 26ef 3d3d 3d3d 3d3d 3d3d 3d3d 2069 7318  &.========== is.
  1013	00003f40: 3d3d 3d3d 3d3d 3d3d 2047 3777 384c 4969  ======== G7w8LIi
```
It seems like the hexdump of the first 3 lines are trying to say that 'the password is ..'<br />
And then there are many '=' signs before a string in the 4th line that seems like a password.<br />
So, let's display those lines till we get the full password.
```bash
bandit9@bandit:~$ xxd data.txt | nl | grep 1013
   519	00002060: b266 930d fa61 b268 81bc 9a05 cdf5 1013  .f...a.h........
  1013	00003f40: 3d3d 3d3d 3d3d 3d3d 2047 3777 384c 4969  ======== G7w8LIi
bandit9@bandit:~$ xxd data.txt | nl | grep 1014
  1014	00003f50: 364a 336b 5462 3841 376a 394c 6772 7977  6J3kTb8A7j9Lgryw
bandit9@bandit:~$ xxd data.txt | nl | grep 1015
  1015	00003f60: 7445 556c 7979 7036 730a 40a7 bb0b 7fd4  tEUlyyp6s.@.....
```
Here, we got the password for the Level 10 of Bandit in 3 different lines.<br />
So, our purpose is complete. Let's logout from the server using the 'exit' command
```bash
bandit9@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
<br />
Password for Level 10 = G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
