## Descripcion
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.
## Solucion
```
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2026-08-27 03:25:46--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.64, 3.160.5.95, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                   100%[========================================================================================>]     270  --.-KB/s    in 0s      

2026-08-27 03:25:46 (117 MB/s) - 'runme.py' saved [270/270]

celeh127-academy@webshell:~$ python3 runme.py
picoCTF{run_s4n1ty_run}
```
## Notas adicionales
## Referencias
