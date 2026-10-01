## Descripcion
Decode this [message](https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav) from the moon.
## Solucion

```
┌──(celesteh㉿K-Celeste)-[~/moonwalk]
└─$ wget https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav

┌──(moon)(celesteh㉿K-Celeste)-[~/moonwalk]
└─$ sstv -d message.wav -o flag.png
[sstv] Searching for calibration header... Found!
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [######################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

┌──(moon)(celesteh㉿K-Celeste)-[~/moonwalk]
└─$ open flag.png

```
flag: picoCTF{beep_boop_im_in_space}
## Notas adicionales
## Referencias
uso del repositorio sstv
 https://github.com/colaclanth/sstv.git