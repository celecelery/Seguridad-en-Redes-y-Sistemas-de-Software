## Descripcion
We found this [file](https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery). Recover the flag.
## Solucion

┌──(celesteh㉿K-Celeste)-[~/corrupt]
└─$ wget https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery

### 1. Restaurar la cabecera (Magic Bytes)

Al abrir el archivo en el editor hexadecimal, notamos que los primeros 8 bytes no correspondían a ningún formato estructurado válido. Siguiendo la pista del reto, dedujimos que debía ser un archivo PNG. Los archivos PNG siempre requieren una "firma" inicial exacta.

- **Bytes originales corruptos:** `89 65 4E 34 0D 0A B0 AA` (aprox.)
    
- **Corrección:** Sobrescribimos el inicio del archivo con los Magic Bytes correctos de PNG: `89 50 4E 47 0D 0A 1A 0A`.
    

### 2. Reparar el bloque IHDR

Al intentar procesar el archivo reparado con el comando `pngcheck -v`, la herramienta arrojó un error fatal en el offset 0x0000C: `invalid chunk name "C"DR" (43 22 44 52)`. El primer bloque de datos obligatorio en un PNG es el `IHDR`.

- **Corrección:** Modificamos la secuencia hexadecimal `43 22 44 52` y la reemplazamos por `49 48 44 52`. Esto restauró correctamente el nombre del bloque a texto ASCII legible `IHDR`.
    

### 3. Reparar el bloque pHYs (Error de CRC)

Con el IHDR arreglado, `pngcheck` logró leer un par de bloques más pero colapsó en el bloque `pHYs` marcando un error de redundancia cíclica (CRC) y mostrando un tamaño físico ilógico: `2852132389x5669 pixels/meter`. El bloque `pHYs` indica la resolución de la imagen y los ejes X/Y deben ser coherentes (usualmente simétricos).

- **Corrección:** Ubicamos los datos del bloque y observamos que el eje X tenía un byte dañado (ej. `AA`). Lo cambiamos a `00`, logrando que la secuencia volviera a ser simétrica: `00 00 16 25 00 00 16 25`.
    

### 4. Reparar el bloque de imagen IDAT

El último error reportado fue `invalid chunk length (too large)`. Esto significaba que el bloque principal de la imagen (`IDAT`), donde se guardan los píxeles, tenía la cabecera rota.

- **Corrección de la longitud (Offset 0x53):** Los bytes indicaban un tamaño desproporcionado. Calculando los bytes restantes del archivo, los ajustamos a `00 03 11 8A`.
    
- **Corrección del identificador (Offset 0x57):** El nombre del bloque no era legible (`AB...`). Cambiamos esos 4 bytes por `49 44 41 54` para que el archivo lo reconociera correctamente como `IDAT`.
## Notas adicionales
## Referencias
