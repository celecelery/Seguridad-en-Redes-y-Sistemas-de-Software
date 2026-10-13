## Descripcion
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).
## Solucion
1. Descargar el archivo proporcionado por el reto
    
2. Extraer el texto cifrado inicial contenido en el archivo
    
3. Ingresar el texto en la plataforma CyberChef y aplicar una decodificación en **Base64**
    
4. Tomar el resultado obtenido de la primera decodificación, volver a ingresarlo en CyberChef y aplicarle otra capa de decodificación en **Base64**
    
5. Aplicar la operación **ROT13** (o cifrado César) configurándola con un desplazamiento de 19 rotaciones sobre el texto resultante para revelar la bandera final
    

**flag:**  academy{caesar_d3cr9pt3d_9df0cfea}
## Notas adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,19)&input=aGpoa2x0ZntqaGx6aHlfazNqeTl3YTNrXzlrbTBqbWxofQ&oeol=NEL