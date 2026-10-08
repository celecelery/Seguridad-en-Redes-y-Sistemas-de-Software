## Descripcion
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/sleuth]
└─$ wget https://challenge-files.cylabacademy.net/library/d8718cbbc14dcd9f9aad532a51d7a01b00e1715ca3b1d654dfef687d0b15cbf5/disk.img.gz
--2026-10-07 11:07:55--  https://challenge-files.cylabacademy.net/library/d8718cbbc14dcd9f9aad532a51d7a01b00e1715ca3b1d654dfef687d0b15cbf5/disk.img.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.26, 18.238.132.49, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29714372 (28M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                   100%[=================================================>]  28.34M   427KB/s    in 3m 4s

2026-10-07 11:11:00 (157 KB/s) - ‘disk.img.gz’ saved [29714372/29714372]


┌──(celesteh㉿K-Celeste)-[~/sleuth]
└─$ ls -lah
total 29M
drwxr-xr-x  2 celesteh celesteh 4.0K Oct  7 11:07 .
drwx------ 13 celesteh celesteh 4.0K Oct  7 11:07 ..
-rw-r--r--  1 celesteh celesteh  29M Sep 22 20:52 disk.img.gz


┌──(celesteh㉿K-Celeste)-[~/sleuth]
└─$ gzip disk.img.gz
gzip: disk.img.gz already has .gz suffix -- unchanged

┌──(celesteh㉿K-Celeste)-[~/sleuth]
└─$ gzip -d disk.img.gz

┌──(celesteh㉿K-Celeste)-[~/sleuth]
└─$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)

┌──(celesteh㉿K-Celeste)-[~/sleuth]
└─$ nc xebec.cylabacademy.net 25039
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
academy{mm15_f7w!}

```
## Notas adicionales
## Referencias