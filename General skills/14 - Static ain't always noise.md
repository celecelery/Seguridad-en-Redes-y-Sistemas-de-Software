## Descripcion
Can you look at the data in this binary? The bash script might help!
## Solucion

```
celeh127-academy@webshell:~$ ls
README.txt  ltdis.sh  static  strings  strings.1  warm
celeh127-academy@webshell:~$ chmod +x ltdis.sh
celeh127-academy@webshell:~$ ./ltdis.sh       
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
celeh127-academy@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
celeh127-academy@webshell:~$ grep "picoCTF" static.ltdis.strings.txt
   3020 picoCTF{d15a5m_t34s3r_20335e41}
```
## Notas adicionales
.sh son scripts de bash
rm * borra los archivos de la carpeta actual
## Referencias
