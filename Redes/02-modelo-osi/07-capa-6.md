# 7 - Capa 6 (Presentación): El Traductor y Guardaespaldas 🕴️
> **🎯 Objetivo:** Descubrirás cómo tu computadora traduce los unos y ceros en fotos de gatos o textos legibles, y cómo protege tus secretos bancarios mediante el cifrado.

---

### 1. ¿Qué hace la Capa de Presentación? 🎭
Imagina que recibes una carta escrita en un idioma que no entiendes. Necesitas un traductor antes de poder leerla. La **Capa 6 (Presentación)** es ese traductor universal.

Su trabajo se resume en dos palabras clave vitales para el examen: **Formateo** y **Cifrado** .

Esta capa se asegura de que los datos sean legibles para el sistema receptor y compatibles entre diferentes dispositivos. Básicamente, "presenta" los datos a la capa superior (Aplicación) en un formato que esta pueda entender .

---

### 2. El Formateo de Datos: Hablando el Mismo Idioma 🗣️
En el fondo, todo en tu computadora son series de unos y ceros. La Capa 6 decide qué significan esos números.

* **Texto (ASCII):** Es un estándar antiguo pero fundamental. Dice, por ejemplo, que el número 65 siempre es una "A" mayúscula y el 40 es una "@" . Si todos usamos ASCII, todos podemos leer el texto del otro.
* **Imágenes y Video:**
    * **GIF:** Imágenes que bailan o se mueven.
    * **JPEG:** Fotografías.
    * **PNG:** Imágenes de Internet.
    * **MP4/MOV:** Archivos de película.

La Capa 6 toma esos unos y ceros del disco duro o la red y dice: "¡Ah! Esto es una foto, debo mostrarla así en la pantalla" .

> **🖼️ Referencia Visual:** ASCII Table Chart
> * **Descripción:** Una tabla que muestra caracteres (letras, símbolos) y su equivalente numérico en código ASCII (ej: A = 65, @ = 40).

---

### 3. Cifrado: Tu Túnel de Seguridad 🔒
Aquí es donde entra el "Guardaespaldas". Si envías tu tarjeta de crédito por internet, no quieres que viaje como texto plano que cualquiera pueda leer.

La Capa 6 se encarga de **Cifrar (Encryption)**: revolver los datos para que sean ilegibles para los curiosos (confidencialidad) durante el tránsito .

* **TLS (Transport Layer Security):** Es el estándar moderno. Cuando ves el candadito 🔒 en tu navegador web (junto a Amazon o tu banco), eso es TLS en acción en la Capa 6. Crea un túnel seguro para tus datos.
* **SSL (Secure Sockets Layer):** El predecesor de TLS. Hacen lo mismo: codificar datos.

> **🛡️ Nota de Seguridad:** Aunque a veces usamos "SSL" por costumbre, **TLS** es la versión segura y moderna que debes usar. SSL está obsoleto y tiene vulnerabilidades .

---

### 4. Lenguajes de Scripting y Formato 📜
Además de imágenes y texto simple, la Capa 6 maneja lenguajes que dicen *cómo* se debe ver el texto:
* **HTML / XML / PHP / JavaScript:** Estos lenguajes le dicen a tu navegador: "Pon esta letra en **negrita**, subraya esta otra o haz esta fuente más grande" .

**Tabla de Formatos de Capa 6:**

| Tipo de Dato | Ejemplos Comunes |
| :--- | :--- |
| **Texto** | ASCII, Unicode, EBCDIC |
| **Imágenes** | JPEG, GIF, PNG, SVG, TIFF |
| **Video** | MP4, MPEG, MOV |
| **Seguridad** | TLS, SSL |

---

### 🎓 Resumen para llevar
* La **Capa 6 (Presentación)** se encarga del **Formateo** y el **Cifrado**.
* Convierte 1s y 0s en formatos que entendemos: **ASCII** (texto), **JPEG** (fotos), **MP4** (video).
* Protege los datos en tránsito usando **TLS** (el candadito del navegador).
* Prepara (negocia la sintaxis) los datos para que la Capa 7 (Aplicación) pueda usarlos.