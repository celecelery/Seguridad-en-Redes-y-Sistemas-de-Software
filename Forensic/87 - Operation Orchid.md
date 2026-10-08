## Descripcion
Download this disk image, find the key and log into the remote machine.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/last]
└─$ wget https://challenge-files.cylabacademy.net/library/8af34b0fa863a6efa03d28278ca270b335291ad998f21c3696889bdc9c77ab72/disk.img.gz

2026-10-07 18:47:16 (27.9 MB/s) - ‘disk.img.gz’ saved [48132743/48132743]


┌──(celesteh㉿K-Celeste)-[~/last]
└─$ gzip -d disk.img.gz

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ fls -o 206847 disk.img
Cannot determine file system type

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ fls -o 206848 disk.img
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ fls -o 206848 disk.img 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ icat -o 206848 disk.img 2345 > ssh_key

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ cat ssh_key
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ chmod 600 ssh_key

┌──(celesteh㉿K-Celeste)-[~/last]
└─$ ssh -i ssh_key -p 10844 ctf-player@chatelaine.cylabacademy.net
Welcome to Ubuntu 24.04.4 LTS (GNU/Linux 7.0.0-1014-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
academy{k3y_5l3u7h_0e000cd7}ctf-player@challenge:~$ Connection to chatelaine.cylabacademy.net closed by remote host.
Connection to chatelaine.cylabacademy.net closed.

```

flag: academy{k3y_5l3u7h_0e000cd7}
## Notas adicionales
## Referencias