## Descripcion
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...
## Solucion
```
celeh127-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/5a478d0b24d6a4f4185e3adb7a78c41cdad626fb02fe80e083dc33bf8b197d3d/warm
--2026-08-24 16:43:51--  https://challenge-files.picoctf.net/c_wily_courier/5a478d0b24d6a4f4185e3adb7a78c41cdad626fb02fe80e083dc33bf8b197d3d/warm
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.40, 3.160.5.18, 3.160.5.64, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19312 (19K) [application/octet-stream]
Saving to: 'warm'

warm                 100%[===================>]  18.86K  --.-KB/s    in 0.001s  

2026-08-24 16:43:51 (17.9 MB/s) - 'warm' saved [19312/19312]

celeh127-academy@webshell:~$ chmod +x warm
celeh127-academy@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
celeh127-academy@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
celeh127-academy@webshell:~$ 

```
## Notas adicionales
chmod +x agreaga permisos de ejecucion a un binario en linux
./warm ejecuta el binario warm una vez que ya tiene los permisos de ejecucion
.elf es el formato de archivo ejecutable en linux equivalente a .exe
file permite saber de que tipo es un archivo
## Referencias
