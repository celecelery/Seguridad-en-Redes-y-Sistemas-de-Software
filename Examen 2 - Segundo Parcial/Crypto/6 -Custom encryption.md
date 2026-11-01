## Descripcion
Can you get sense of this code file and write the function that will decode the given encrypted file content.

Find the encrypted file here [flag_info](https://challenge-files.cylabacademy.net/library/c5a30495112ed010f3131d9c91bc11efa2c005dfda1262f5c64d434f43a3bbc2/enc_flag) and [code file](https://challenge-files.cylabacademy.net/library/c5a30495112ed010f3131d9c91bc11efa2c005dfda1262f5c64d434f43a3bbc2/custom_encryption.py) might be good to analyze and get the flag.
## Solucion

1 - decargar los archivos
2 - usar cat en ambos archivos
3 - hacer un script e incluir los dos datos extraidos de cat

```
a = 95
b = 31
cipher = [134352, 343344, 238848, 1194240, 0, 1298736, 1059888, 1134528, 1059888, 626976, 0, 1239024, 313488, 74640, 1015104, 0, 328416, 1283808, 14928, 925536, 358272, 403056, 89568, 89568, 253776, 89568, 388128, 179136, 373200, 343344, 253776, 74640, 89568, 0]

p = 97
g = 31
text_key = "trudeau"

# 1. Calcular la llave compartida (Diffie-Hellman)
shared_key = pow(pow(g, b, p), a, p)

# 2. Revertir la multiplicación del cifrado original
semi_cipher = ""
for num in cipher:
    semi_cipher += chr(num // (shared_key * 311))

# 3. Revertir la capa de XOR dinámico usando la llave "trudeau"
flag_invertida = ""
key_length = len(text_key)
for i, char in enumerate(semi_cipher):
    key_char = text_key[i % key_length]
    flag_invertida += chr(ord(char) ^ ord(key_char))

# 4. Invertir la cadena final 
print(flag_invertida[::-1])
```

flag: academy{custom_d2cr0pt6d_5826e4ee}
## Notas adicionales
## Referencias
