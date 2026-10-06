## Descripcion

## Solucion

- Descargar el archivo `.pcap` y la clave (`key`) provistos por el reto
    
- Abrir el archivo de captura en Wireshark y configurar la clave proporcionada para desencriptar el flujo del protocolo TLS
    
- Analizar el tráfico descifrado para localizar y extraer la imagen de buitre (_vulture_) transmitida en la sesión
    
- Guardar la imagen extraída en el equipo local
    
- Ejecutar el comando `strings` sobre la imagen descargada para buscar cadenas de texto ocultas y obtener la flag
- 
picoCTF{honey.roasted.peanuts}
## Notas adicionales
## Referencias