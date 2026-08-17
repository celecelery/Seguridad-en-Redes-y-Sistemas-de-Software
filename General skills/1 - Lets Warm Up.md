## Descripcion

If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Solucion 1

- ir a web que transoforme hexadecimal a ascii

picoCTF[p}]

## Solucion 2

`ir al interprete de python`
`celeh127-academy@webshell:~$ python`
`Python 3.10.12 (main, Mar  3 2026, 11:56:32) [GCC 11.4.0] on linux`
`Type "help", "copyright", "credits" or "license" for more information.`
>>> `int(0x70)`
`112`
>>> `chr(112)`
`'p'`


## Notas adicionales
Tomar en cuenta el formato de la bandera para que sea aceptada


## Referencias
- https://www.rapidtables.com/convert/number/hex-to-ascii.html