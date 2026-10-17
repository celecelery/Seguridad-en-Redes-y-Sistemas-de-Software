## Descripcion
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.

To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!

Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.cylabacademy.net/library/828ca80eed550dbc9645ad6c2aa5c2061b2dd2e8e4098b1c7fe6d639459ea5a5/myNetworkTraffic.pcap) and try to get the flag.
## Solucion
- Descargar el archivo de captura de red (`.pcap`) proporcionado por el reto
    
- Abrir el archivo en Wireshark para inspeccionar el tráfico y notar que, al ordenar los paquetes por tiempo, se forma una secuencia oculta en la carga útil (payload) de TCP
    
- Utilizar la herramienta de línea de comandos `tshark` para extraer de forma estructurada los campos de tiempo (`frame.time_epoch`) y el payload (`tcp.payload`) del archivo
    
- Procesar la salida utilizando herramientas de terminal (`sort`, `awk`, `tr`, `xxd`) para ordenar cronológicamente los fragmentos y convertir los bytes hexadecimales a su forma original
    
- Aplicar una decodificación final en Base64 al flujo reconstruido para revelar la cadena de texto plano

flag: academy{1t_w4snt_th4t_34sy_tbh_4r_6b09861f}
## Notas adicionales
## Referencias
