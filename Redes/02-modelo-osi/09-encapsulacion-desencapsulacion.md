# 9 - Encapsulación y Desencapsulación: El Viaje del Paquete 📦
> **🎯 Objetivo:** Comprenderás el proceso vital que hace que los datos viajen desde tu pantalla hasta el mundo y viceversa. Es como aprender a envolver y desenvolver un regalo capa por capa para que llegue perfecto a su destino.

---

### 1. ¿Qué es Encapsulación? (La Carta a la Abuela) 👵
Imagina que escribes una carta a tu abuela.
1.  Escribes el contenido (Capa 7 - Aplicación).
2.  La metes en un sobre (Capa 4 - Transporte).
3.  Escribes la dirección en el sobre (Capa 3 - Red).
4.  La metes en el buzón o camión de correo (Capa 2 - Enlace).

Este proceso de "envolver" los datos añadiendo información extra (encabezados/headers) se llama **Encapsulación**. [cite_start]Ocurre cuando los datos bajan de la Capa 7 a la 1[cite: 489, 491].

**Desencapsulación:** Es el proceso inverso. Cuando tu abuela recibe la carta, abre el sobre y tira lo de afuera para quedarse con el mensaje. [cite_start]Ocurre cuando los datos suben de la Capa 1 a la 7[cite: 490, 492].

---

### 2. PDUs: Los Nombres Cambiantes de los Datos 🏷️
A medida que envolvemos el regalo, le cambiamos el nombre. [cite_start]Estas son las **Unidades de Datos de Protocolo (PDU)**[cite: 496]:

| Capa | Nombre del PDU | Mnemotecnia (Inglés) |
| :--- | :--- | :--- |
| **Capa 4 (Transporte)** | Segmentos (TCP) / Datagramas (UDP) | **S**ome |
| **Capa 3 (Red)** | Paquetes | **P**eople |
| **Capa 2 (Enlace)** | Tramas (Frames) | **F**ear |
| **Capa 1 (Física)** | Bits | **B**irthdays |

> **💡 Nota del Mentor:** Memoriza esto: **S**egmentos -> **P**aquetes -> **T**ramas -> **B**its. Es vital para el examen y para hablar con propiedad técnica.

---

### 3. Las Capas de la Cebolla (Detalle Técnico) 🧅

#### A. Capa 4 (Transporte) - Segmentos
Aquí añadimos puertos de origen y destino.
* **TCP Header (20 bytes):** Es complejo. [cite_start]Tiene números de secuencia, acuses de recibo y **Banderas (Flags)**[cite: 501].
    * **SYN:** Sincronizar (Iniciar conexión).
    * **ACK:** Acuse de recibo ("Te escuché").
    * **FIN:** Finalizar conexión.
    * **RST:** Resetear (Error, corta la conexión).
    * **PSH (Push):** Procesa esto ya.
    * **URG (Urgent):** Prioridad máxima.
* **UDP Header (8 bytes):** Es simple. [cite_start]Solo puertos, longitud y checksum[cite: 516].

#### B. Capa 3 (Red) - Paquetes
[cite_start]Aquí añadimos las **Direcciones IP** (Origen y Destino)[cite: 528, 529]. Es como poner la dirección de la casa en el sobre.

#### C. Capa 2 (Enlace de Datos) - Tramas
[cite_start]Aquí añadimos las **Direcciones MAC** (Físicas) y el **EtherType** (que dice qué protocolo va dentro, como IPv4)[cite: 531, 534].
* **MTU (Maximum Transmission Unit):** Es el tamaño máximo del paquete que cabe en la trama. [cite_start]Por defecto en Ethernet es **1500 bytes**[cite: 546]. [cite_start]Si es más grande, se llama *Jumbo Frame*[cite: 547].

> **🖼️ Referencia Visual:** Data Encapsulation Process Diagram
> * **Descripción:** Un diagrama mostrando cómo los datos bajan por el modelo OSI, ganando un encabezado nuevo en cada capa (L4 Header + Data -> L3 Header + L4 + Data, etc.), hasta convertirse en bits.

---

### 4. El Viaje Completo (Resumen) 🚀
1.  **Capa 4:** Añadimos Puertos (Aplicación destino).
2.  **Capa 3:** Añadimos IPs (Dirección lógica).
3.  **Capa 2:** Añadimos MACs (Dirección física local).
4.  **Capa 1:** Enviamos Bits (Luz/Electricidad).

El dispositivo receptor hace lo contrario (Desencapsula): lee la MAC (¿es para mí?), lee la IP, lee el Puerto y entrega los datos a la aplicación.

---

### 🎓 Resumen para llevar
* **Encapsulación** es bajar (añadir headers); [cite_start]**Desencapsulación** es subir (quitar headers)[cite: 491, 492].
* [cite_start]**TCP** usa Banderas (Flags) como SYN, ACK, FIN para controlar la conexión[cite: 506].
* **MTU** estándar es 1500 bytes. [cite_start]Más grande es Jumbo Frame[cite: 546, 547].
* [cite_start]En cada capa, los datos tienen un nombre distinto (PDU): Segmento -> Paquete -> Trama -> Bit[cite: 498].