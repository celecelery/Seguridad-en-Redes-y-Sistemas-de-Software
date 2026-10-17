## Descripcion
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://challenge-files.cylabacademy.net/library/c585b4adbdaa06f409db7bf5012c2e58e9aab24669764a5f1cf0f9ce0d60dcfd/cat.jpg)
## Solucion
- Descargar la imagen proporcionada por el reto
    
- Ejecutar la herramienta `exiftool` en la terminal para inspeccionar los metadatos ocultos en el archivo de imagen
    
- Copiar la cadena de texto almacenada en el campo de licencia, la cual contiene la flag encriptada
    
- Ingresar el texto obtenido en la plataforma CyberChef y aplicar la operación de descifrado correspondiente (como Base64 u otro formato identificado)
    
- Revisar la salida generada para revelar el texto plano y completar la solución

flag: academy{the_m3tadata_1s_modified}
## Notas adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=WVdOaFpHVnRlWHQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjk