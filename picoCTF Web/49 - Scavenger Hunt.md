## Descripcion
There is some interesting information hidden around this site. Can you find it?
## Solucion
1- Entré a la página principal del reto, hice clic derecho y seleccioné **Ver código fuente de la página**. Al final del HTML encontré un comentario con la Parte 1 de la bandera.

2- En el mismo código fuente vi que la página cargaba un archivo de estilos. Hice clic en el enlace a mycss.css y al final del archivo encontré un comentario con la Parte 2.

3- Abrí el archivo de JavaScript myjs.js. Ahí no estaba la bandera directamente, pero había un comentario que decía que la página no quería ser indexada por buscadores.

4- Escribí `/robots.txt` al final de la URL en la barra de direcciones. Al entrar, encontré la Parte 3 y una nota que mencionaba el uso de un servidor web Apache.

5- Escribí /.htaccess en la URL (el archivo de configuración de Apache) para obtener la Parte 4, la cual incluía una pista sobre cómo se guardan archivos en computadoras Mac.

6- Escribí /.DS_Store en la URL para acceder al archivo oculto de macOS y me dio la Parte 5.

- **Parte 1:** picoCTF{t
- **Parte 2:** h4ts_4_l0
- **Parte 3:** t_0f_pl4c
- **Parte 4:** 3s_2_lO0k
- **Parte 5:** _9588550}

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_9588550}
## Notas adicionales
## Referencias
