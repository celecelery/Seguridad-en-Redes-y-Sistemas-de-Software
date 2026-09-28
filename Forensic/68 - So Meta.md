## Descripcion
Find the flag in this [picture](https://challenge-files.cylabacademy.net/library/c0f3e512631112c251ffec94d2ffd27689fccdde3f8ee08fae4b0c05b25aa818/pico_img.png).
## Solucion
```

┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/c0f3e512631112c251ffec94d2ffd27689fccdde3f8ee08fae4b0c05b25aa818/pico_img.png


pico_img.png                  100%[=================================================>] 106.25K   479KB/s    in 0.2s

2026-09-28 10:44:43 (479 KB/s) - ‘pico_img.png’ saved [108795/108795]


┌──(celesteh㉿K-Celeste)-[~]
└─$ exiftool pico_img.png
ExifTool Version Number         : 13.55
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2026:09:22 19:49:11-06:00
File Access Date/Time           : 2026:09:28 10:44:43-06:00
File Inode Change Date/Time     : 2026:09:28 10:44:43-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : academy{s0_m3ta_b9d1ec99}
Image Size                      : 600x600
Megapixels                      : 0.360

┌──(celesteh㉿K-Celeste)-[~]
└─$ exiftool pico_img.png | grep academy
Artist                          : academy{s0_m3ta_b9d1ec99}
```

 flag: academy{s0_m3ta_b9d1ec99}
## Notas adicionales
## Referencias