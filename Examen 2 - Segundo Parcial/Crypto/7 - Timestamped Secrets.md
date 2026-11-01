## Descripcion
Someone encrypted a message using AES in ECB mode but they weren’t very careful with their key. Turns out it’s derived from something as simple as the current time! Can you uncover the key and decrypt the flag? Download the encrypted message: [message](https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/message.txt)  
You may also find the encryption script helpful: [code](https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/encryption.py)
## Solucion
1. Descargar el mensaje cifrado (`message`) y el script de encriptación (`code`) desde los enlaces del reto.
    
2. Leer el archivo `message_2.txt` para extraer el timestamp aproximado (`1790147519`) y el texto cifrado en hexadecimal (`44e98ac8b821d1b561b49f38c114c89405c1895b1f9425b6adc8e0911b68731a`).
    
3. Analizar el archivo `encryption_2.py` para identificar que la llave AES-ECB son los primeros 16 bytes del hash SHA256 del timestamp.  
    
4. Ejecutar el siguiente script en Python para aplicar fuerza bruta sobre los segundos cercanos al timestamp proporcionado y extraer la bandera:
    

```
from hashlib import sha256
from Crypto.Cipher import AES
from Crypto.Util.Padding import unpad

# Valores extraídos de message
timestamp_aproximado = 1790147519
ciphertext = bytes.fromhex("44e98ac8b821d1b561b49f38c114c89405c1895b1f9425b6adc8e0911b68731a")

# Probar 1000 segundos antes y después del timestamp dado
for t in range(timestamp_aproximado - 1000, timestamp_aproximado + 1000):
    # Recrear la llave usando la misma lógica de encryption_2.py
    key = sha256(str(t).encode()).digest()[:16]
    cipher = AES.new(key, AES.MODE_ECB)
    
    try:
        # Intentar descifrar y quitar el padding
        decrypted = unpad(cipher.decrypt(ciphertext), AES.block_size)
        
        # Filtrar el resultado correcto
        if b"academy{" in decrypted:
            print(decrypted.decode('utf-8'))
            break
    except ValueError:
        # El padding incorrecto lanza ValueError, se ignora y se sigue intentando
        pass
```

academy{sa3S_sEc9t_3b464909}
## Notas adicionales
## Referencias
