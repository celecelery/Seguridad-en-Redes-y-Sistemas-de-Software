## Descripcion
Can you find the flag in this disk image? Wrap what you find in the academy{} flag format. Download the disk image [here](https://challenge-files.cylabacademy.net/library/bf9a20c350075c5863371e078daee1d570d4062902edc8a4a042e02a7cebf161/partition4.img.gz).
## Solucion
1. Descargar la imagen de disco y revisar qué tipo de archivo es con `file partition4.img.gz`. Es un gzip, así que se descomprime con `gunzip partition4.img.gz`.
2. Correr `mmls partition4.img`. No muestra particiones, así que la imagen es directamente un sistema de archivos y no se necesita offset.
3. Listar los archivos con `fls -r -p partition4.img`. Se revisaron `/root/.ash_history` (solo contenía `poweroff`) y `/home/ctf-player` (vacío). No había nada útil.
4. Generar la línea de tiempo del sistema de archivos:

bash

```bash
   fls -r -m / partition4.img > body.txt
   mactime -b body.txt -d > timeline.csv
```

5. Contar cuántos archivos hay por fecha para encontrar una fuera de lugar:

bash

```bash
   awk -F, '{print substr($1,1,15)}' timeline.csv | sort | uniq -c
```

Aparece una sola entrada con fecha **Tue Jan 01 1985**, en un sistema instalado en noviembre de 2025.  
6. Filtrar por esa fecha con `grep '1985' timeline.csv`. Sale el archivo `/bin/bcab` (inodo 4945, 41 bytes) con la fecha alterada (timestomping).  
7. Leer el archivo con `icat partition4.img 4945`. Su contenido es una cadena en Base64: `NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK`.  
8. Decodificarla con `icat partition4.img 4945 | base64 -d`, que da `71m311n3_0u7113r_h3r_43a2e7af`, y envolver el resultado en el formato `academy{}`.

**Flag:** `academy{71m311n3_0u7113r_h3r_43a2e7af}`
## Notas adicionales
## Referencias
