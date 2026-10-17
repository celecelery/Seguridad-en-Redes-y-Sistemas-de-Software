## Descripcion
RED, RED, RED, RED Download the image: [red.png](https://challenge-files.cylabacademy.net/library/fefcf06050d98347e1585e5cb9f2940967f82e0b89c591966473c752de9f3aba/red.png)
## Solucion
- Descargar la imagen proporcionada por el reto
    
- Ejecutar la herramienta `zsteg` sobre la imagen para analizar los datos ocultos en los canales de los bits menos significativos
    
- Identificar en la salida del comando el texto que se repite varias veces en formato codificado
    
- Copiar dicha cadena y utilizar una herramienta de decodificación en Base64 (como CyberChef) para procesarla
    
- Analizar el resultado obtenido para revelar el texto plano y completar la solución

flag: academy{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
## Notas adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=WVdOaFpHVnRlWHR5TTJSZk1YTmZkR2d6WDNWc2RERnROSFF6WDJOMWNqTmZaakJ5WHpVMFpHNHpOVFZmZlE9PVlXTmhaR1Z0ZVh0eU0yUmZNWE5mZEdnelgzVnNkREZ0TkhRelgyTjFjak5mWmpCeVh6VTBaRzR6TlRWZmZRPT1ZV05oWkdWdGVYdHlNMlJmTVhOZmRHZ3pYM1ZzZERGdE5IUXpYMk4xY2pOZlpqQnlYelUwWkc0ek5UVmZmUT09WVdOaFpHVnRlWHR5TTJSZk1YTmZkR2d6WDNWc2RERnROSFF6WDJOMWNqTmZaakJ5WHpVMFpHNHpOVFZmZlE9PSI