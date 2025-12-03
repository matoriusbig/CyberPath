# 4 - Capa 3 (Red): El GPS de Internet 🧭
> **🎯 Objetivo:** Aprenderás cómo los datos encuentran su camino a través del laberinto mundial de redes. Aquí es donde decidimos la *mejor ruta* para que tu mensaje llegue a su destino, sin importar en qué parte del mundo esté.

---

### 1. ¿Qué hace la Capa de Red? (Enrutamiento) 🛣️
Bienvenidos a la Capa 3. Si en la Capa 2 (Enlace de Datos) nos preocupábamos por llegar al dispositivo de al lado (usando direcciones MAC), en la **Capa 3 (Red)** nos preocupamos por llegar al destino final, que puede estar al otro lado del planeta.

Aquí nos enfocamos en dos cosas principales:
1.  **Direccionamiento Lógico:** Usamos direcciones IP (IPv4 o IPv6) para identificar "quién" es el destino.
2.  **Enrutamiento (Routing):** Decidir "por dónde" enviar los datos.

> **💡 Nota del Mentor:** A veces escucharás el término "Conmutación de Capa 3" (*Layer 3 Switching*). ¡No te confundas! Aunque usa la palabra "Switching", en realidad se refiere a la función de **Enrutamiento**. Recuerda:
> * Switch (físico) = Capa 2 (generalmente).
> * Enrutamiento = Capa 3.

---

### 2. Direccionamiento Lógico: Tu Dirección Postal 🏠
A diferencia de la dirección MAC (que es física y permanente, como tu huella digital), la dirección IP es lógica y puede cambiar (como tu dirección postal).

Históricamente existían otros protocolos como AppleTalk o IPX, pero el rey indiscutible hoy es el **Protocolo de Internet (IP)**. Lo verás en dos sabores:
* **IPv4:** El clásico (ej: `172.16.254.1`). Son 4 grupos de números.
* **IPv6:** El moderno, mucho más largo y complejo, diseñado porque se nos acabaron las direcciones IPv4.

> **🖼️ Referencia Visual:** IPv4 Packet Structure
> * **Descripción:** Un diagrama que muestre una dirección IP dividida en sus 4 octetos, y quizás una comparación visual simple con una dirección IPv6.

---

### 3. Métodos de Envío: La Analogía de la Carta ✉️
¿Cómo movemos los datos de A a B? Existen tres formas principales. Para entenderlas, usaremos la analogía de enviar una carta a tu madre.

**A. Conmutación de Paquetes (Packet Switching) - ¡El Estándar de Internet!**
Imagina que escribes una carta, la metes en un sobre con la dirección de tu madre y la echas al buzón.
1.  El cartero la lleva a la oficina local.
2.  La oficina local ve el estado y la manda a la central regional.
3.  La central la manda a la ciudad de tu madre.
4.  Finalmente llega a su casa.

No te importa si el camión de correo tomó la autopista A o la carretera B, siempre y cuando la carta llegue. **Así funciona Internet (IP).** Cortamos los datos en pedacitos (paquetes) y cada uno busca su mejor camino.

**B. Conmutación de Circuitos (Circuit Switching)**
Esto es como una llamada telefónica antigua. Cuando llamas, se establece un cable físico (o circuito virtual) dedicado *solo para ti* entre tu teléfono y el de tu madre.
* **Ventaja:** La ruta es fija y exclusiva.
* **Desventaja:** Si cuelgas y vuelves a llamar, podrías obtener una ruta distinta, pero mientras hablas, ocupas esa línea.

**C. Conmutación de Mensajes (Message Switching)**
Es como el correo electrónico o un sistema de "almacenar y reenviar" (*Store and Forward*).
Si la carta llega a la oficina postal y está cerrada por ser domingo, no la tiran. La guardan (almacenan) y la envían el lunes (reenvían).

**Tabla Comparativa:**

| Método | Analogía | Uso Principal | Características |
| :--- | :--- | :--- | :--- |
| **Conmutación de Paquetes** | Carta por correo | **Internet / Redes Modernas** | Rutas dinámicas, eficiente. |
| **Conmutación de Circuitos** | Llamada telefónica | Redes de voz antiguas (PSTN) | Ruta dedicada y fija durante la sesión. |
| **Conmutación de Mensajes** | Correo Electrónico | Email / Sistemas tolerantes a retrasos | Almacena y reenvía (Store & Forward). |

---

### 4. El GPS de la Red: Descubrimiento de Rutas 🛰️
¿Cómo sabe un router cuál es el mejor camino? Los routers tienen una **Tabla de Enrutamiento**.

Imagina que eres el Router 5 y quieres llegar al Router 1.
* Opción A: 5 -> 4 -> 1
* Opción B: 5 -> 4 -> 3 -> 2 -> 1

¿Cuál eliges? Los routers "hablan" entre sí usando **Protocolos de Enrutamiento Dinámico** (como OSPF, RIP, EIGRP). Son como Waze o Google Maps: se avisan si hay tráfico (congestión) en una ruta y sugieren una alternativa más rápida automáticamente.

---

### 5. Servicios de Conexión: Poniendo Orden 🧩
La Capa 3 también ayuda a mantener el orden.

1.  **Control de Flujo:** Es como un policía de tránsito. Si el emisor habla muy rápido, el receptor dice: "¡Hey, más despacio! Me estoy saturando".
2.  **Reordenamiento de Paquetes:**
    * Imagina que envías un libro de 5 páginas por correo en sobres separados.
    * Debido al tráfico, llegan en este orden: Página 1, 5, 2, 4, 3.
    * La Capa 3 (gracias a la numeración de secuencia) es capaz de decir: "Esperen, ordenemos esto: 1, 2, 3, 4, 5" antes de entregar el mensaje completo.

---

### 6. ICMP: La Herramienta de Diagnóstico 🩺
En esta capa vive un protocolo muy especial: **ICMP (Internet Control Message Protocol)**. No se usa para enviar datos de usuario (como fotos o emails), sino para enviar mensajes de *estado*.

* **Ping:** Es el sonar del submarino. Envías un "Ping" a `google.com` y si responde "Pong" (Echo Reply), sabes que está vivo y cuánto tarda en responder.
* **Traceroute:** Te muestra cada salto (router) por el que pasa tu paquete hasta llegar al destino.

> **🛡️ Nota de Seguridad:** Muchos administradores bloquean el tráfico ICMP en sus firewalls para evitar que extraños "mapeen" su red o realicen ataques de denegación de servicio (DoS).

---

### 7. Dispositivos de Capa 3 🤖
¿Qué hardware vive aquí?

1.  **Router (Enrutador):** El rey de la Capa 3. Conecta diferentes redes entre sí.
2.  **Switch Multicapa (Multilayer Switch):** Es un híbrido. Físicamente parece un switch, pero tiene el cerebro de un router. Para el examen, si dice "Switch Multicapa", trátalo como un dispositivo de Capa 3.

> **🖼️ Referencia Visual:** Network Router Icon 
> * **Descripción:** El símbolo estándar de un router en diagramas de red: un círculo con cuatro flechas apuntando hacia adentro o hacia afuera en forma de cruz.

---

### 🎓 Resumen para llevar
* La **Capa 3 (Red)** se encarga del **Direccionamiento Lógico (IP)** y el **Enrutamiento**.
* Los datos aquí se llaman **Paquetes**.
* Internet usa **Conmutación de Paquetes**: la ruta no es fija, importa llegar al destino.
* **Routers** y **Switches Multicapa** son los dispositivos clave.
* **ICMP** (Ping) es tu herramienta principal para probar si un destino es alcanzable.