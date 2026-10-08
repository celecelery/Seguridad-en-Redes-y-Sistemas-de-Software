## Descripcion
Download this disk image and find the flag.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ wget https://challenge-files.cylabacademy.net/library/7d645367284f9df9139dd5ad212e5c3bd0815b7674ca700648a3983158394892/disk.flag.img.gz
--2026-10-07 11:35:00--  https://challenge-files.cylabacademy.net/library/7d645367284f9df9139dd5ad212e5c3bd0815b7674ca700648a3983158394892/disk.flag.img.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.88, 18.238.132.115, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360921 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz              100%[=================================================>]  42.31M   746KB/s    in 33s

2026-10-07 11:35:34 (1.27 MB/s) - ‘disk.flag.img.gz’ saved [44360921/44360921]


┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ ls
disk.flag.img.gz

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ gzip -d disk.flag.img.gz

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ fls -o 411648 disk.flag.img -r | grep flag
+ r/r * 1876(realloc):  flag.txt
+ r/r 1782:     flag.txt.enc

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ fls -o 411648 disk.flag.img -r | grep flag -A 2 -B 2
d/d 472:        root
+ r/r 1875:     .ash_history
+ r/r * 1876(realloc):  flag.txt
+ r/r 1782:     flag.txt.enc
d/d 473:        run
d/d 475:        srv

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ icat -o 411648 disk.flag.img 1782 > flag.txt.enc

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ file flag.txt.enc
flag.txt.enc: openssl enc'd data with salted password

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ icat -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt
apk get nano
apk --help
apk add nano
nano flag.txt
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ openssl aes256 -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567 -d
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
4037E3E470700000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:

┌──(celesteh㉿K-Celeste)-[~/orchid]
└─$ cat flag.txt
academy{h4un71ng_p457_718ebd29}
```
## Notas adicionales
## Referencias