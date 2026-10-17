## Descripcion
How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/6/unknown.zip).
## Solucion
- Descargar el archivo proporcionado por el reto y descomprimirlo para acceder a la imagen contenida
    
- Ejecutar la herramienta `exiftool` sobre la imagen para inspeccionar sus metadatos
    
- Localizar el campo "Attribution URL" dentro de los metadatos que contiene la cadena cifrada o codificada
    
- Copiar dicha cadena y utilizar una plataforma de conversión o descifrado (como CyberChef) para procesarla
    
- Revisar la salida obtenida para revelar el texto plano y completar la solución

flag: academy{ME74D47A_HIDD3N_a81d9431}
## Notas adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=WVdOaFpHVnRlWHROUlRjMFJEUTNRVjlJU1VSRU0wNWZZVGd4WkRrME16RjlDZz09