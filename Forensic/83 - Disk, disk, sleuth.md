## Descripcion
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image. [dds1-alpine.flag.img.gz](https://challenge-files.cylabacademy.net/library/0e33413e7b309ae38964211ca09f5c86005b6fe4f2cc95b75ad5b482d98a2d76/dds1-alpine.flag.img.gz)
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/sleuthdisk]
└─$ wget https://challenge-files.cylabacademy.net/library/0e33413e7b309ae38964211ca09f5c86005b6fe4f2cc95b75ad5b482d98a2d76/dds1-alpine.flag.img.gz
--2026-10-07 10:57:07--  https://challenge-files.cylabacademy.net/library/0e33413e7b309ae38964211ca09f5c86005b6fe4f2cc95b75ad5b482d98a2d76/dds1-alpine.flag.img.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.49, 18.238.132.88, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29768910 (28M) [application/octet-stream]
Saving to: ‘dds1-alpine.flag.img.gz’

dds1-alpine.flag.img.gz       100%[=================================================>]  28.39M  6.33MB/s    in 4.6s

2026-10-07 10:57:12 (6.11 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768910/29768910]


┌──(celesteh㉿K-Celeste)-[~/sleuthdisk]
└─$ gzip -d dds1-alpine.flag.img.gz

┌──(celesteh㉿K-Celeste)-[~/sleuthdisk]
└─$ file dds1-alpine.flag.img.gz
dds1-alpine.flag.img.gz: cannot open `dds1-alpine.flag.img.gz' (No such file or directory)

┌──(celesteh㉿K-Celeste)-[~/sleuthdisk]
└─$ ls -lah
total 129M
drwxr-xr-x  2 celesteh celesteh 4.0K Oct  7 10:58 .
drwx------ 13 celesteh celesteh 4.0K Oct  7 10:56 ..
-rw-r--r--  1 celesteh celesteh 128M Sep 22 20:21 dds1-alpine.flag.img

┌──(celesteh㉿K-Celeste)-[~/sleuthdisk]
└─$ file dds1-alpine.flag.img
dds1-alpine.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0x10,81,1), startsector 2048, 260096 sectors

┌──(celesteh㉿K-Celeste)-[~/sleuthdisk]
└─$ srch_strings dds1-alpine.flag.img | grep academy
  SAY academy{f0r3ns1c4t0r_n30phyt3_6502313d}
```
## Notas adicionales
## Referencias