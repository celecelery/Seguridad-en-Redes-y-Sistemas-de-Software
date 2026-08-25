## Descripcion
Can you make sense of this file?
## Solucion

celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c/472/enc_flag
--2026-08-25 00:29:28--  https://artifacts.picoctf.net/c/472/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag             100%[===================>]     349  --.-KB/s    in 0s      

2026-08-25 00:29:28 (160 MB/s) - 'enc_flag' saved [349/349]

celeh127-academy@webshell:~$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_73494190}
celeh127-academy@webshell:~$ 

## Notas adicionales
## Referencias