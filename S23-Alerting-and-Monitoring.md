# Alertas y Monitorización

Las **alertas y la monitorización** permiten detectar posibles incidentes de seguridad y proteger la confidencialidad, integridad y disponibilidad de los sistemas.

## 1. Alertas de seguridad

Notifican al personal cuando se detecta un posible incidente. Pueden generarse mediante IDS/IPS, SIEM y antivirus.

- **Verdadero positivo (TP):** se detecta correctamente una amenaza real.
- **Falso positivo (FP):** se alerta sobre una amenaza inexistente.
- **Verdadero negativo (TN):** no se genera una alerta porque realmente no hay amenaza.
- **Falso negativo (FN):** no se detecta una amenaza que sí existe.

**Objetivo:** maximizar los verdaderos positivos y minimizar los falsos positivos para reducir la fatiga de alertas sin dejar amenazas sin detectar.

**Ejemplo:** Imaginá trabajás como analista SOC y tu SIEM genera alertas sobre posibles ataques.
- Maximizar los verdaderos positivos (TP): detectar correctamente la mayor cantidad posible de amenazas reales.
- Minimizar los falsos positivos (FP): evitar alertas innecesarias cuando no existe ninguna amenaza.

¿Qué es la fatiga de alertas?

Es cuando los analistas reciben tantas alertas, muchas de ellas falsas, que pueden terminar ignorándolas o tardar más en investigar las importantes.

## 2. Monitorización (Monitoring)

Consiste en observar continuamente sistemas y redes para detectar anomalías, intrusiones y amenazas.

- **Automatizada:** herramientas de software para escanear y analizar automáticamente nuestros registros de red, nuestros registros de sistema, nuestro tráfico de red y otros datos en busca de signos de actividad maliciosa.
- **Manual:** analistas revisan e investigan los datos.

Te voy a dar 3 situaciones. 1. de analisis de registro de red, 2. registro de sistema y  3. tráfico de la red, esto solo para que lo tengas en cuenta y apartir de ello puedas crear proyectos si lo deseas

1. Registros de red (Network Logs)

Son registros generados por dispositivos y herramientas de red, como firewalls, routers, switches y sistemas IDS/IPS. Muestran información sobre las comunicaciones que pasan por ellos.
Por ejemplo, un firewall puede registrar:
- IP de origen y de destino.
- Puerto de origen y de destino.
- Fecha y hora.
- Protocolo utilizado.
- Si la conexión fue permitida o bloqueada.
- Cantidad de datos transferidos, según el dispositivo.

Ejemplo de registros de firewall
10:01 — PC-01 → Servidor interno — Permitido
10:02 — PC-01 → Servidor interno — Permitido
10:03 — PC-01 → 50 IP externas diferentes — Bloqueado

¿Qué puede resultar anómalo?

Si esa computadora normalmente se comunica con pocos destinos y, de repente, intenta conectarse a decenas de IP externas, podría indicar un escaneo de red, malware o un equipo comprometido.

El sistema puede detectar la anomalía porque cambió el patrón de comunicaciones: hay más destinos, conexiones o intentos de los habituales. No significa necesariamente que sea un ataque; requiere investigación.

2. Registros del sistema (System Logs)

Son eventos que registra el propio sistema operativo o dispositivo. Por ejemplo, Windows, Linux o un servidor.
Pueden incluir:
- Inicios de sesión exitosos y fallidos.
- Creación de usuarios.
- Cambios en permisos.
- Inicio y detención de servicios.
- Errores del sistema.
- Ejecución de procesos, si está habilitado el registro correspondiente.

Ejemplo de registros de autenticación
09:00 — Usuario Santiago inicia sesión correctamente.
09:05 — Inicio de sesión fallido.
09:05 — Inicio de sesión fallido.
09:06 — Inicio de sesión exitoso con una cuenta privilegiada.

¿Qué puede resultar anómalo?

Una secuencia de intentos fallidos seguida de un acceso exitoso con una cuenta privilegiada puede indicar un posible intento de adivinar credenciales o un acceso no autorizado.

En este caso, la anomalía no se identifica necesariamente por la cantidad de registros, sino por la secuencia de eventos, el usuario involucrado, el tipo de cuenta y el contexto del acceso.

3. Tráfico de red (Network Traffic)

Acá hay una diferencia importante: los registros son información escrita sobre eventos; el tráfico es la comunicación que realmente circula entre los dispositivos.
Se puede analizar mediante herramientas como Wireshark, sensores IDS o sistemas de análisis de tráfico.
Se observan características como:
- IP y puertos de origen y destino.
- Protocolos utilizados.
- Tamaño y frecuencia de los paquetes.
- Duración y volumen de las comunicaciones.
- Contenido de los paquetes cuando es visible y está permitido inspeccionarlo.

Ejemplo de tráfico de red:
PC de empleado & Servidor externo

La PC comienza a enviar grandes cantidades de datos al exterior durante la madrugada.

¿Qué puede resultar anómalo?

Si el equipo normalmente transmite pocos datos y de repente envía varios gigabytes a un destino inusual, podría tratarse de una extracción de información (data exfiltration).

En este caso, no importa solamente cuántos paquetes hay: también importan el volumen, el destino, el horario, la duración y el comportamiento habitual de ese equipo.
Además, si la comunicación está cifrada, puede que no sea posible ver su contenido, pero sí analizar metadatos como IP, puertos, volumen y tiempos.

## 3. Conceptos y herramientas principales

- **SNMP(Protocolo Simple Gestión de Red):** protocolo para supervisar y gestionar dispositivos de red, como routers, switches, módems servidores e impresoras.

- **Trampas SNMP (SNMP Traps):** se utiliza para configurar y recopilar datos, pero simplemente son notificaciones que un dispositivo envía cuando ocurre un evento determinado.

- **SIEM:** centraliza y correlaciona registros de múltiples fuentes para detectar amenazas y generar alertas. Mediante el uso de un SIEM, vamos a ser capaces de agregar
colectivamente todos nuestros datos de registro generados a través de toda la red de la organización, incluyendo toda su infraestructura tecnológica de sus sistemas y aplicaciones de acogida todo
el camino a su red y antivirus, sistemas DLP, sistemas de detección de intrusiones en red, sistemas de prevención de intrusiones en red, cortafuegos y escáneres de vulnerabilidades.

Es capaz de tomar todos esos datos juntos y mirar a través de ellos para averiguar lo que tiene y lo que tenemos que estar alertando sobre la base de lo que estamos viendo

Estos SIEM también van a utilizar dos tipos diferentes de monitorización, uno basado en agentes y otro sin agentes, y hablaremos de ambos.

- **Monitorización basada en agentes:** instala un agente en el dispositivo supervisado.

- **Monitorización sin agentes:** recopila información mediante mecanismos remotos o protocolos compatibles, sin instalar un agente dedicado.

- **SCAP (Protocolo de Automatización de Contenidos de Seguridad):** conjunto de estándares para automatizar la gestión de vulnerabilidades y la evaluación del cumplimiento de políticas de seguridad.

- **Flujos de tráfico de red (Network Flows):** resumen de comunicaciones identificadas mediante IP de origen y destino, puertos y protocolo. Ayudan a detectar anomalías y analizar el uso de la red. Es decir
permite analizar quién se comunica con quién, mediante qué puertos y protocolos.

Ejemplo: una PC se comunica con un servidor por TCP, puerto 443. Si comienza a enviar grandes cantidades de datos a una IP desconocida, el análisis del flujo puede ayudar a detectar una anomalía.

- **SPOG (Single Pane of Glass/Cristal único):** interfaz única que consolida información de diferentes herramientas y sistemas en una sola pantalla.

## 4. Actividades de monitorización

- Agregación de registros (logs).
- Generación y gestión de alertas.
- Escaneo y análisis.
- Elaboración de informes.
- Archivado de datos.
- Investigación y respuesta a alertas.
- Remediación y validación.

**Objetivo final:** detectar incidentes a tiempo, responder eficazmente y mantener la seguridad y disponibilidad de los sistemas.

# Monitorización de recursos

La monitorización de recursos permite supervisar sistemas, aplicaciones e infraestructura para garantizar su rendimiento, seguridad y disponibilidad.

## 1. Monitorización de sistemas (System Monitoring)

Consiste en controlar los recursos de un equipo:
- CPU: utilización del procesador.
- Memoria RAM: consumo de memoria.
- Disco: uso del almacenamiento.
- Red: tráfico y rendimiento de las comunicaciones.

**Línea de base (Baseline):** conjunto de métricas que representan el funcionamiento normal de un sistema, se establece un punto de referencia para comparar en determinada situación actual y se compara con la historica, para ver la actualidad del sistema.
Básicamente, una línea de base sirve como punto de referencia o estándar con el que medir el rendimiento de nuestro sistema.

Las desviaciones pueden indicar problemas de rendimiento, fallos o posibles amenazas.

Ejemplo: si un servidor normalmente utiliza el 30 % de CPU y de repente alcanza el 95 % de forma constante, se debe investigar la causa.

Herramienta de ejemplo: Monitor de rendimiento de Windows.

## 2. Monitorización de aplicaciones (Application Monitoring)

Consiste en supervisar **el rendimiento y la disponibilidad** de las aplicaciones.

Se analizan:
- Tiempos de respuesta.
- Tasas de error.
- Cuellos de botella.
- Disponibilidad y experiencia del usuario.

Ejemplo: una aplicación web responde lentamente debido a un error en el código o a la falta de recursos del servidor.

Herramientas: New Relic y AppDynamics.

## 3. Monitorización de infraestructura (Infrastructure Monitoring)

Consiste en supervisar el estado y rendimiento de los componentes físicos y virtuales de una organización:
- Servidores y redes.
- Máquinas virtuales y contenedores.
- Servicios en la nube.
- Dispositivos de red y hardware.

Se analiza el tráfico, el ancho de banda y el estado de los dispositivos.

Ejemplo: un switch está constantemente sobrecargado, por lo que se debe investigar si necesita mayor capacidad o una corrección de su configuración.

Herramientas: SolarWinds y PRTG Network Monitor.

---

## Objetivos de la monitorización

- Detectar problemas antes de que sean graves.
- Optimizar el rendimiento.
- Identificar anomalías.
- Planificar futuras necesidades de recursos.
- Mejorar la disponibilidad y la experiencia del usuario.

## Resúmen breve

Así que recuerde, la supervisión de sus sistemas, aplicaciones e infraestructura es un aspecto crítico de las operaciones tecnológicas de su organización. La supervisión también puede ayudar a identificar posibles
problemas antes de que se conviertan en problemas importantes. La supervisión nos ayudará a optimizar el rendimiento y a planificar nuestras futuras necesidades de recursos.

La monitorización del sistema implica el seguimiento de los recursos de nuestro sistema, como la utilización de la CPU, el consumo de memoria, la utilización del disco y el rendimiento de la red.

La supervisión de aplicaciones se va a centrar en gestionar y supervisar el rendimiento y la disponibilidad de nuestras aplicaciones de software. Y la supervisión de infraestructuras consiste
en observar el rendimiento y la disponibilidad de la infraestructura física o virtual de una organización.

Utilizando las herramientas y estrategias de supervisión adecuadas, nuestras organizaciones pueden supervisar eficazmente sus recursos, lo que a su vez va a redundar en una mejora
del rendimiento, la fiabilidad y la satisfacción de los usuarios.
