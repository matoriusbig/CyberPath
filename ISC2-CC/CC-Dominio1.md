# 🛡️ Dominio 1: Principios de Seguridad (ISC)² CC

Este *write-up* cubre los conceptos fundamentales del **Dominio 1: Principios de Seguridad** de la certificación (CC) de (ISC)². El objetivo es desglosar los pilares sobre los que se construye toda la ciberseguridad.

---

## 1.1 Los Pilares: La Tríada de la CIA

En ciberseguridad, todo gira en torno a proteger los **activos** (principalmente, la información). Para definir qué significa "proteger", usamos la Tríada de la CIA.

> Piénsalo como las tres patas de un taburete: si falla una, todo el sistema se cae.

### 1. Confidencialidad (El Secreto 🤫)
* **Definición Clara:** Asegurarse de que solo las personas autorizadas puedan ver la información.
* **El Desafío:** No se trata de esconderlo todo, sino de regular el acceso. RRHH debe poder ver los salarios de todos, pero un desarrollador no.
* **Ejemplo Práctico:** El **cifrado**. Cuando envías un WhatsApp, el mensaje va cifrado "de extremo a extremo". Si alguien lo intercepta, solo verá un galimatías ilegible.
* **Términos Clave:**
    * `PII (Información de Identificación Personal)`: Cualquier dato que pueda identificar a una persona (Ej: tu RUT, nombre + dirección).
    * `PHI (Información de Salud Protegida)`: Tu historial médico. Es un tipo de PII extremadamente sensible.

### 2. Integridad (La Confianza 🤝)
* **Definición Clara:** Asegurarse de que la información es exacta, completa y no ha sido modificada sin autorización.
* **El Desafío:** Debemos confiar en nuestros datos. Si los datos pueden ser alterados, no sirven de nada.
* **Ejemplo Práctico:** Una transferencia bancaria. Si envías $10.000, la integridad garantiza que el banco reciba $10.000, y no $1.000 (corrupción accidental) o $100.000 (modificación maliciosa).
* **Términos Clave:**
    * `Baseline (Línea Base)`: ¿Cómo sabes si un archivo del sistema fue modificado por un virus? Porque tienes una "foto" de cómo se veía cuando estaba limpio (la baseline). Si no coinciden, ¡alerta roja!

### 3. Disponibilidad (La Luz Encendida 💡)
* **Definición Clara:** Asegurarse de que los sistemas y los datos estén accesibles para los usuarios autorizados cuando los necesiten.
* **El Desafío:** No significa que deba funcionar el 100% del tiempo, sino que debe cumplir con las necesidades del negocio.
* **Ejemplo Práctico:** Un ataque **DDoS (Denegación de Servicio Distribuido)**. Un atacante inunda un e-commerce con tanto tráfico basura que los usuarios legítimos no pueden entrar. La información sigue siendo confidencial e íntegra, pero la disponibilidad se ha roto.
* **Términos Clave:**
    * `Criticidad`: ¿Qué tan importante es el sistema? Un e-commerce en Black Friday tiene una criticidad altísima.

---

## 1.2 Más Allá de la Tríada: Conceptos Clave de Acceso

### Autenticación (¿Realmente eres tú? 🆔)
Es el proceso de **probar** tu identidad. Existen 3 factores:
* 🧠 **Algo que sabes:** Una contraseña, un PIN.
* 📱 **Algo que tienes:** Tu celular (para un código 2FA), un token USB (YubiKey).
* 👁️ **Algo que eres:** Biometría (tu huella digital, tu cara).

> [!WARNING]
> **¡Ojo con esto!** Pedir un usuario y una contraseña **NO es MFA**. Ambos son "Algo que sabes".
> **MFA (Autenticación Multifactor) real es:** Tu contraseña (sabes) + un código de tu celular (tienes).

### No Repudio (Sin "Yo No Fui" ✍️)
Un concepto legal que crea una prueba irrefutable de que una persona específica realizó una acción. (Ej: una firma digital).

### Privacidad (Tu Derecho a Controlar 🔐)
Es el derecho de un individuo a controlar cómo se recopila, usa y distribuye su información personal.
> Puedes tener seguridad sin privacidad (una red social segura que legalmente vende tus datos), pero **no puedes tener privacidad sin seguridad**.

---

## 1.3 El Núcleo del Negocio: Gestión de Riesgos

Nuestro trabajo no es eliminar todo el peligro (es imposible), sino **gestionar el riesgo** a un nivel aceptable para la organización.

> [!IMPORTANT]
> **¿Qué es el Riesgo?** En seguridad, el Riesgo tiene una fórmula:
> `Riesgo = Impacto x Probabilidad`

Es una medida que combina el impacto adverso (cuánto dolería si algo malo pasa) con la probabilidad de que ese "algo malo" realmente ocurra.

### Los 3 Componentes del Riesgo
Para que exista un riesgo, necesitamos tres componentes que se crucen:
1.  **Activo:** Es lo que queremos proteger (Ej: la base de datos de clientes).
2.  **Vulnerabilidad:** Es una debilidad o brecha en nuestras defensas (Ej: un software sin actualizar).
3.  **Amenaza:** Es algo o alguien que puede explotar esa vulnerabilidad (Ej: un ciberdelincuente).

#### 🕵️ Caso de Estudio: El Carterista
* **Activo:** Tu billetera.
* **Amenaza:** Un carterista (actor de amenaza) que está en la zona.
* **Vulnerabilidad:** El turista está distraído y lleva la billetera en el bolsillo trasero.
* **Riesgo:** La alta probabilidad de que el carterista (Amenaza) explote la distracción (Vulnerabilidad) para robar la billetera (Activo).

### El Proceso de Gestión de Riesgos
Gestionar el riesgo es un ciclo continuo:
1.  **Identificación:** Encontrar los riesgos. ("¿Qué podría salir mal?").
2.  **Evaluación (Priorización):** Analizar el impacto y la probabilidad. Usamos una Matriz de Riesgo. Un riesgo de Impacto Alto y Probabilidad Alta (como un ransomware) es una Prioridad Alta (🔥).
3.  **Tratamiento:** Una vez priorizado el riesgo, tenemos 4 opciones.

### Las 4 Formas de Tratar el Riesgo
#### 🦈 Caso de Estudio: El Negocio de Nadar con Tiburones
* **Aceptación (Accept):** Aceptar el riesgo y no hacer nada. Se usa cuando el costo de arreglarlo es mayor que el daño.
    * *Ejemplo:* La dueña acepta el riesgo inherente de que trabajar con tiburones salvajes es peligroso. Es parte del negocio.
* **Evitación (Avoid):** Eliminar el riesgo por completo deteniendo la actividad que lo causa.
    * *Ejemplo:* Evitan el riesgo decidiendo no salir al mar cuando hay mal tiempo.
* **Mitigación (Mitigate):** Es la opción más común. Reducir la probabilidad o el impacto implementando controles.
    * *Ejemplo:* Mitigan el riesgo usando jaulas de acero fuertes (control físico). En ciberseguridad, esto es instalar un Firewall.
* **Transferencia (Transfer):** Pasar el riesgo (generalmente el impacto financiero) a un tercero.
    * *Ejemplo:* Compran una póliza de seguro. Si ocurre un accidente, la aseguradora asume el costo financiero.

### Apetito y Tolerancia al Riesgo
* **Apetito de Riesgo:** La cantidad total de riesgo que una organización está dispuesta a asumir para lograr sus objetivos.
* **Tolerancia al Riesgo:** El nivel específico de riesgo aceptable para un área. (Ej: "Nuestra tolerancia a una caída del e-commerce es CERO").

---

## 1.4 Controles de Seguridad (Nuestras Defensas)
Si el riesgo es el problema, los **controles** son la solución (o, más bien, la mitigación). Un control es una salvaguarda que implementamos para proteger la Tríada CIA.

### 1. Controles Físicos 🚪
Son salvaguardas tangibles que controlan el movimiento de personas y equipos.
* **Ejemplos:** Cerraduras, guardias, puertas de acceso, lectores de credenciales, extintores, generadores de respaldo.

### 2. Controles Técnicos 💻 (Lógicos)
Son las salvaguardas implementadas directamente en el software y el hardware.
* **Ejemplos:** Listas de Control de Acceso (ACLs), Firewalls, Cifrado, Biometría (Face ID), Sistemas de Detección de Intrusos (IDS).

### 3. Controles Administrativos 📜 (Gerenciales)
Son las reglas del juego para las personas. Se centran en las directivas, políticas y procedimientos.
* **Ejemplos:** Política de Uso Aceptable (AUP), Capacitación de Concienciación de Seguridad (¡el más importante!), Políticas de contratación y despido.

### 💡 Poniéndolo Todo Junto: Conectando Controles y la CIA

| Control | Tipo de Control | Cómo Protege la Tríada CIA |
| :--- | :--- | :--- |
| **Cerradura en un Archivador** | Físico | Protege la **Confidencialidad** (nadie ve los papeles) y la **Integridad** (nadie los modifica). |
| **Generador de Respaldo** | Físico | Protege la **Disponibilidad** durante un corte de energía. |
| **Política de Contraseñas** | Administrativo (la regla) + Técnico (el sistema que la obliga) | Protege la **Confidencialidad** (impide acceso) y la **Integridad** (impide cambios). |
| **Cifrado de Datos** | Técnico | Es el pilar de la **Confidencialidad**. También puede proteger la **Integridad**. |

---

## 1.5 Gobernanza (Las Reglas del Juego)
¿Quién decide qué controles usar? ¿Y por qué? Esa es la **Gobernanza**: el sistema de reglas, prácticas y decisiones que guía a una organización.

La forma más fácil de entender esto es pensar en una pirámide jerárquica:

1.  **Leyes y Regulaciones (El "Deber"):** Es lo que el gobierno nos exige.
2.  **Estándares (El "Marco"):** Son las "mejores prácticas" que usamos como guía.
3.  **Políticas (El "Qué"):** Son las reglas internas de nuestra empresa.
4.  **Procedimientos (El "Cómo"):** Son los pasos detallados para hacer una tarea.

### 1. Leyes y Regulaciones ⚖️
Son las reglas impuestas por un gobierno. Su incumplimiento conlleva multas o incluso cárcel.
* **Ejemplos Clave:** **HIPAA** (Ley de EE.UU. para datos de salud - `PHI`) y **GDPR** (Reglamento de la UE para datos personales - `PII`).
* **Punto Crítico:** El GDPR tiene alcance internacional. No importa si tu empresa está en Chile; si manejas datos de un ciudadano de la UE, debes cumplir con el GDPR.

### 2. Estándares 📚
Son los "marcos" y "mejores prácticas" que usamos para construir nuestras políticas.
* **Organismos Clave:**
    * `ISO (Organización Internacional de Normalización)`: Estándares globales (Ej: ISO 27001).
    * `NIST (Instituto Nacional de Estándares y Tecnología de EE.UU.)`: Sus publicaciones son gratuitas y se usan como referencia mundial.
    * `IETF (Grupo de Trabajo de Ingeniería de Internet)`: Define los protocolos que hacen que Internet funcione (TCP/IP).

### 3. Políticas 📜
Reglas internas de la organización. Son de alto nivel y definen "el qué".
* *Ejemplo:* "Todos los empleados deben proteger la información de la empresa".

### 4. Procedimientos 📋
Instrucciones paso a paso que definen "el cómo".
* *Ejemplo:* **Política:** "Se debe gestionar el acceso de los empleados de forma segura". **Procedimiento:** "1. RRHH envía el formulario X-10. 2. El gerente aprueba los permisos Y. 3. El equipo de TI crea la cuenta...".

---

## 1.6 El Código de Ética (El Cimiento Profesional)
Este es el dominio que nos define como profesionales. La ciberseguridad es una profesión de **confianza**.

### Los 4 Cánones del Código de Ética (ISC)²
1.  Proteger la sociedad, el bien común, la confianza pública y la infraestructura.
    * *En simple:* Nuestra primera lealtad es con la gente.
2.  Actuar honorable, honesta, justa, responsable y legalmente.
    * *En simple:* Ser una de las "personas buenas".
3.  Brindar un servicio diligente y competente a los "principales" (empleadores y clientes).
    * *En simple:* Hacer bien nuestro trabajo y proteger a quienes confían en nosotros.
4.  Avanzar y proteger la profesión.
    * *En simple:* Cuidar la reputación de nuestra industria y ser un mentor.

### ⚖️ Ética en la Práctica: Casos de Estudio
* **Caso 1: El Administrador "Vigilante"**
    * *Escenario:* Un admin de red (Admin A) tiene un conflicto personal con un usuario (Usuario B). Usando sus privilegios de administrador, "caza" al Usuario B hasta que lo encuentra violando una política menor y lo reporta.
    * *Violación Ética:* El Admin A violó los Cánones 2 y 3. Abusó de la confianza y los privilegios que se le dieron (no actuó honorablemente) para un fin personal.

---

## 📖 Glosario de Términos del Dominio 1

* **Activo:** Cualquier cosa de valor que es propiedad de una organización (datos, servidores, reputación).
* **Actor de amenazas:** Un individuo o grupo que intenta explotar vulnerabilidades.
* **Amenaza:** Cualquier circunstancia o evento con el potencial de causar daño.
* **Análisis de Riesgo Cualitativo:** Método de análisis de riesgo basado en descriptores (Bajo, Medio, Alto).
* **Análisis de Riesgo Cuantitativo:** Método de análisis de riesgo basado en valores numéricos (monetarios).
* **Autenticación:** Proceso que valida la identidad de un usuario (probando que eres quien dices ser).
* **Autorización:** El permiso que se otorga a un usuario para acceder a un recurso (lo que se te permite hacer).
* **Baseline (Línea Base):** Un nivel documentado de configuración de seguridad o estado "limpio" de un sistema.
* **Cifrado (Encripción):** Proceso de convertir texto plano a texto cifrado para proteger la confidencialidad.
* **Confidencialidad:** Asegurar que la información no se revele a personas o procesos no autorizados.
* **Controles (Administrativos, Físicos, Técnicos):** Salvaguardas para reducir el riesgo.
* **Criticidad:** El grado en que una organización depende de un sistema para su misión.
* **Disponibilidad:** Asegurar el acceso y uso oportuno y confiable de la información por parte de usuarios autorizados.
* **Evaluación de riesgos:** El proceso de identificar y analizar los riesgos.
* **GDPR (Reglamento General de Protección de Datos):** Legislación de la UE sobre privacidad personal.
* **Gestión de riesgos:** El proceso de identificación, evaluación y control de amenazas.
* **Gobernanza:** El proceso de cómo se gestiona una organización (políticas, roles, decisiones).
* **HIPAA (Ley de Portabilidad y Responsabilidad del Seguro Médico):** Ley de EE. UU. que regula la información de salud (PHI).
* **Impacto:** La magnitud del daño que podría causar una amenaza.
* **Integridad:** Asegurar que la información no ha sido alterada de manera no autorizada.
* **ISO (Organización Internacional de Normalización):** Desarrolla estándares internacionales (Ej: ISO 27001).
* **MFA (Autenticación de Múltiples Factores):** Usar dos o más tipos de factores de autenticación (saber, tener, ser).
* **NIST (Institutos Nacionales de Estándares y Tecnología):** Agencia de EE. UU. que establece estándares de tecnología y seguridad.
* **No repudio:** La incapacidad de negar haber realizado una acción.
* **PHI (Información de Salud Protegida):** Información sobre el estado de salud, protegida por HIPAA.
* **PII (Información de Identificación Personal):** Información que puede usarse para identificar a un individuo (nombre, RUT, etc.).
* **Privacidad:** El derecho de un individuo a controlar cómo se distribuye su información personal.
* **Probabilidad:** Las posibilidades de que una amenaza explote una vulnerabilidad.
* **Riesgo:** Un evento posible que puede tener un impacto negativo. (Riesgo = Impacto x Probabilidad).
* **Tolerancia al riesgo:** El nivel de riesgo que una entidad está dispuesta a asumir (también "apetito por el riesgo").
* **Tratamiento de riesgos:** La determinación de cómo abordar un riesgo: Aceptar, Evitar, Mitigar o Transferir.
* **Vector de amenazas:** Los medios por los cuales un actor de amenazas lleva a cabo su objetivo (Ej: un correo de phishing).
* **Vulnerabilidad:** Debilidad en un sistema, procedimiento o control que podría ser aprovechada por una amenaza.
