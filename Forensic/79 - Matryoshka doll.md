## Descripcion

## Solucion
- Descargar la imagen proporcionada por el reto (`dolls.jpg`)
    
- Ejecutar el comando `binwalk -Me dolls.jpg` para extraer de forma automática todos los archivos ocultos y comprimidos incrustados en la imagen
    
- Explorar las carpetas generadas por la extracción utilizando el comando de búsqueda `find . -name "flag.txt" -exec cat {} +`
    
- Localizar el archivo de texto resultante y leer su contenido directamente desde la consola para completar la solución
## Notas adicionales
## Referencias