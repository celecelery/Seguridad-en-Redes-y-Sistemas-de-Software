## Descripcion
Can you find the flag in this disk image? This time I deleted the file! Let see you get it now! Download the disk image [here](https://challenge-files.cylabacademy.net/library/4642fdd92be0f083b557c67cba47484a62c74bfdf3a99153137b356902f5b13c/disko-4.dd.gz)
## Solucion
1. Descargar la imagen con `wget` y descomprimirla con `gunzip disko-4.dd.gz`.
2. Identificar el tipo de imagen con `file disko-4.dd`. Es un sistema de archivos **FAT32** sin tabla de particiones, así que no se necesita offset.
3. Buscar la flag directamente con `strings disko-4.dd | grep -i 'academy'`. **No aparece nada**, porque el archivo que la contiene está comprimido.
4. Listar solo los archivos borrados con `fls -r -p -d disko-4.dd`. Aparecen dos:

```
   r/r * 522629:   log/messages
   r/r * 532021:   log/dont-delete.gz
```

El sospechoso es `log/dont-delete.gz` (número 532021).  
5. Recuperar el archivo borrado con `icat disko-4.dd 532021 > dont-delete.gz`.  
6. Verificar qué tipo de archivo es con `file dont-delete.gz`. Es un **gzip** que originalmente se llamaba `dont-delete` y pesaba 55 bytes.  
7. Descomprimirlo y mostrar el contenido con `gunzip -c dont-delete.gz`:

```
   Here is your flag
   academy{d3l_d0n7_h1d3_w3ll_f564c3ef}
```

**Flag:** `academy{d3l_d0n7_h1d3_w3ll_f564c3ef}`
## Notas adicionales
## Referencias
