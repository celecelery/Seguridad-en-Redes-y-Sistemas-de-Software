## Descripcion
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.

There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solucion
```
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.py
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.hash.bin
celeh127-academy@webshell:~$ nano level3.py
celeh127-academy@webshell:~$ python level3.py
Please enter correct password for flag: 6997
That password is incorrect
celeh127-academy@webshell:~$ python level3.py
Please enter correct password for flag: 3ac8    
That password is incorrect
celeh127-academy@webshell:~$ python level3.py
Please enter correct password for flag: ec27
That password is incorrect
celeh127-academy@webshell:~$ python level3.py
Please enter correct password for flag: 4e66
That password is incorrect
celeh127-academy@webshell:~$ python level3.py
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
```

## Notas adicionales
## Referencias
