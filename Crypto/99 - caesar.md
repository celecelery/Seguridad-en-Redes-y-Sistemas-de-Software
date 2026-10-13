## Descripcion
Decrypt this message. Message: [message](https://challenge-files.picoctf.net/c_fickle_tempest/4baa3e051f746434453e7cb328af49573b3771c7789d068c0c53df5c52919a5b/data.enc)
## Solucion
1. Descargar el archivo proporcionado por el reto
    
2. Extraer el texto cifrado contenido dentro del archivo descargado
    
3. Ingresar el texto en la plataforma CyberChef
    
4. Aplicar la operación de cifrado **ROT13** ajustando la cantidad de desplazamientos (giros) a un total de 27 rotaciones
    
5. Analizar el resultado obtenido en la salida de CyberChef para revelar el texto plano y completar la solución
    

**flag:** academy{crossingtherubiconvfuyazrb}
## Notas adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,true,5)&input=e3htam5uZGlib2N6bXB3ZHhqaXFhcHR2dW13fQ