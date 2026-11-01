## Descripcion
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag. Download the jpg image [here](https://challenge-files.cylabacademy.net/library/6618af1eb2daf007cb7b54d1213093d4dd2801941619b236580ebe3b738dea7b/img.jpg).
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ wget https://challenge-files.cylabacademy.net/library/6618af1eb2daf007cb7b54d1213093d4dd2801941619b236580ebe3b738dea7b/img.jpg
--2026-10-31 19:46:58--  https://challenge-files.cylabacademy.net/library/6618af1eb2daf007cb7b54d1213093d4dd2801941619b236580ebe3b738dea7b/img.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 54.239.180.124, 54.239.180.73, 54.239.180.120, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|54.239.180.124|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73515 (72K) [application/octet-stream]
Saving to: ‘img.jpg’

img.jpg            100%[================>]  71.79K   395KB/s    in 0.2s

2026-10-31 19:47:01 (395 KB/s) - ‘img.jpg’ saved [73515/73515]


┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ exiftool img.jpg
ExifTool Version Number         : 13.55
File Name                       : img.jpg
Directory                       : .
File Size                       : 74 kB
File Modification Date/Time     : 2026:09:22 23:38:56-06:00
File Access Date/Time           : 2026:10:31 19:47:01-06:00
File Inode Change Date/Time     : 2026:10:31 19:47:01-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Comment                         : c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9
Image Width                     : 640
Image Height                    : 640
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 640x640
Megapixels                      : 0.410

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ echo 'c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9' | base64 -d; echo
steghide:cEF6endvcmQ=

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ echo 'cEF6endvcmQ=' | base64 -d; echo
pAzzword

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ steghide extract -sf img.jpg -p pAzzword
wrote extracted data to "flag.txt".

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ cat flag.txt
academy{h1dd3n_1n_1m4g3_d0c4a4e2}
```
## Notas adicionales
## Referencias
