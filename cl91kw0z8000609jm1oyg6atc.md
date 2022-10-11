# Reconocimiento con Nmap (Ethical Hacking)

## Recopilación de información:

Comprobación de la conectividad con la máquina.
	❯ ping -c 1 10.10.11.130
En la salida del comando anterior se puede ver un parámetro llamado ttl, gracias a este parámetro podemos saber qué sistema operativo está corriendo en la máquina víctima.

	❯ GNU/Linux = TTL 64
	❯ Windows = TTL 128

Nmap para descubrir que puertos están abiertos y que servicios están asociados a estos.

	❯ nmap -p- --open -sS --min-rate 5000 -vvv -n -Pn 10.10.11.130 -oG allport

-   -p-  ⇾ Escanea todos los puertos (65535)
-   –open → Muestra solo los puertos con un estatus “open”
-   -sS → Aplica un TCP SYN Scan
-   –min-rate 5000 → Indica que quiero emitir paquetes no más lentos que 5000 paquetes por segundo
-   -vvv → Muestra la información en pantalla a medida que se descubre
-   -n → Indica que no aplique resolución DNS
-   -Pn → Indica que no aplique el protocolo ARP
-   10.10.11.130 → Dirección IP que se quiere escanear
-   -oG allPorts  → Exporta el output a un fichero grepeable con nombre “allPorts”

Nmap, pero esta vez solamente lanzaremos scripts básicos de enumeración y analizaremos la versión de los puertos abiertos obtenidos anteriormente.

	❯ nmap -p80 -sC -sV 10.10.11.130 -oN targeted

-   **-p80**  *->* Indica los puertos que se quieren escanear
-   **-sC**  *->* Lanza scripts básicos de enumeración
-   **-sV**  *->* Enumera la versión y servicio que está corriendo en los puertos
-   **10.10.11.130**  *->* Dirección IP que se quiere escanear
-   **-oN targeted**  *->* Exporta el output a un fichero en formato nmap con nombre “targeted”