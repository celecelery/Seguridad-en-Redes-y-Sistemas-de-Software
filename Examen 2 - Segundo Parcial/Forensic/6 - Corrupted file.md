## Descripcion
This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life? Download the file [here](https://challenge-files.cylabacademy.net/library/217bef66dcb5fd0797e1c0f064b705a73600a8be2e1ebadeab51df5be013109d/file).

## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ wget https://challenge-files.cylabacademy.net/library/217bef66dcb5fd0797e1c0f064b705a73600a8be2e1ebadeab51df5be013109d/file
--2026-10-31 20:00:47--  https://challenge-files.cylabacademy.net/library/217bef66dcb5fd0797e1c0f064b705a73600a8be2e1ebadeab51df5be013109d/file
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 54.239.180.124, 54.239.180.73, 54.239.180.126, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|54.239.180.124|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8783 (8.6K) [application/octet-stream]
Saving to: ‘file’

file               100%[================>]   8.58K  --.-KB/s    in 0s

2026-10-31 20:00:50 (28.4 MB/s) - ‘file’ saved [8783/8783]


┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ file file
file: data

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ xxd archivo | head
xxd: archivo: No such file or directory

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ xxd file | head
00000000: 5c78 ffe0 0010 4a46 4946 0001 0100 0001  \x....JFIF......
00000010: 0001 0000 ffdb 0043 0008 0606 0706 0508  .......C........
00000020: 0707 0709 0908 0a0c 140d 0c0b 0b0c 1912  ................
00000030: 130f 141d 1a1f 1e1d 1a1c 1c20 242e 2720  ........... $.'
00000040: 222c 231c 1c28 3729 2c30 3134 3434 1f27  ",#..(7),01444.'
00000050: 393d 3832 3c2e 3334 32ff db00 4301 0909  9=82<.342...C...
00000060: 090c 0b0c 180d 0d18 3221 1c21 3232 3232  ........2!.!2222
00000070: 3232 3232 3232 3232 3232 3232 3232 3232  2222222222222222
00000080: 3232 3232 3232 3232 3232 3232 3232 3232  2222222222222222
00000090: 3232 3232 3232 3232 3232 3232 3232 ffc0  22222222222222..

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ printf '\xff\xd8' | dd of=file bs=1 seek=0 count=2 conv=notrunc
2+0 records in
2+0 records out
2 bytes copied, 0.000198428 s, 10.1 kB/s

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ xxd file | head -n 1
00000000: ffd8 ffe0 0010 4a46 4946 0001 0100 0001  ......JFIF......

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ file file
file: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 800x500, components 3

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ mv file fixed.jpg

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ xdg-open fixed.jpg
```
## Notas adicionales
## Referencias
