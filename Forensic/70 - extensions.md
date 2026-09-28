## Descripcion
This is a really weird text file. Can you find the flag? Get the flag from [TXT](https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt).
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt
--2026-09-28 11:15:14--  https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.26, 18.238.132.88, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15696 (15K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt                      100%[=================================================>]  15.33K  48.8KB/s    in 0.3s

2026-09-28 11:15:16 (48.8 KB/s) - ‘flag.txt’ saved [15696/15696]


┌──(celesteh㉿K-Celeste)-[~]
└─$ mv flag.txt flag.png

┌──(celesteh㉿K-Celeste)-[~]
└─$ open flag.png

```

flag:
academy{now_you_know_about_extensions}
## Notas adicionales
## Referencias
