## Descripcion
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log. Download the encoded data here: [Logs Data](https://challenge-files.cylabacademy.net/library/0246cbed3fe2edb81de38ddfb60f948020c30448c0c21fcd82cee316fb9da111/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial .
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ wget https://challenge-files.cylabacademy.net/library/0246cbed3fe2edb81de38ddfb60f948020c30448c0c21fcd82cee316fb9da111/logs.txt
--2026-10-31 19:55:37--  https://challenge-files.cylabacademy.net/library/0246cbed3fe2edb81de38ddfb60f948020c30448c0c21fcd82cee316fb9da111/logs.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 54.239.180.124, 54.239.180.73, 54.239.180.120, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|54.239.180.124|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1592148 (1.5M) [application/octet-stream]
Saving to: ‘logs.txt’

logs.txt           100%[================>]   1.52M  2.54MB/s    in 0.6s

2026-10-31 19:55:38 (2.54 MB/s) - ‘logs.txt’ saved [1592148/1592148]


┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ base64 -d logs.txt > salida

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ file salida
salida: PNG image data, 896 x 1152, 8-bit/color RGB, non-interlaced

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ mv salida salida.png

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ xdg-open salida.png

┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ echo '61636164656D797B666F72656E736963735F616E616C797369735F69735F616D617A696E675F38646264333133337D' | xxd -r -p; echo
academy{forensics_analysis_is_amazing_8dbd3133}
```
## Notas adicionales
## Referencias
