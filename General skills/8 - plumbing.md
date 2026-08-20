## Descripcion
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?

## Solucion

```
`K-Celeste:/mnt/host/c/Users/cherp# nc fickle-tempest.picoctf.net 51876 | grep picoCTF`
`picoCTF{digital_plumb3r_00da27CC}`

```

## Notas adicionales

- Se utiliza para la salida de cualquier comando aun archivo de texto
- | redirige la salida de un comando a otro comando
## Referencias