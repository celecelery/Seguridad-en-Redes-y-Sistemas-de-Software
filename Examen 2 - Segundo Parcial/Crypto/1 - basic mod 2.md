## Descripcion
A new modular challenge! Download the message [here](https://challenge-files.cylabacademy.net/library/8493f8b1c07d84e858fa52d3dacdc63752275286da7a30b69fab36993eafb5ea/message.txt).

Take each number mod 41 and find the modular inverse for the result. Then map to the following character set: 1-26 are the alphabet, 27-36 are the decimal digits, and 37 is an underscore.

Wrap your decrypted message in the academy flag format (i.e. `academy{decrypted_message}`)
## Solucion
1 - Descargar el archivo provisto por el reto. 
2 - Usar el comando `cat` en la terminal para leer el contenido del archivo y obtener la secuencia de números. 
3 - Hacer un script en Python para que muestre la flag usando los números que salieron con el uso de `cat`:

```
numeros = [239, 396, 131, 87, 188, 147, 309, 295, 165 ,248 ,353 ,383 ,299, 258 ,137 ,291, 145, 180, 262, 178, 252 ,148]

caracteres = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_"

flag_interna = ""

for n in numeros:
    flag_interna += caracteres[n % 37]

print(f"academy{{{flag_interna}}}")
```

**Flag:** `academy{R0UND_N_R0UND_0686D44A}`
## Notas adicionales
## Referencias
