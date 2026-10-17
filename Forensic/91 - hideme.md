## Descripcion
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/259/flag.png).
## Solucion
- Descargar la imagen proporcionada por el reto
    
- Ejecutar la herramienta `binwalk` sobre la imagen para analizar su estructura e identificar archivos ocultos o incrustados en su interior
    
- Utilizar el comando `binwalk -e` (extract) para extraer de forma automática todos los archivos ocultos encontrados dentro de la imagen
    
- Explorar el directorio generado por la extracción para localizar la nueva imagen o archivo resultante que contiene la flag visible

flag: academy {Hiddinng_An_imag3_within_@n_ima9e_c55a7afe}
## Notas adicionales
## Referencias
