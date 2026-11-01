## Descripcion
You will find the flag after decrypting this file Download the encrypted flag [here](https://challenge-files.cylabacademy.net/library/545f29dd6d01fbbfe2cb0c2616132c3b10c64c676d94c9cc88d3fc15020078a2/encrypted.txt).
## Solucion
1 - Descargar el archivo con la flag encriptada desde el enlace provisto por el reto. 
2 - Usar el comando `cat` en la terminal para leer el texto cifrado contenido en el archivo. 
3 - Hacer un script en Python para aplicar fuerza bruta y encontrar el desplazamiento correcto (Cifrado César), basándose en la pista "Sometimes rotation is right":

```
texto_cifrado = "ikilmug{z0bib1wv_l3kzgxb3l_91mllij9}"

for rot in range(26):
    flag_interna = ""
    for char in texto_cifrado:
        if char.isalpha():
            # Determinar si es mayúscula (65) o minúscula (97) en código ASCII
            offset = 65 if char.isupper() else 97
            # Aplicar la rotación
            flag_interna += chr((ord(char) - offset + rot) % 26 + offset)
        else:
            # Mantener números y símbolos (como llaves y guiones) intactos
            flag_interna += char
    
    # Filtrar e imprimir solo el resultado que tenga sentido (formato de flag)
    if "picoCTF{" in flag_interna or "academy{" in flag_interna:
        print(f"Flag (Rotación {rot}): {flag_interna}")
```

flag: academy{r0tat1on_d3crypt3d_91eddab9}
## Notas adicionales
## Referencias
