## Descripcion
Unzip this archive and find the file named 'uber-secret.txt'
## Solucion
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c/501/files.zip
celeh127-academy@webshell:~$ unzip -q files.zip
celeh127-academy@webshell:~$ find . -name "uber-secret.txt"
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
celeh127-academy@webshell:~$ cat $(find . -name "uber-secret.txt")
picoCTF{f1nd_15_f457_ab443fd1}

## Notas adicionales
## Referencias