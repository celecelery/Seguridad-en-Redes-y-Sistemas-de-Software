## Descripcion
Check the admin scratchpad!
## Solucion
1- Entré a la página del reto y me "registré" con un nombre de usuario cualquiera.
2- Abrí la extensión Cookie-Editor en el navegador y busqué una cookie llamada jwt, la cual al revisarla en un decodificador JWT mostraba que esa cadena guardaba mi nombre de usuario.
3- Como necesitaba codificar un nuevo JWT con el nombre de admin pero me faltaba la contraseña secreta para firmarlo, usé la herramienta John the Ripper en mi terminal de Kali Linux 
4- Descomprimí el diccionario rockyou.txt alojado en `/usr/share/wordlists` ejecutando `gzip -d /usr/share/wordlists/rockyou.txt.gz` y luego apliqué el comando `john -w=/usr/share/wordlists/rockyou.txt jwt.txt`.
5- John encontró la contraseña secreta que era `ilovepico`, la cual introduje en el codificador JWT junto con el usuario `admin` para generar el nuevo valor de la cookie.
6- Al reemplazar la cookie jwt original con este nuevo valor falsificado y recargar la página, entré como administrador y me dio la bandera.

flag:
picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}
## Notas adicionales
## Referencias
https://www.jwt.io/