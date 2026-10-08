
## Descripcion
🥛
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/slap]
└─$ wget http://chatelaine.cylabacademy.net:16412/concat_v.png

2026-10-07 10:41:48 (555 KB/s) - ‘concat_v.png’ saved [18095896/18095896]


┌──(celesteh㉿K-Celeste)-[~/slap]
└─$ RUBY_THREAD_VM_STACK_SIZE=50000000 zsteg -a concat_v.png | grep academy
b1,b,lsb,xy         .. text: "academy{imag3_m4n1pul4t10n_sl4p5}\n"

```

## Notas adicionales
## Referencias
