## Descripcion
 user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
## Solucion

- Descargar el archivo de la filtración desde el enlace proporcionado en el reto y extraer su contenido, el cual incluirá los archivos `usernames.txt` y `passwords.txt`.
    
- Buscar en qué número de línea exacto se encuentra el usuario `cultiris` dentro del archivo `usernames.txt`.  `grep -n "cultiris" usernames.txt`.
    
- Extraer la contraseña correspondiente leyendo exactamente ese mismo número de línea en el archivo `passwords.txt`.
    
- Analizar la contraseña extraída
    
- Aplicar el algoritmo de descifrado ROT13 a esa cadena (utilizando herramientas como CyberChef
    

academy{C7r1F_54V35_71M3}

## Notas adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=bnBucXJ6bHtQN2UxU181NEkzNV83MVozfQ