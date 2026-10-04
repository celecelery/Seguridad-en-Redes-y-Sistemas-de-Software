## Descripcion

## Solucion
1. Entrar al link proporcionado por el reto
2. Identificar que la aplicación web utiliza el motor de plantillas Jinja2
3. Introducir la carga útil de SSTI (Server-Side Template Injection) ingresando la expresión `{{ config.class.init.globals['os'].popen('cat flag').read() }}` en el campo vulnerable
4. Ejecutar la inyección para que el motor procese el comando del sistema operativo y lea el archivo que contiene la bandera
5. Visualizar el resultado devuelto en la respuesta de la página web para obtener la flag 

**flag:**
academy{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_31d5a337}
## Notas adicionales
## Referencias
