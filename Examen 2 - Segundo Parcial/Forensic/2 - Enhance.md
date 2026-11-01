## Descripcion
Download this image file and find the flag.
## Solucion

1- descargar archivo
2 - usar grep
```
┌──(celesteh㉿K-Celeste)-[~/retop3]
└─$ tr -d '\n' < drawing.flag.svg | grep -o '<tspan[^>]*>[^<]*</tspan>' | sed 's/<[^>]*>//g' | tr -d ' '; echo
academy{3nh4nc3d_001f8059}
```
academy{3nh4nc3d_001f8059}
## Notas adicionales
## Referencias
