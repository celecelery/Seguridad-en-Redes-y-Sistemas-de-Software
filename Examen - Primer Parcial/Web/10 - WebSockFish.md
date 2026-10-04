## Descripcion
Can you win in a convincing manner against this chess bot? He won't go easy on you!
## Solucion
- Abrir la aplicación de ajedrez proporcionada por el reto.
- Inspeccionar la comunicación de la aplicación mediante las herramientas de desarrollador y observar que utiliza un **WebSocket** para comunicarse con el servidor.
- Identificar que la aplicación envía mensajes con el formato `eval <valor>`, donde el valor representa la evaluación de la posición de ajedrez.
- Abrir la pestaña **Console** de las herramientas de desarrollador y utilizar la función `sendMessage()` para enviar manualmente mensajes al WebSocket.
- Enviar una evaluación extremadamente negativa mediante:
    
    ```
    sendMessage("eval -100000")
    ```
    
- Provocar que el servidor considere que el bot está perdiendo de manera irremediable y que abandone la partida.
- Visualizar la respuesta del servidor, donde se muestra la **flag**.

flag:
academy{c1i3nt_s1d3_w3b_s0ck3t5_96466159}

## Notas adicionales
## Referencias
