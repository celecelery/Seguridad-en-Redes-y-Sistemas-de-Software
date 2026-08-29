## Descripcion
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?
## Solucion
```
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/71/challenge.zip
--2026-08-29 23:03:48--  https://artifacts.picoctf.net/c_titan/71/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24467 (24K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                         100%[=========================================================================>]  23.89K  --.-KB/s    in 0.004s  

2026-08-29 23:03:48 (5.43 MB/s) - 'challenge.zip' saved [24467/24467]

celeh127-academy@webshell:~$ unzip -q challenge.zip
celeh127-academy@webshell:~$ cd drop-in
celeh127-academy@webshell:~/drop-in$ git branch -a
celeh127-academy@webshell:~/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
celeh127-academy@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')celeh127-academy@webshell:~/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
celeh127-academy@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')celeh127-academy@webshell:~/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
celeh127-academy@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")

print("w0rk_4c24302f}")
celeh127-academy@webshell:~/drop-in$ 

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_4c24302f}
```
## Notas adicionales
## Referencias
