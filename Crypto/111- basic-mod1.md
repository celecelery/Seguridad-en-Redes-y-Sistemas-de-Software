## Descripcion
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://challenge-files.cylabacademy.net/library/153c6663b971f4d124ad181fdbf1c21ad47dc241b7a578ab47253d6461f2f145/message.txt).

Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.

Wrap your decrypted message in the academy flag format (i.e. `academy{decrypted_message}`)
## Solucion

1 - descargar el archivo
2- usar cat
3- hacer un script para que muestre la flag usando los numeros que salieron con el uso de cat

```
numeros = [239, 396, 131, 87, 188, 147, 309, 295, 165 ,248 ,353 ,383 ,299, 258 ,137 ,291, 145, 180, 262, 178, 252 ,148]

caracteres = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_"


flag_interna = ""

for n in numeros:

    flag_interna += caracteres[n % 37]

  

print(f"academy{{{flag_interna}}}")
```

flag: academy{R0UND_N_R0UND_0686D44A}
## Notas adicionales
## Referencias
