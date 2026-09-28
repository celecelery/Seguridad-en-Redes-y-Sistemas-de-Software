## Descripcion
There's something in the [building](https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png). Can you retrieve the flag?
## Solucion

┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png

usar decodificador de esteganografia online y subir la imagen

academy{h1d1ng_1n_th3_b1t5}
## Notas adicionales

tambien se puede usar :
```
┌──(celesteh㉿K-Celeste)-[~]
└─$ zsteg -a buildings.png | grep academy
b1,rgb,lsb,xy       .. text: "academy{h1d1ng_1n_th3_b1t5}"
```
## Referencias
https://stylesuxx.github.io/steganography/