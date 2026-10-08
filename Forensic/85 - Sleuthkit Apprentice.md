## Descripcion
Download this disk image and find the flag.
Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ wget https://challenge-files.cylabacademy.net/library/162bc8bf6dd1abbc5269c16570e170277369a39cf46bdd8d99443e136fabcc5f/disk.flag.img.gz
--2026-10-07 11:15:29--  https://challenge-files.cylabacademy.net/library/162bc8bf6dd1abbc5269c16570e170277369a39cf46bdd8d99443e136fabcc5f/disk.flag.img.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.115, 18.238.132.49, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 47534528 (45M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz              100%[=================================================>]  45.33M   339KB/s    in 92s

2026-10-07 11:17:02 (507 KB/s) - ‘disk.flag.img.gz’ saved [47534528/47534528]


┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ ls -lah
total 46M
drwxr-xr-x  2 celesteh celesteh 4.0K Oct  7 11:15 .
drwx------ 13 celesteh celesteh 4.0K Oct  7 11:15 ..
-rw-r--r--  1 celesteh celesteh  46M Sep 22 20:59 disk.flag.img.gz

┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ gzip disk.flag.img.gz
gzip: disk.flag.img.gz already has .gz suffix -- unchanged

┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ gzip -d disk.flag.img.gz

┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ mmls disk.flag.img.gz
Error stat(ing) image file (raw_open: image "disk.flag.img.gz" - No such file or directory)

┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)

┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ fls -o 360448 -r disk.flag.img 1995
r/r 2363:       .ash_history
d/d 3981:       my_folder
+ r/r * 2082(realloc):  flag.txt
+ r/r 2371:     flag.uni.txt

┌──(celesteh㉿K-Celeste)-[~/apprentice]
└─$ icat -o 360448 -r disk.flag.img 2371
academy{by73_5urf3r_85e9b307}
```
## Notas adicionales
## Referencias