## Descripcion
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled1.png) [scrambled2.png](https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled2.png)
## Solucion
1- Descargar las imagen
2 - Hacer un script de python que convierta las imagenes en matrices
3 - Obtener la flag

```
from PIL import Image
import numpy as np

img1 = Image.open('scrambled1.png')
img2 = Image.open('scrambled2.png')

matriz1 = np.array(img1, dtype=np.uint8)
matriz2 = np.array(img2, dtype=np.uint8)

mflag = matriz1 + matriz2

res = Image.fromarray(mflag)
res.save('flag.png')
```

flag: academy{2f16d0c4}
## Notas adicionales
## Referencias
