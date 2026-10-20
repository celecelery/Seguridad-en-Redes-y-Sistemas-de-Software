## Descripcion
In RSA, a small e value can be problematic, but what about N? Can you decrypt this? [values](https://challenge-files.picoctf.net/c_wily_courier/748a8bfc7244df64f48a6ad1d79b5900ee905dd28ebbcd5856652b0e4435393f/values)
## Solucion
- Descargar el archivo proporcionado por el reto para extraer los parámetros criptográficos públicos ($n$, $e$ y el texto cifrado $c$)
    
- Analizar el valor del módulo $n$ y notar que es inusualmente pequeño, lo que lo hace completamente vulnerable a una factorización directa
    
- Utilizar herramientas o servicios automatizados (como _FactorDB_) o un script en Python para descomponer rápidamente el módulo $n$ en sus factores primos $p$ y $q$
    
- Calcular la función phi de Euler, obtener la llave privada $d$ mediante el inverso modular y descifrar el texto cifrado
    
- Ejecutar el código para procesar los datos y revelar el mensaje original de forma automatizada


flag: academy{sma11_N_n0_g0od_a3ac7152}
## Notas adicionales
## Referencias
