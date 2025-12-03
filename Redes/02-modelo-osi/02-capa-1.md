# Capa 1 (Física): Donde los Datos Tocan el Cable 🔌
> **🎯 Objetivo:** Entenderás cómo la "magia" del software se convierte en señales eléctricas, de luz o de radio reales. Sin esta capa, internet sería solo una idea imaginaria. Aquí es donde los bits (1s y 0s) viajan físicamente.

---

### 1. El Lenguaje de los Bits: Voltaje vs. Luz 💡
Imagina que quieres comunicarte con un vecino usando una linterna. Si enciendes la luz es un "Sí" (1), si la apagas es un "No" (0). En el nivel más bajo, las computadoras hacen exactamente esto.

En la **Capa Física (Layer 1)**, no nos importan las aplicaciones ni las direcciones IP. Solo nos importa **cómo representar un bit** (un 1 o un 0) en el medio físico.

* **Cobre (Cables Ethernet Cat 5/6):** Usamos electricidad.
    * **0:** Cero voltaje.
    * **1:** +5 voltios (o -5 voltios).
* **Fibra Óptica:** Usamos luz.
    * **0:** Luz apagada.
    * **1:** Luz encendida.

> **💡 Nota del Mentor:** Existe un concepto llamado **Modulación de Transición**. No necesitas memorizar la física detrás de esto para el examen, pero entiende el concepto básico: es el cambio entre estados (voltaje o luz) lo que le dice al dispositivo si está leyendo un 1 o un 0.

---

### 2. Cables y Conectores: Las Tuberías de la Red 🛠️
Para que la electricidad o la luz viajen, necesitamos carreteras. Aquí entran los cables y sus conectores (como el famoso **RJ45** que conectas a tu PC).

Pero, ¿cómo ordenamos los cables de colores dentro del conector? Hay dos estándares mundiales que **debes** conocer:

1.  **TIA/EIA-568A**
2.  **TIA/EIA-568B**

¿Por qué importan? Porque definen qué tipo de cable estás creando:

| Tipo de Cable | Configuración de Extremos | Uso Típico |
| :--- | :--- | :--- |
| **Cable Directo (Straight-through)** | Ambos extremos son **B** (o ambos A). | Conectar PC a Switch (dispositivos diferentes). |
| **Cable Cruzado (Crossover)** | Un extremo es **A** y el otro es **B**. | Conectar PC a PC o Switch a Switch (dispositivos iguales). |

> **🖼️ Referencia Visual:** Diagrama de Pines T568A vs T568B 

[Image of T568A vs T568B pinout diagram]

> * **Descripción:** Una imagen que muestre el orden de colores de los 8 cables para el estándar A y para el estándar B lado a lado.

---

### 3. Sincronización: El Ritmo de la Conversación 🥁
Cuando envías bits, el receptor necesita saber cuándo leerlos. Es como hablar: necesitas pausas y ritmo.

* **Comunicación Asíncrona (El Buzón de Voz):**
    * Imagina dejar un mensaje de voz. No necesitas que tu amigo esté al otro lado en ese momento.
    * En redes, usamos un **bit de inicio** y un **bit de parada** para decir "Aquí va un mensaje... y aquí termina". No hay un reloj constante.

* **Comunicación Síncrona (La Llamada en Vivo):**
    * Ambos están en la línea al mismo tiempo.
    * En redes, usamos un **Reloj de Referencia** común. Ambos dispositivos se ponen de acuerdo en el "tic-tac" del reloj y envían datos en cada segundo (o microsegundo) exacto.

---

### 4. Ancho de Banda: ¿Autopista o Carril Único? 🛣️
¿Cómo usamos el cable para enviar información?

* **Banda Ancha (Broadband):**
    * **Analogía:** La TV por Cable. Un solo cable llega a tu casa, pero trae 200 canales a la vez. Tú sintonizas uno, pero todos están ahí. Divide el cable en múltiples "canales" de frecuencia.
* **Banda Base (Baseband):**
    * **Analogía:** Un teléfono antiguo o un Walkie-Talkie. Cuando hablas, ocupas **toda** la línea. Nadie más puede usarla mientras tú transmites. Ethernet tradicional usa esto (usa todo el ancho de banda disponible).

> **🖼️ Referencia Visual:** Broadband vs Baseband 
> * **Descripción:** Un gráfico que muestre la Banda Base como una única señal ancha ocupando todo el espectro, y la Banda Ancha como múltiples señales más delgadas viajando juntas.

---

### 5. Multiplexación: Compartiendo el Sofá 📺
Si usamos Banda Base (un solo canal), ¿cómo dejamos que varias personas usen la red? Usamos **Multiplexación** (hacer más eficiente un recurso limitado).

Imagina una familia con **una sola TV** pero 4 personas queriendo ver cosas distintas:

1.  **TDM (Time-Division Multiplexing):**
    * *El Horario Rígido:* Papá ve la TV de 8:00 a 8:30. Mamá de 8:30 a 9:00. Si Papá no está, la TV se queda apagada de 8:00 a 8:30. Nadie más puede usar su turno. Ineficiente.
2.  **StatTDM (Statistical TDM):**
    * *El Horario Inteligente:* Se asignan turnos dinámicamente. Si Papá no está a las 8:00, Mamá puede tomar ese turno. Es mucho más eficiente.
3.  **FDM (Frequency-Division Multiplexing):**
    * *Pantalla Dividida:* Dividimos la pantalla en 4 cuadros y todos ven su programa al mismo tiempo (como en Banda Ancha).

---

### 6. Dispositivos de Capa 1: Los "Repetidores Tontos" 📢
Finalmente, ¿qué aparatos viven aquí? Son dispositivos que **no toman decisiones inteligentes**. No saben de direcciones ni de datos. Solo ven electricidad o luz y la empujan hacia adelante.

* **Cables:** (Fibra, Coaxial, Ethernet). Lo que entra por un lado, sale por el otro.
* **Hub (Concentrador):** Es un repetidor multipuerto. Si entra un dato por el puerto 1, el Hub lo "grita" ciegamente por los puertos 2, 3 y 4. No tiene cerebro.
* **Media Converter:** Convierte fibra a cobre. Entra luz, sale electricidad. Simple transformación física.
* **Wi-Fi / Bluetooth:** Las ondas de radio en sí mismas son Capa 1.

> **🛡️ Nota de Seguridad:** Como los **Hubs** repiten todo a todos, son terribles para la seguridad. Si conectas una herramienta de hackeo a un Hub, podrás ver el tráfico de todos los demás usuarios conectados. Por eso ya casi no los usamos.

---

### 🎓 Resumen para llevar
* La **Capa 1 (Física)** trata sobre **Bits** (1s y 0s), **Voltaje** y **Luz**.
* **568A y 568B** son los estándares de cableado. Cable cruzado (A con B) para dispositivos iguales; Directo (B con B) para diferentes.
* **Síncrono** usa un reloj; **Asíncrono** usa bits de inicio/parada.
* **Banda Ancha** divide el cable en canales (TV); **Banda Base** usa todo el cable (Ethernet).
* [cite_start]Los dispositivos de Capa 1 (Cables, Hubs) son **tontos**: solo repiten señales, no leen datos[cite: 2509].