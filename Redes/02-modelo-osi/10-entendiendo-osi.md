# 10 - Wireshark: Los Rayos X de la Red 🦈
> **🎯 Objetivo:** Aprenderás a ver lo invisible. Usaremos una herramienta real para "abrir" los cables de red y ver exactamente cómo se ven las capas del Modelo OSI en la vida real. Prepárate para sentirte como un hacker ético o un detective de redes.

---

### 1. ¿Qué es Wireshark? (El Microscopio Digital) 🔬
Imagina que eres un médico y puedes ver la sangre fluir por las venas. En redes, **Wireshark** es esa herramienta: un **Analizador de Paquetes (Packet Sniffer)** que captura y muestra todo el tráfico que entra y sale de tu computadora .

Aunque el examen Network+ no te pedirá que seas un experto en Wireshark, necesitas saber **qué es** y **para qué sirve**: solucionar problemas (troubleshooting), análisis de seguridad y entender el flujo de datos.

> **💡 Nota del Mentor:** Wireshark te permite capturar tráfico en tiempo real o abrir archivos guardados (llamados archivos `.pcap`). Es como grabar una conversación telefónica para escucharla después y analizar cada palabra.

---

### 2. Diseccionando una Conexión Web (HTTP) 🌐
Vamos a abrir una captura real de alguien visitando una página web.

Al seleccionar un solo paquete en Wireshark, verás cómo se despliegan las capas del Modelo OSI como si fueran una cebolla:

1.  **Frame (Trama):** Esto es **Capa 2 (Enlace de Datos)**. Aquí verás:
    * Dirección MAC de Origen (tu PC).
    * Dirección MAC de Destino (el router o servidor).
    * Protocolo: Ethernet.

2.  **Internet Protocol (IP):** Esto es **Capa 3 (Red)**. Aquí verás:
    * Dirección IP de Origen (Source IP).
    * Dirección IP de Destino (Destination IP).
    * Versión: IPv4.

3.  **Transmission Control Protocol (TCP):** Esto es **Capa 4 (Transporte)**. Aquí verás:
    * Puertos de origen y destino (ej: Puerto 80 para Web).
    * Banderas (Flags) como SYN o ACK.

4.  **Hypertext Transfer Protocol (HTTP):** Esto es **Capa 7 (Aplicación)**.
    * Aquí verás la petición real: "GET /download.html". Es decir, "Por favor, dame la página de descargas".

> **🖼️ Referencia Visual:** Wireshark Packet Details Pane 
> * **Descripción:** Una captura de pantalla de Wireshark mostrando el panel inferior donde se expanden las capas: "Frame" (L2), "Internet Protocol" (L3), "Transmission Control Protocol" (L4) y "Hypertext Transfer Protocol" (L7).

---

### 3. El Peligro de los Protocolos Inseguros (Telnet) ⚠️
Ahora, veamos una captura de **Telnet**, un protocolo antiguo para controlar computadoras remotamente.

Al hacer clic derecho y seleccionar "Follow TCP Stream" (Seguir flujo TCP), Wireshark reconstruye toda la conversación tal cual sucedió.

**¿Qué vemos?**
* El servidor dice: "Login:".
* El usuario escribe: "fake" (usuario).
* El servidor dice: "Password:".
* El usuario escribe: "user" (contraseña).

**¡Todo está en texto plano!** Cualquiera con Wireshark en la misma red podría haber robado esas credenciales.

> **🛡️ Nota de Seguridad:** Esta es la razón por la que **NUNCA** debes usar Telnet. Siempre usa **SSH (Secure Shell)**, que cifra toda esta conversación para que, si alguien la captura con Wireshark, solo vea basura ilegible.

---

### 4. Analizando FTP (Transferencia de Archivos) 📂
Con FTP pasa lo mismo. Podemos ver la "conversación" de control (usuario, contraseña, comandos) y luego la transferencia de datos. Aunque no veas el archivo como tal inmediatamente, un experto forense podría "reconstruir" el archivo descargado (una imagen, un documento) a partir de los paquetes capturados.

---

### 🎓 Resumen para llevar
* **Wireshark** captura tráfico de red para análisis y solución de problemas.
* Puedes ver las capas del modelo OSI desplegadas en cada paquete: **Ethernet (L2)**, **IP (L3)**, **TCP/UDP (L4)** y **HTTP/FTP (L7)**.
* Protocolos como **Telnet** y **FTP** envían datos en texto plano, lo que es un riesgo de seguridad enorme.
* Herramientas como esta son vitales tanto para **arreglar redes** (ver por qué falla una conexión) como para **ciberseguridad** (ver qué hizo un atacante).