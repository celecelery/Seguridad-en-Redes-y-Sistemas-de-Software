## Descripcion
How about trying to match a regular expression
## Solucion
La descripción nos indica que debemos de buscar una palabra o frase que encaje con una expresión regular que no sabemos cual es. Para esto, podemos buscar en el código fuente de la página. Buscando hasta en la parte de abajo, encontramos el siguiente código:

```html
<script>
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}

</script>
```

Aquí encontramos la expresión regular: **^p.....F!?** la cual nos dice que debe de haber una p minúscula al inicio de la palabra, con al menos 5 caracteres cualquiera y una F al final de la palabra. Al introducir una como picoCTF nos da la flag.

picoCTF{succ3ssfully_matchtheregex_08c310c6}
## Notas adicionales
## Referencias