## Descripcion
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag. The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden. The website is running [picoCTF News](http://verbal-sleep.picoctf.net:53815/).
## Solucion
1. Entrar al link proporcionado por el reto
    
2. Navegar a la sección de "Api Documentation" dentro de la página
    
3. Desplazarse hasta localizar la sección del volcado de memoria (headdump)
    
4. Descargar el archivo disponible en dicha sección
    
5. Utilizar el comando `grep` para buscar la cadena "academy" dentro del archivo descargado y revelar la flag
    

**flag:**`academy{Pat!3nt_15_Th3_K3y_cc0f4fda}`
## Notas adicionales

## Referencias
