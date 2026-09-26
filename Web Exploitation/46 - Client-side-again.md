## Descripcion
Can you break into this super secure portal?
## Solucion
1- Ir a la pagina proporcionada y entrar a ver el codigo fuente
2- en la parte de script viene la flag pero dividida
3- Juntar las partes de la flag
(con ayuda de gemini)
Para extraer la bandera, reconstruimos las piezas del arreglo ofuscado y las condiciones de la función `verify()`.

```
['daf93}', '_again_4', 'this', 'Password Verified', 'Incorrect password', 'getElementById', 'value', 'substring', 'picoCTF{', 'not_this']
```

La función autoejecutable realiza una rotación circular mediante `push(shift())` tantas veces como indique `++0x1b3`:

- $0x1b3 + 1 = 435 + 1 = 436$
- $436 \pmod{10} = 6$

Rotar 6 veces a la izquierda desplaza los elementos:
- `_0x5a46[0]` ('0x0'): `'getElementById'`
- `_0x5a46[1]` ('0x1'): `'value'`
- `_0x5a46[2]` ('0x2'): `'substring'`
- `_0x5a46[3]` ('0x3'): `'picoCTF{'`
- `_0x5a46[4]` ('0x4'): `'not_this'`
- `_0x5a46[5]` ('0x5'): `'daf93}'`
- `_0x5a46[6]` ('0x6'): `'_again_4'`
- `_0x5a46[7]` ('0x7'): `'this'`
- `_0x5a46[8]` ('0x8'): `'Password Verified'`
- `_0x5a46[9]` ('0x9'): `'Incorrect password'`
    

### 2. Segmentación de la cadena (`checkpass`)

Con `split = 4`:


- **`[0, split*2]` $\rightarrow$ `substring(0, 8)`**:
    
    Debe ser igual a `_0x4b5b('0x3')` $\rightarrow$ `'picoCTF{'`
    
- **`[split*2, split*2*2]` $\rightarrow$ `substring(8, 16)`**:
    
    Debe ser igual a `_0x4b5b('0x4')` $\rightarrow$ `'not_this'`
    
- **`[split*2*2, split*3*2]` $\rightarrow$ `substring(16, 24)`**:
    
    Debe ser igual a `_0x4b5b('0x6')` $\rightarrow$ `'_again_4'`
    
- **`[split*3*2, split*4*2]` $\rightarrow$ `substring(24, 32)`**:
    
    Debe ser igual a `_0x4b5b('0x5')` $\rightarrow$ `'daf93}'`
    
_(Las comprobaciones intermedias redundantes como `(7, 9) == '{n'`, `(3, 6) == 'oCT'`, `(6, 11) == 'F{not'` y `(12, 16) == 'this'` coinciden perfectamente con estos fragmentos)._

Bandera:

```
picoCTF{not_this_again_4daf93}
```
## Notas adicionales
## Referencias
