## Descripcion

## Solucion
1.- Descargar y guardar el archivo de captura de red provisto por el reto en tu carpeta de trabajo.

2.- Abrir la herramienta **Wireshark** en tu sistema.

3.- Cargar y abrir el archivo `.pcap` dentro de Wireshark.

4.- Filtrar los paquetes usando el protocolo **UDP** introduciendo el filtro `udp` en la barra superior.

5.- Analizar los puertos UDP de los paquetes (específicamente revisando los valores de los puertos origen/destino, ya que ahí suelen codificarse los caracteres de la flag en ASCII o en secuencia) para reconstruir y revelar la flag completa.
## Notas adicionales
## Referencias
