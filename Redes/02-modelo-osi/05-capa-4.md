# Capa 4 (Transporte): El Director de Orquesta 🎻
> **🎯 Objetivo:** Entenderás cómo controlamos el flujo del tráfico para que los datos lleguen completos y en orden. Aquí decidimos si queremos velocidad pura o confiabilidad total. [cite_start]Es la frontera entre el hardware (red) y el software (aplicación)[cite: 1301].

---

### 1. ¿Qué es la Capa de Transporte? (El Intermediario) 🤝
Imagina que las capas inferiores (1, 2 y 3) son los camiones y carreteras que mueven cosas. Las capas superiores (5, 6 y 7) son las personas que escriben y leen las cartas. [cite_start]La **Capa 4 (Transporte)** es el **sistema de gestión de envíos** que conecta ambos mundos[cite: 1302].

Aquí es donde decidimos *cómo* se envían los datos. ¿Queremos un acuse de recibo de cada paquete? ¿O simplemente queremos enviarlos lo más rápido posible?

Dependiendo del protocolo que elijamos, a los datos en esta capa les llamamos de dos formas:
* [cite_start]**Segmentos:** Si usamos TCP[cite: 1304].
* [cite_start]**Datagramas:** Si usamos UDP[cite: 1320].

---

### 2. TCP: El "Correo Certificado" Confiable 📨
**TCP (Transmission Control Protocol)** es el obsesivo del control. [cite_start]Es un protocolo **orientado a la conexión**[cite: 1307].

**La Analogía:**
Imagina que envías documentos importantes a Hacienda (Impuestos). No los tiras a un buzón cualquiera. Los envías por **correo certificado**. Necesitas que alguien firme al recibirlo y te devuelva un recibo. Si no recibes el recibo, envías el documento de nuevo. Así es TCP.

**El Apretón de Manos de Tres Vías (Three-Way Handshake):**
[cite_start]Antes de enviar un solo dato, TCP establece una conexión formal así[cite: 1309]:
1.  [cite_start]**SYN (Sincronización):** Cliente dice: "¿Hola? Quiero hablar contigo"[cite: 1309].
2.  [cite_start]**SYN-ACK (Sincronización-Acuse):** Servidor dice: "Te escucho y estoy listo"[cite: 1310].
3.  [cite_start]**ACK (Acuse):** Cliente dice: "Perfecto, allá voy"[cite: 1311].

> **🖼️ Referencia Visual:** TCP 3-Way Handshake Diagram
> * **Descripción:** Un diagrama mostrando tres flechas entre un Cliente y un Servidor etiquetadas como SYN, SYN-ACK y ACK.

---

### 3. UDP: El "Dispara y Olvida" Veloz 🚀
**UDP (User Datagram Protocol)** es el relajado del grupo. [cite_start]Es un protocolo **sin conexión**[cite: 1316].

**La Analogía:**
Imagina ver un video en vivo. Si se pierde un pixel o un milisegundo de audio, no quieres que el video se detenga para "re-enviar" ese pixel perdido. Prefieres que el video siga fluyendo. UDP lanza los datos (Datagramas) y no le importa si llegan o no. [cite_start]Es "disparar y olvidar"[cite: 1556].

[cite_start]**Tabla de Batalla: TCP vs UDP** [cite: 1321-1332]

| Característica | TCP (Segmentos) | UDP (Datagramas) |
| :--- | :--- | :--- |
| **Confiabilidad** | Alta (Fiable) | Baja (No fiable) |
| **Conexión** | Orientado a conexión (Handshake) | Sin conexión (Connectionless) |
| **Errores** | Reenvía datos perdidos | No reenvía nada |
| **Orden** | Secuencia los datos (1, 2, 3...) | No hay secuencia (llegan como sea) |
| **Uso Típico** | Web (HTTP), Email, Banca | Streaming de Video/Audio, Juegos Online |

> **💡 Nota del Mentor:** Para el examen, recuerda esto: **TCP = Segmentos, UDP = Datagramas**. [cite_start]Si ves "Datagrama", es Capa 4 y es UDP[cite: 1319].

---

### 4. Control de Flujo: Ventanas y Buffering 🚦
La Capa 4 no solo envía, también controla la velocidad para que nadie se sature.

#### A. Ventanas (Windowing) 🪟
[cite_start]Es cómo el cliente y el servidor negocian cuántos datos enviar antes de detenerse a esperar un "OK" (Acuse de recibo)[cite: 1333].

* **Analogía:** Si te dicto números.
    * Empiezo lento: "Uno... dos...". Tú dices "OK".
    * Acelero (abro la ventana): "Tres, cuatro, cinco, seis...". Tú dices "OK".
    * Si voy muy rápido y te pierdes, me dices "¡Espera!". [cite_start]Entonces, reduzco la velocidad (cierro la ventana)[cite: 1334].

#### B. Buffering (Amortiguación) ⏳
Los routers tienen memoria temporal (RAM). [cite_start]Si llegan demasiados datos a la vez y el router no puede procesarlos, los guarda en un **Buffer**[cite: 1336].
* **El Riesgo:** Si el buffer se llena (se desborda), el router no tiene más remedio que empezar a **tirar paquetes** (drop packets).

> **🖼️ Referencia Visual:** TCP Sliding Window Mechanism
> * **Descripción:** Un gráfico que muestre cómo el tamaño de la ventana (cantidad de datos) aumenta o disminuye dinámicamente según la recepción exitosa de los paquetes.

---

### 5. Dispositivos de Capa 4 🛡️
Aunque los routers son de Capa 3, hay dispositivos que entienden y toman decisiones basadas en puertos y protocolos (TCP/UDP):
1.  [cite_start]**Firewalls:** Pueden bloquear puertos específicos (ej: Bloquear puerto 80 TCP)[cite: 1340].
2.  [cite_start]**Balanceadores de Carga:** Distribuyen el tráfico a diferentes servidores basándose en el tipo de servicio[cite: 1340].

> [cite_start]**🛡️ Nota de Seguridad:** Cuando configuras un firewall para bloquear el puerto 80 (Web), estás actuando en Capa 4, porque estás filtrando basado en el puerto y el protocolo (TCP), no solo en la dirección IP[cite: 1535].

---

### 🎓 Resumen para llevar
* La **Capa 4** se encarga de la entrega confiable (o no) de los datos.
* **TCP** es confiable, lento, usa sesiones y acuses de recibo (Segmentos).
* **UDP** es rápido, no confiable, ideal para streaming (Datagramas).
* El **Windowing** ajusta la velocidad de transmisión dinámicamente.
* El **Buffering** almacena datos temporalmente; si se llena, se pierden datos.