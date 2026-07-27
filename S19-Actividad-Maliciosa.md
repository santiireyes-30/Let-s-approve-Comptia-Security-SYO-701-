# Actividad Maliciosa

En esta sección se estudian las **actividades maliciosas** y los principales **ciberataques** que afectan a personas, empresas y gobiernos. Debido a que las amenazas evolucionan constantemente y son cada vez más sofisticadas, comprender cómo funcionan es fundamental para prevenirlas y mitigarlas.

El objetivo es **analizar indicadores de actividad maliciosa (Indicators of Malicious Activity)**.

### Temas que se estudiarán

- **Ataques de Denegación de Servicio (DoS y DDoS):**
  - DoS.
  - DDoS.
  - DDoS por amplificación.
  - DDoS por reflexión.
  - Métodos de prevención y mitigación.

- **Ataques contra DNS:**
  - Envenenamiento de caché (DNS Cache Poisoning).
  - Amplificación DNS.
  - DNS Tunneling.
  - Secuestro de dominios (Domain Hijacking).
  - Transferencia de zona DNS (Zone Transfer Attacks).

- **Directory Traversal (Path Traversal):**
  - Explotación de una validación insuficiente de rutas o nombres de archivos para acceder a directorios restringidos.

- **Escalada de privilegios:**
  - Obtención de permisos superiores mediante la explotación de vulnerabilidades.

- **Ataques de repetición (Replay Attacks):**
  - Intercepción y retransmisión de comunicaciones válidas para realizar acciones fraudulentas.

- **Secuestro de sesión (Session Hijacking), Secuestro lateral de sesión/Secuestro de Cookies o Secuestro de Clave de sesión):**
  - Robo de sesiones activas para obtener acceso no autorizado.

- **Inyección de código malicioso:**
  - Inserción de código dañino en una aplicación o sistema para modificar su comportamiento.

- **Indicadores de Compromiso (IoCs):**
  - Bloqueos de cuentas.
  - Sesiones concurrentes inusuales.
  - Contenido bloqueado.
  - Viajes imposibles.
  - Consumo anormal de recursos.
  - Recursos inaccesibles.
  - Inicios de sesión fuera del horario habitual.
  - Mensajes indicando que el sistema fue comprometido.
  - Archivos de registro (logs) faltantes.

En la sección reforzaremos los conceptos y comprobar la comprensión de los distintos tipos de actividad maliciosa, sus mecanismos de ataque y los principales indicadores de compromiso.

# Ataques de Denegación de Servicio (DoS y DDoS)

Un **ataque de Denegación de Servicio (DoS)** es una categoría de ataques cuyo objetivo es **hacer que un servidor, computadora o dispositivo de red deje de estar disponible** para los usuarios legítimos, pero
también puede extenderse a dispositivos de red como conmutadores y enrutadores. Generalmente, esto se logra consumiendo todos los recursos del sistema.

## Tipos de ataques DoS

### • Ataque por inundación (Flood Attack)

Consiste en enviar una gran cantidad de solicitudes a un servidor hasta que no pueda responder.

#### • Ping Flood (ICMP Flood)

Ahora, un ping es técnicamente un paquete de solicitud de eco ICMP pero les gusta llamarlo ping en el exámen.

- Envía una gran cantidad de paquetes **ICMP Echo Request (ping)**, ping tambien es un comando y ICMP sería su protocolo
- Puede mitigarse bloqueando o limitando las respuestas/peticiones ICMP mediante el firewall.
- El resultado de la mitigación es que el atacante simplemente recibe un mensaje de tiempo de espera de la solicitud y el servidor permanece en línea y se detiene la denegación de servicio.

#### • SYN Flood

- El atacante envía múltiples paquetes **SYN** para iniciar conexiones TCP(múltiples sesiones TCP), pero nunca completa el **Three-Way Handshake**(apretón de manos a tres bandas).

Vamos a ver con ejemplo mas claro para que tengamos una idea de como funciona su conexión

Qué significa esto del: Three-Way Handshake (apretón de manos a tres bandas)

Es el proceso que usa TCP para crear una conexión.

Funciona así:

#### Paso 1 — SYN

El cliente dice:

  - "Hola servidor, quiero conectarme."

Cliente -------- SYN --------> Servidor

#### Paso 2 — SYN-ACK

El servidor responde:

  - "Perfecto, yo también estoy listo."

Cliente <----- SYN-ACK ------- Servidor

#### Paso 3 — ACK

El cliente confirma:

  - "Genial, ahora sí podemos comunicarnos."

Cliente -------- ACK --------> Servidor

A partir de ese momento la conexión queda establecida.

#### ¿Qué hace el atacante en un SYN Flood?

Hace solamente esto:

Cliente -------- SYN --------> Servidor

Cliente <----- SYN-ACK ------- Servidor

- Nunca envía el ACK (El ACK es simplemente el tercer mensaje que debería enviar el cliente para terminar de crear la conexión).

Entonces el servidor piensa:

"Bueno... voy a esperar un poco más."

Y reserva memoria para esa conexión.

El atacante vuelve a hacer lo mismo miles de veces:

SYN
SYN
SYN
SYN
SYN
SYN
SYN
SYN
...

El servidor sigue reservando memoria para cada conexión pendiente hasta que se queda sin recursos y deja de atender a usuarios legítimos.


- El servidor mantiene recursos reservados para conexiones incompletas hasta agotarlos. 

**Mitigación:**

- SYN Flood Protection en routers o firewalls.
- IPS (Intrusion Prevention System).
- Reducir el tiempo de espera (timeout) de conexiones semiabiertas. su servidor puede configurarse para que las peticiones medio abiertas se agoten después de un periodo de tiempo, digamos 10, 15 o 30 segundos, y
  esto liberará esos recursos y evitará que se produzca la denegación de servicio.
- Protectores contra inundaciones en la red (Flood Guars).

Esquema/Recorrido:

Antes de mostrar el esquema debemos tener en cuenta que el atacante no se conecta directamente al servidor (a menos que esté en la misma red, lo cual casi nunca ocurre).

El recorrido es:

Atacante
   ↓
Switch
   ↓
Router
   ↓
Internet
   ↓
Router del servidor
   ↓
Switch
   ↓
Servidor (victima)

---

### • Permanent Denial of Service (PDoS)

- Ataque que explota vulnerabilidades para **corromper o sobrescribir el firmware** de un dispositivo. Es decir que se trata de un ataque que aprovecha un fallo de seguridad para
romper de forma permanente un dispositivo de red mediante la reinicialización de su firmware. Esto puede provocar que un dispositivo no pueda reiniciarse porque su sistema operativo se sobrescribe.

También se denomina ataque permanente de denegación de servicio porque un reinicio rápido no volverá a poner en línea el sistema. En su lugar, hay que desconectar el dispositivo, hacer una recarga completa del firmware
y volver a conectarlo.

---

### • Fork Bomb (Bomba de Horquilla)

Con una bomba de bifurcación, El atacante crea un gran número de procesos para utilizar la potencia de procesamiento disponible de un ordenador. Este ataque recibe su nombre
porque un proceso se llama bifurcación, y puede bifurcarse(se múltiplica) en dos procesos y luego en cuatro procesos y así sucesivamente hasta que consuma todos los recursos.

Ahora, algunas personas piensan en esto como un gusano debido a la naturaleza auto-replicante, pero no son un gusano porque no infectan programas y no utilizan
la red para propagarse.

En cambio, las bombas de bifurcación sólo se propagan dentro de la memoria caché del procesador en un único ordenador con el que se está atacando, y provoca un ataque de denegación de
servicio y una condición de denegación de servicio, razón por la que se considera que no es un gusano.

Descripciones:

- Crea procesos que se duplican continuamente hasta consumir toda la CPU y la memoria.
- Solo afecta al equipo donde se ejecuta.
- **No es un gusano**, porque no se propaga por la red.

---

# Ataque Distribuido de Denegación de Servicio (DDoS)

Un **DDoS (Distributed Denial of Service)** funciona igual que un DoS, pero utiliza **cientos o miles de equipos comprometidos (bots o zombis)** para atacar simultáneamente a una misma víctima.

## Características

- Utiliza una **botnet**.
- Los dispositivos infectados normalmente desconocen que participan en el ataque.
- Es mucho más difícil de detener que un DoS tradicional.

---

## DNS Amplification Attack

Es un tipo especial de **DDoS**.

### Funcionamiento

1. El atacante falsifica (**IP Spoofing**) la dirección IP de la víctima.
2. Envía pequeñas consultas DNS a múltiples servidores DNS abiertos.
3. Los servidores responden con respuestas mucho más grandes.
4. Todas esas respuestas llegan a la víctima, saturando su ancho de banda.

> Una consulta DNS pequeña genera una respuesta mucho mayor (**amplificación**), aumentando enormemente el volumen del ataque.

---

# Ejemplo real

En **marzo de 2018**, GitHub sufrió uno de los mayores ataques DDoS registrados.

- Aproximadamente **1.35 Tbps** de tráfico.
- El servicio estuvo fuera de línea durante **5 minutos**.

---

# Mitigación de DoS y DDoS

## • Blackholing (Sinkholing)

- Identifica las IP atacantes.
- Redirige su tráfico hacia una interfaz nula ("agujero negro").
- Es una solución temporal porque el atacante puede cambiar de IP.

---

## • IPS (Intrusion Prevention System)

- Detecta y bloquea ataques DoS.
- Es efectivo para ataques pequeños o medianos.
- Puede no ser suficiente frente a un DDoS masivo.

---

## • Infraestructura en la nube elástica

- Escala automáticamente los recursos cuando aumenta el tráfico.
- Permite soportar grandes volúmenes de solicitudes.
- Su desventaja es el incremento del costo durante el ataque.

---

## • Servicios Anti-DDoS

Ejemplos:

- Cloudflare
- Akamai

Estos servicios ofrecen:

- Filtrado del tráfico malicioso.
- CDN (Content Delivery Network).
- Protección contra ataques de gran volumen.
- Alta disponibilidad.
- Defensa en múltiples capas del modelo OSI.

---

# Resumen para examen

- **DoS:** un único equipo intenta dejar fuera de servicio a la víctima.
- **DDoS:** cientos o miles de equipos (botnet) atacan simultáneamente a la misma víctima.
- **Flood Attack:** satura un sistema enviando enormes cantidades de tráfico.
- **Ping Flood:** inundación de paquetes ICMP.
- **SYN Flood:** conexiones TCP incompletas consumen los recursos del servidor.
- **PDoS:** corrompe el firmware y deja inutilizable un dispositivo.
- **Fork Bomb:** crea procesos infinitos hasta consumir CPU y memoria.
- **DNS Amplification:** amplifica el ataque utilizando respuestas DNS mucho mayores que las consultas.
- **Mitigaciones:** Firewall, IPS, SYN Flood Protection, Blackholing/Sinkholing, infraestructura elástica y servicios especializados como Cloudflare o Akamai.

#### Otro conceoto es:
IP Spoofing: IP falsas (utilizada para inundar el servidor), en si no es tan relevante como los conceptos de exámen visto anteriormente, pero es para tenerlo en cuenta
