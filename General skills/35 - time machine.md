## Descripcion
What was I last working on? I remember writing a note to help me remember...
## Solucion

```
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/67/challenge.zip
--2026-08-29 22:53:37--  https://artifacts.picoctf.net/c_titan/67/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17743 (17K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                         100%[=========================================================================>]  17.33K  --.-KB/s    in 0.005s  

2026-08-29 22:53:37 (3.69 MB/s) - 'challenge.zip' saved [17743/17743]

celeh127-academy@webshell:~$ unzip -q challenge.zip
celeh127-academy@webshell:~$ cd drop-in
celeh127-academy@webshell:~/drop-in$ git log
celeh127-academy@webshell:~/drop-in$ 

commit b92bdd8ec87a21ba45e77bd9bed3e4893faafd0f (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:29 2024 +0000

```
    picoCTF{t1m3m@ch1n3_5cde9075}
(END)


## Notas adicionales
## Referencias
