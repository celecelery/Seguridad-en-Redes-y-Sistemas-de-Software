## Descripcion
Can you find the flag in this disk image? Wrap what you find in the academy{} flag format. Download the disk image [here](https://challenge-files.cylabacademy.net/library/0b369ed5974a5e777ca3bc323bd39d75a6f27762a449d16cd2a0ffc08b2a6aa8/timeline-1-partition4.img.gz).
## Solucion

1. Descargar la imagen con `wget` y descomprimirla con `gunzip timeline-1-partition4.img.gz`.
2. Correr `mmls timeline-1-partition4.img`. No muestra particiones, así que la imagen es directamente un sistema de archivos y no se necesita offset.
3. Generar la línea de tiempo:

bash

```bash
   fls -r -m / timeline-1-partition4.img > body.txt
   mactime -b body.txt -d > timeline.csv
```

4. Contar los archivos por fecha con `awk -F, '{print substr($1,1,15)}' timeline.csv | sort | uniq -c`. A diferencia de Timeline 0, esta vez **no hay fechas absurdas** (como 1985), así que el truco anterior no funciona.
5. Revisar los archivos borrados con `fls -r -p -d timeline-1-partition4.img | grep -v '\.apk\.'`. Solo aparecen restos de vim, nada relevante.
6. Filtrar los archivos **creados** (`macb` o `...b`) quitando el ruido del sistema y ver los últimos eventos:

bash

```bash
   grep -E 'macb|\.\.\.b' timeline.csv | grep -vE '/etc/(init.d|conf.d|runlevels)|/lib/rc|/lib/modules|busybox' | tail -n 40
```

La secuencia que se ve es:

- 15:42:05: se instala vim.
- **15:50:07: se crea `/etc/chat` (inodo 32716, 49 bytes), que no es un archivo propio de Alpine.**
- 15:50:23: `poweroff`.

7. Leer el archivo con `icat timeline-1-partition4.img 32716`. Contiene la cadena Base64 `NTczNDE3aDEzcl83aDRuXzdoM18xNDU3XzU4NTI3YmIyMjIK`.
8. Decodificarla con `icat timeline-1-partition4.img 32716 | base64 -d`, que da `573417h13r_7h4n_7h3_1457_58527bb222`, y envolver el resultado en `academy{}`.

**Flag:** `academy{573417h13r_7h4n_7h3_1457_58527bb222}`
## Notas adicionales
## Referencias
