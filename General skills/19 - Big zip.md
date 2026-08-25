## Descripcion
Unzip this archive and find the flag.
## Solucion

celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
celeh127-academy@webshell:~$ unzip -qq big-zip-files.zip
celeh127-academy@webshell:~$ grep -r "picoCTF" .
./big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
celeh127-academy@webshell:~$ 
## Notas adicionales
-q es para descomprimir sin que aparezcan todos los archivos en pantalla
## Referencias