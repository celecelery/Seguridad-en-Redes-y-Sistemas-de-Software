## Descripcion
This service provides you an encrypted flag. Can you decrypt it with just N & e?
## Solucion
1. Ejecutar el comando de conexión `nc xebec.cylabacademy.net 32515` en la terminal para obtener los parámetros de cifrado generados por el servidor.
    
2. Copiar los valores resultantes proporcionados por la salida del comando: el módulo `N`, el exponente `e`, y el texto cifrado `cyphertext`.
    
3. Confirmar que el valor del módulo `N` termina en número par (6), lo cual asegura que la vulnerabilidad de generación de primos está presente y permite deducir inmediatamente que uno de los factores es $p = 2$.
    
4. Reemplazar los valores exactos en el script de Python previamente estructurado para calcular el factor $q = N // 2$, obtener la llave privada $d$, y descifrar el mensaje.
    
5. Ejecutar el script en el entorno de desarrollo para revelar la flag final en texto plano.

```
from Crypto.Util.number import long_to_bytes, inverse

# Valores extraídos de la conexión por netcat
N = 13501609825291126143039196228773223395150303148565763705702310496990239027812630418869870112260851689749767982632930332354896434371236107824523231139739546
e = 65537
c = 10558595975659015230240794207481883152325382385970657244931921225470604559554828680689520656384175057993513675482823867702662859946104020340304113707697111

# Factorización inmediata aprovechando la vulnerabilidad de paridad (EVEN RSA)
p = 2
q = N // 2

# Cálculo de phi y la llave privada d
phi = (p - 1) * (q - 1)
d = inverse(e, phi)

# Descifrado del mensaje
m = pow(c, d, N)

# Conversión a texto plano
flag = long_to_bytes(m)
print("Flag encontrada:", flag.decode())
```

academy{tw0_1$_pr!m3207f407f}
## Notas adicionales
## Referencias
