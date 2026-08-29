## Descripcion
Someone's commits seems to be preventing the program from working. Who is it?
## Solucion
```
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/159/challenge.zip
--2026-08-29 22:57:59--  https://artifacts.picoctf.net/c_titan/159/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.64, 3.160.5.95, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 293915 (287K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                         100%[=========================================================================>] 287.03K  1.84MB/s    in 0.2s    

2026-08-29 22:57:59 (1.84 MB/s) - 'challenge.zip' saved [293915/293915]

celeh127-academy@webshell:~$ unzip -q challenge.zip
celeh127-academy@webshell:~$ cd drop-in
celeh127-academy@webshell:~/drop-in$ git log
celeh127-academy@webshell:~/drop-in$ git log --pretty=format:"%an <%ae>" | grep picoCTF
picoCTF <ops@picoctf.com>
picoCTF <ops@picoctf.com>
picoCTF <ops@picoctf.com>
picoCTF{@sk_th3_1nt3rn_81e716ff} <ops@picoctf.com>
picoCTF <ops@picoctf.com>

```
## Notas adicionales
## Referencias
