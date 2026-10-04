## Descripcion
BookShelf Pico, my premium online book-reading service.

I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!
## Solucion
1. Entrar a la página web del reto y obtener el token JWT correspondiente al usuario normal
2. Revisar y decodificar el token JWT obtenido utilizando una herramienta de decodificación
3. Inspeccionar el código fuente de la aplicación para extraer el usuario, la contraseña de administrador y la llave secreta (en este caso, "1234")
4. Utilizar un codificador de JWT con los datos de administrador y la llave secreta para generar un nuevo token JWT con privilegios elevados
5. Modificar el almacenamiento local (`localStorage`) de la página web reemplazando el token anterior por el nuevo JWT de administrador para obtener la flag

**flag:**
academy{w34k_jwt_n0t_g00d_1107047a}
## Notas adicionales
## Referencias
