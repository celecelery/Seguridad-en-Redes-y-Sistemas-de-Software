## Descripcion
This file contains more than it seems. Get the flag from [garden.jpg](https://challenge-files.cylabacademy.net/library/3c60c5a7f7a8067606c51d4b4b3c7913fae709b11e2f2c7adbc0a0b4cda452ff/garden.jpg).
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/3c60c5a7f7a8067606c51d4b4b3c7913fae709b11e2f2c7adbc0a0b4cda452ff/garden.jpg

2026-09-28 10:30:57 (1.21 MB/s) - ‘garden.jpg’ saved [2295191/2295191]


┌──(celesteh㉿K-Celeste)-[~]
└─$ strings -n 10 garden.jpg | grep academy
Here is a flag: academy{more_than_m33ts_the_3y3ff3b9e86}

```

flag: academy{more_than_m33ts_the_3y3ff3b9e86}
## Notas adicionales
## Referencias
