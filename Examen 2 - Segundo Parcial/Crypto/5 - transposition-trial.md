## Descripcion
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://challenge-files.cylabacademy.net/library/575d166ae8e15aa3d7119731bdfb61feb9682e987d146d02fa3b47dde75d596a/message.txt).
## Solucion
1. Descargar el mensaje corrupto desde el enlace provisto por el reto.
    
2. Leer el texto del archivo descargado usando el comando `cat` en la terminal.
    
3. Ejecutar el siguiente script en Python, reemplazando el contenido de la variable `texto` con el mensaje obtenido:
    

```
texto = "heTfl g as icaaemd{7y4NRP051N5_16_35P3X51N3_V7F2D46C}5"

flag = ""
for i in range(0, len(texto), 3):
    bloque = texto[i:i+3]
    if len(bloque) == 3:
        flag += bloque[2] + bloque[0] + bloque[1]
    else:
        flag += bloque

print(flag)
```

flag: academy{7R4N5P051N6_15_3XP3N51V3_27F6D45C}
## Notas adicionales
## Referencias
