## Descripcion
Why use p and q when I can use more?
## Solucion
- Analizar las pistas proporcionadas por el reto y notar que el módulo $n$ está compuesto por el producto de más de dos números primos (Multi-Prime RSA)
    
- Utilizar una herramienta especializada en factorización de números grandes (como la calculadora de factorización de enteros de Alpertron) para ingresar el valor gigante de $n$
    
- Obtener la lista completa de todos los factores primos distintos que componen $n$ (en este caso, 34 números primos)
    
- Desarrollar un script en Python para procesar todos los primos obtenidos, calcular la función phi generalizada para Multi-Prime RSA, reconstruir la llave privada $d$ y descifrar el texto cifrado
    
- Ejecutar el código para procesar los parámetros y revelar el mensaje original de forma automatizada

flag: academy{too_many_fact0rs_9487747}
## Notas adicionales
## Referencias
