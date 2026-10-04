## Descripcion
Python scripts are invoked kind of like programs in the Terminal... Can you run [ende.py](https://challenge-files.cylabacademy.net/library/a4f054dce4d90aca10ca6075cc2598da541e9acf11ed4a138b962ec69b442f05/ende.py) using [password.txt](https://challenge-files.cylabacademy.net/library/a4f054dce4d90aca10ca6075cc2598da541e9acf11ed4a138b962ec69b442f05/password.txt) to get [flag.txt.en](https://challenge-files.cylabacademy.net/library/a4f054dce4d90aca10ca6075cc2598da541e9acf11ed4a138b962ec69b442f05/flag.txt.en)?
## Solucion
```

┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/a4f054dce4d90aca10ca6075cc2598da541e9acf11ed4a138b962ec69b442f05/ende.py


2026-10-03 12:09:34 (25.8 MB/s) - ‘ende.py’ saved [1328/1328]


┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/a4f054dce4d90aca10ca6075cc2598da541e9acf11ed4a138b962ec69b442f05/password.txt


2026-10-03 12:09:44 (26.2 MB/s) - ‘password.txt’ saved [33/33]


┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/a4f054dce4d90aca10ca6075cc2598da541e9acf11ed4a138b962ec69b442f05/flag.txt.en


2026-10-03 12:09:54 (182 MB/s) - ‘flag.txt.en’ saved [140/140]

┌──(celesteh㉿K-Celeste)-[~]
└─$ cat password.txt
563e47ddeaf84eca8b2a31201381a898

┌──(celesteh㉿K-Celeste)-[~]
└─$ python3 ende.py -d flag.txt.en
Please enter the password:563e47ddeaf84eca8b2a31201381a898
academy{4p0110_1n_7h3_h0us3_d6af8f37}


```
## Notas adicionales
## Referencias