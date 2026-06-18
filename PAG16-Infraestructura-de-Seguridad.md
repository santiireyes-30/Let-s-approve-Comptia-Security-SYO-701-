## Infraestructura de Seguridad

La infraestructura de seguridad es el conjunto de hardware, software, redes, datos y políticas que protegen los activos e información de una organización.

En esta sección se estudia cómo asegurar la arquitectura empresarial y mejorar las capacidades de seguridad.

Temas principales:

Puertos y protocolos: repaso de los protocolos y puertos más importantes.

Firewalls (cortafuegos):
- WAF (Web Application Firewall).
- UTM (Unified Threat Management).
- NGFW (Next-Generation Firewall).
- Diferencias entre firewalls de Capa 4 y Capa 7.
- Firewalls de hardware y software.

Configuración de firewalls:
- Reglas.
- ACL (Access Control Lists).
- Puertos y protocolos.
- Subredes de pantalla (DMZ).

IDS e IPS:
- IDS detecta amenazas.
- IPS detecta y bloquea amenazas.

Dispositivos de red:
- Balanceadores de carga.
- Proxies.
- Dispositivos de monitoreo.
- Equipos de seguridad.

Seguridad de puertos:
- Control de acceso mediante direcciones MAC.
- Protocolos 802.1X y EAP.

Protección de comunicaciones:
- VPN.
- IPSec.
- TLS.

SD-WAN: (Es una tecnología que utiliza principios de redes definidas por software para gestionar y optimizar una conexión de red de área extensa o conexión WAN.)
- Optimiza y enruta inteligentemente el tráfico WAN.
- Mejora rendimiento y seguridad para la transmición de datos.

SASE:
- Combina SD-WAN con servicios de seguridad en la nube.
- Integra firewall, VPN, Zero Trust y más.

Consideraciones de infraestructura:
- Ubicación de dispositivos.
- Zonas de seguridad.
- Subredes protegidas.
- Superficie de ataque.
- Conectividad.
- Dispositivos activos y pasivos.
- Modos de fallo (Fail Open y Fail Closed).

Selección de controles de seguridad:
- Elegir las medidas adecuadas según las necesidades de la organización.

(Lo más importante para Security+)

Firewalls → filtran tráfico.

IDS/IPS → detectan y/o bloquean ataques.

VPN, IPSec y TLS → protegen las comunicaciones.

802.1X → controla quién puede conectarse a la red.

SD-WAN y SASE → tecnologías modernas para redes empresariales.

DMZ (subred de pantalla) → separa servicios públicos de la red interna.

Fail Open vs Fail Closed:

- Fail Open: si falla el dispositivo, deja pasar el tráfico.

- Fail Closed: si falla el dispositivo, bloquea el tráfico.

## Puertos y Protocolos 
Un puerto es un punto lógico de comunicación en un equipo o servidor.
Los puertos de entrada (inbound) reciben conexiones.
Los puertos de salida (outbound) son abiertos temporalmente por el cliente para iniciar conexiones.

Los puertos van del 0 al 65535 y se dividen en:
0-1023: Puertos bien conocidos (Well-Known Ports).
1024-49151: Puertos registrados. 
"Este rango se conoce como el rango de puertos registrados porque todos ellos tienen que ser utilizados por los proveedores para sus propios protocolos
propietarios, y cada proveedor va a registrar el número que desea utilizar con IANA(Autoridad de Números Asignados de Internet) antes de poder utilizarlos."
49152-65535: Puertos dinámicos o efímeros. 
"Estos puertos pueden ser utilizados por cualquier aplicación en cualquier momento sin necesidad de registrarse previamente en la IANA.
Ahora este rango usualmente va a ser usado por tu cliente cuando escoja su propio puerto aleatorio de números altos para su aplicación.
Cada vez que quiera tener una conexión de salida temporal, este es el rango que vamos a utilizar.

Ejemplo simple

Cuando tu navegador entra a una web:

Tu PC abre un puerto temporal (por ejemplo 52363).
Se conecta al servidor web por el puerto 443 (HTTPS).
El servidor responde a tu puerto temporal.
Cuando termina la sesión, tu PC cierra ese puerto.

Ahora, una vez abierto cada puerto, puedes tener comunicaciones hacia o desde tu dispositivo a través de ese puerto usando lo que se conoce como un protocolo.

Un Protocolo es un conjunto definido de reglas y convenciones que rige la comunicación y el intercambio de datos entre dispositivos o sistemas que especifica el formato y la secuencia
de los mensajes que se van a utilizar para esas comunicaciones.

Repasamos estos puertos bien conocidos o registrados, y usted necesita tomar algún tiempo para memorizar cuatro cosas para cada puerto dado.

Primero, quiero que memoricemos el número de puerto.

En segundo lugar, quiero que memoricemos el protocolo que utiliza ese puerto por defecto.

En tercer lugar, quiero que sepas si el protocolo admite conexiones TCP o UDP.

Y cuarto, quiero que sepas una descripción básica de para qué se va a utilizar ese puerto o protocolo.

A continuación, daremos a conocer los puertos más comúnes:

Puerto 21 – FTP: Transferencia de archivos. (TCP)

Puerto 22 – 3 cosas diferentes: SSH / SFTP / SCP: Administración remota segura y transferencia segura de archivos. (TCP)

Puerto 23 – Telnet: Administración remota insegura. (TCP)

Puerto 25 – SMTP: Envío de correos electrónicos. (TCP)

Puerto 53 – DNS: Resolución de nombres de dominio a direcciones IP. (TCP & UDP)

Puerto 69 – TFTP: Transferencia simple de archivos. (UDP)

Puerto 80 – HTTP: Navegación web sin cifrado. (TCP)

Puerto 88 – Kerberos: Autenticación en entornos Windows/Active Directory. Kerberos es un protocolo de autenticación de red. (UDP)

Puerto 110 – POP3: Recepción/Recuperación de correos electrónicos. (TCP)

Puerto 119 – NNTP o el Protocolo de Transferencia de Noticias en Red, y es usado para acceder a grupos de noticias. (TCP)

Puerto 135 – RPC o Remote Procedure Call facilities. Esto va a facilitar su comunicación entre diferentes procesos del sistema. verás que se utiliza como parte del sistema de compartición de archivos de Windows. (TCP & UDP)

Puerto 137, 138 y 139 – Se utilizan para NetBIOS. NetBIOS es un conjunto de protocolos de red. NetBIOS se utiliza dentro de un entorno de dominio Windows para poder compartir cosas como nombres de red internos, así como para compartir archivos e impresoras en un entorno Windows local. (TCP & UDP)

Puerto 143 – IMAP: Acceso y gestión de correos en el servidor. (TCP)

Puerto 161 – SNMP: Administración y monitoreo de dispositivos de red. (UDP)

Puerto 162 – SNMP Trap: Recepción de alertas SNMP. (UDP)

Puerto 389 – LDAP: Servicios de directorio y autenticación. (TCP)

Puerto 443 – HTTPS: Navegación web cifrada y segura. (TCP)

Puerto 445 – SMB: Compartición de archivos e impresoras en Windows. (TCP)

Puerto 465/567 – Se utiliza para SMTPS. También se conoce como SMTP Secure y nos proporciona comunicaciones SMTP seguras para enviar nuestros correos electrónicos a través del puerto 465 o 587 utilizando SSL o TLS. (TCP)

Puerto 514 – Syslog: Envío de registros (logs). (UDP)

Puerto 636 – LDAPS: LDAP cifrado mediante SSL/TLS. (TCP)

Puerto 993 – IMAPS: Recuperación segura de correo electrónico. (TCP)

Puerto 995 – POP3S: Oficina de Correos y Recuperación. (TCP)

Puerto 1433 – Microsoft SQL Server: Comunicación con bases de datos SQL Server. (TCP)

Puerto 1645/1646 – Se utilizan para RADIUS. RADIUS es un protocolo de autenticación, autorización y contabilidad remotas. (TCP)

Puerto 1812/1813 – RADIUS: Autenticación, autorización y accounting (AAA). (UDP)

Puerto 3389 – RDP: Escritorio remoto de Windows. (TCP)

Puerto 6514 – Syslog TLS: Envío seguro y cifrado de logs. (TCP)

## Firewalls (Cortafuegos)
¿Qué es un firewall?

Un firewall es un dispositivo o software de seguridad que controla el tráfico de red entrante y saliente según reglas predefinidas para bloquear accesos no autorizados y amenazas.

Subred Apantallada (Screened Subnet)

Consiste en colocar un firewall entre una red externa (no confiable) y una red interna (confiable).

Objetivo:

Filtrar el tráfico.
Permitir solo conexiones autorizadas.
Bloquear amenazas e intentos de acceso no autorizados.

### Tipos de Firewalls

#### Firewall de Filtrado de Paquetes (Packet Filtering)

Son más eficientes en términos de maximizar su rendimiento
Inspecciona únicamente la cabecera del paquete(Evalúa IP de origen → quién envía el paquete, IP de destino → a dónde va, Puerto de origen, Puerto de destino y Protocolo (TCP, UDP, etc.))
Muy rápido y eficiente.
Funciona en la Capa 4 (Transporte).

Desventajas:

No detecta spoofing IP.
No detecta ataques complejos.
Seguridad limitada.
estos cortafuegos simples no pueden evitar la suplantación de IP, los ataques de fragmentación de paquetes o los ataques contra el propio handshake TCP

Recuerda: Más rápido, menos seguro.

#### Firewall Stateful (Con Estado)

Se va a utilizar para rastrear el estado de todas las conexiones y peticiones que entran y salen de la red.

Además de revisar cabeceras:

Mantiene registro de conexiones activas.
Sabe si una comunicación fue iniciada desde dentro de la red.
Permite respuestas legítimas automáticamente.

Ejemplo:
Si visitas una web, recuerda la solicitud y permite la respuesta.

Ventaja: Más seguro que el filtrado simple.

#### Firewall Proxy

Este firewall se colocará entre una conexión interna o externa en una red, y va a hacer conexiones en nombre de sus otros puntos finales.

Actúa como intermediario entre cliente y servidor. Existen 2 tipos de Firewall Proxy

Proxy de Nivel de Circuito
- Opera en la Capa 5 (Sesión).
- Ejemplo: SOCKS Proxy.

Proxy de Aplicación
- Opera en la Capa 7 (Aplicación).
- Realiza inspección profunda de paquetes (DPI).
- Analiza tráfico HTTP, FTP, etc.

Ventaja: Seguridad muy alta.

Desventaja: Mayor latencia y menor rendimiento.

La mayoría de los proxies de nivel de aplicación van a estar mejor posicionados dentro de su red cuando estén ubicados lo más cerca posible del
servidor de aplicación que está tratando de proteger.

#### Kernel Proxy Firewall (5ª Generación)

Se colocará entre dos sistemas y creará conexiones en su nombre, al igual que los otros

tiene un impacto mínimo en el rendimiento de nuestra red
Inspección profunda completa.
Actúa como intermediario entre sistemas.

Ventaja: Alta seguridad y eficiencia.

### Firewalls Modernos (3)

#### NGFW (Next Generation Firewall)

Es un dispositivo de seguridad avanzado que combina las funciones tradicionales de un cortafuegos con otras adicionales como la detección de intrusiones, el conocimiento de las aplicaciones y la protección contra amenazas avanzadas.
va a intentar superar las deficiencias de un cortafuegos con seguimiento de estado tradicional creando cortafuegos que sean conscientes de las aplicaciones.

Combina:

Firewall tradicional.
Inspección profunda de paquetes (estos cortafuegos pueden distinguir entre los distintos tipos de tráfico que las aplicaciones específicas que están enviando
dentro o fuera de una red determinada).
Detección de intrusiones (IPS), basado en firmas cuando se instalan como dispositivos en línea dentro de la configuración de la red.
Reconocimiento de aplicaciones.

Ventajas:

Apenas afectan al rendimiento de su red.
Muy seguro.
Visibilidad completa del tráfico.
Control granular sobre el tráfico (mediante la creación de firmas personalizadas dentro de este cortafuegos).

Desventajas:

Más complejo.
Puede generar dependencia del fabricante.

#### UTM (Unified Threat Management)

un cortafuegos de gestión unificada de amenazas es una solución de seguridad completa que integra múltiples funciones de seguridad, como cortafuegos, antivirus, detección de intrusiones y filtrado de contenidos, en una única plataforma unificada.

En este Firewall se piensa como todo en 1, el tema es si cae este firewall, cae todo lo que "Integra" múltiples funciones en un solo equipo:

- Firewall.
- Antivirus.
- Antispam pasarela.
- VPN.
- IPS.
- Filtrado web.
- Balanceo de carga.
- Prevención de pérdida de datos (DLP).

Ventajas
- Menor costo.
- Menos equipos que administrar.
- Configuración sencilla.

Desventajas
- Punto único de fallo.
- Menor rendimiento que soluciones especializadas.

Recuerda:
Si falla el UTM, puedes perder toda tu protección de seguridad.

#### WAF (Web Application Firewall)

Protege aplicaciones web.

se centra en Analizar los tráfico:

- HTTP
- HTTPS

Su Web Application Firewall utilizará conjuntos de reglas específicas para prevenir ataques comunes contra aplicaciones web,
Incluyendo ataques como:

- SQL Injection.
- Cross-Site Scripting (XSS).

Instalaciónes (2 Tipos), pueden instalarse como dispositivos independientes o como un tipo de complemento de software en su servidor web.

En línea (Inline)
el dispositivo se colocará entre el cortafuegos de la red y los propios servidores web. Al utilizar esta colocación en línea, estos
dispositivos pueden prevenir ataques en vivo, pero también van a ralentizar su tráfico web y, a veces, bloquearán el tráfico legítimo por error.

- Puede bloquear ataques en tiempo real 
- Añade latencia.

Fuera de banda (Out-of-Band)
- Solo monitorea.
- Genera alertas.
- No bloquea tráfico.


### A tener en cuenta

Un cortafuegos de capa 4 va a operar en la capa de transporte y tomar decisiones de filtrado basadas en la información sobre números de puerto y datos de protocolo sin inspeccionar el contenido de sus paquetes de datos individuales.

Por otro lado, un cortafuegos de capa 7, también conocido como proxy de aplicaciones o cortafuegos de aplicaciones, funciona en la capa de aplicaciones y puede inspeccionar, filtrar y controlar el tráfico en función del contenido y las características de la carga útil de los datos.

## Configuración de Firewalls y ACL

¿Qué es una ACL (Access Control List)?

Una lista de control de acceso, o ACL, es el conjunto de reglas que se colocará en el cortafuegos, enrutador u otros dispositivos de infraestructura de red que permite o rechaza el tráfico a través de una interfaz en particular. Es decir, es un conjunto de reglas que utiliza un firewall o router para permitir o bloquear tráfico entrante o saliente de nuestra red.

Las reglas suelen basarse en:

Tipo de tráfico (TCP, UDP, etc.)
IP origen
IP destino
Puerto
Acción (permitir o denegar)

Para configurar las listas de control de acceso en nuestros cortafuegos, vamos a utilizar una interfaz basada en web o una interfaz
de línea de comandos basada en texto.

Ejemplo:

Permitir TCP desde 192.168.0.0 hacia cualquier destino por el puerto 22 (SSH)

Regla importante: Orden de las ACL

Las reglas se evalúan de arriba hacia abajo.

Regla 1
Regla 2
Regla 3

Cuando una coincide:

- Se aplica la acción.
- Se dejan de revisar las demás.

El tráfico se comparará primero con la primera regla y, si coincide con la condición, se aplicará la acción y dejará de ejecutar el resto de la ACL.

Por eso:

Reglas específicas arriba.
Reglas generales abajo.
Denegación implícita (Implicit Deny), si no coiciden los paquetes con las regla, bloquea.

Muchos firewalls funcionan así:

Si no está permitido → está bloqueado

Por eso, es buena práctica agregar:

deny all al final de la lista ACL.

Registro (Logging)

Cada vez que una regla:

- Permite tráfico
- Bloquea tráfico

Debe quedar registrado en logs para auditoría y análisis.

"Las reglas de las listas de control de acceso van a estar compuestas por algunas piezas clave de información, incluyendo el tipo de tráfico, la fuente
del tráfico, el destino del tráfico y la acción que se debe tomar contra ese tráfico."

### Firewall de Hardware vs Software

#### Firewall de Hardware
Está en el router o dispositivo dedicado.
Protege toda la red.

Ejemplo:

Internet
   ↓
Firewall
   ↓
PCs de la empresa

Firewall de Software
Se instala en cada equipo.
Ejemplo:
Windows Defender Firewall
Firewall de macOS

Protege solo esa máquina.

Conceptos clave para examen

- ACL = lista de reglas de permitir/denegar.

- Las reglas se leen de arriba hacia abajo.

- La primera coincidencia gana.

- Se recomienda terminar con deny all.

- Firewall de hardware protege toda la red.

- Firewall de software protege un único equipo.

Así que recuerde, cuando se trata de la configuración del cortafuegos, puede utilizar un cortafuegos basado en hardware que protegerá todas las estaciones de trabajo conectadas a una subred de cortafuegos, o puede utilizar un cortafuegos individual basado en software en la propia estación de trabajo dentro de Windows, Mac OS o en Linux. En cualquier caso, las protecciones que proporcionará tu cortafuegos se basarán en la lista de control de acceso y las reglas que configures al configurar tus cortafuegos.

## IDS Y IPS

Los IDS (Intrusion Detection Systems): Detecta y alerta de actividades sospechosas

IPS (Intrusion Prevention Systems): sirven para detectar actividades sospechosas o ataques, no solo alerta y detecta sino que a diferencia de IDS este acciona bloqueando la actividad sospechosa

Tipos de IDS/IPS
1. Basados en red (NIDS / NIPS)

Monitorean el tráfico de toda la red.

Buscan:

Escaneos de puertos
IPs sospechosas
Tráfico malicioso
Ataques de red

Ubicación:

NIDS → conectado a un puerto espejo (SPAN). debe conectarse a través de un puerto duplicado del conmutador
de red troncal. De este modo, puede analizar todo el tráfico de forma pasiva.
NIPS → en línea, detrás del firewall.

2. Basados en host (HIDS / HIPS)

Se instalan en una computadora o servidor.

Monitorean:

Procesos
Archivos
Cambios en el sistema
Conexiones de red del equipo

Ejemplo:
Un programa intenta modificar archivos críticos de Windows.

HIDS → te avisa.
HIPS → lo bloquea.

3. Inalámbricos (WIDS / WIPS)

Protegen redes Wi-Fi.

Detectan:

- Ataques de desautenticación
- Ataques de disociación
- Flooding de autenticación
- Dispositivos sospechosos

Ejemplo:
Alguien intenta expulsar usuarios del Wi-Fi.

WIDS → alerta.
WIPS → bloquea al atacante.

### Métodos de detección

#### Basado en firmas

Compara el tráfico con una base de datos de ataques conocidos.

Ventaja:

- Muy preciso para amenazas conocidas.

Desventaja:

- No detecta ataques nuevos (Zero-Day).

Piensa en un antivirus que busca virus conocidos.

#### Basado en anomalías

Aprende qué es "normal" y alerta cuando algo se sale de ese comportamiento.

Ventaja:

Puede detectar ataques nuevos.

Desventaja:

Más falsos positivos.

existen cinco tipos de sistemas de detección basados en anomalías. Los hay estadísticos, de protocolo, de tráfico, de reglas o heurísticos y basados en aplicaciones.

Cada uno de estos tipos busca identificar el tráfico que parece estar fuera de un patrón normal.

Ejemplo de tráfico:

Si normalmente hay 100 conexiones por minuto y de repente aparecen 10.000, genera una alerta.

Ahora bien, los IDS basados en firmas se dividen a su vez en dos tipos. Tenemos pattern-matching(coincidencia de patrones) y stateful-matching(coincidencia de estados).

La concordancia de patrones se va a centrar en un patrón específico de pasos que se están reconociendo durante un ataque.

Stateful-matching se va a centrar en una línea de base conocida de un sistema y en informar de cualquier cambio en ese estado.

"La concordancia de patrones es más común en los IDS basados en red y en los IDS inalámbricos, mientras que la concordancia
de estados se utiliza más comúnmente en los IDS basados en host."

Brevemente: 

- IDS = Detecta y alerta.

- IPS = Detecta, alerta y bloquea.

- NIDS/NIPS = Protegen la red.

- HIDS/HIPS = Protegen un equipo o servidor.

- WIDS/WIPS = Protegen la red Wi-Fi.

## Dispositivos de Red

un dispositivo de red es un aparato de hardware dedicado con software preinstalado que está diseñado para proporcionar servicios de red específicos como seguridad, almacenamiento de datos o funciones de servidor dentro de una infraestructura de red.

vamos a centrarnos en 4 tipos diferentes: balanceadores de carga, servidores proxy, sensores y servidores de salto.

1. Balanceador de Carga (Load Balancer)

¿Qué hace?
Distribuye las solicitudes entre varios servidores para que ninguno se sobrecargue. Esto garantiza que podamos mantener la redundancia
y la fiabilidad, mitigando los riesgos asociados a depender de un único servidor

Ejemplo:
Un sitio web tiene 3 servidores. El balanceador reparte los usuarios entre los 3.

Beneficios:

Mayor disponibilidad.
Mejor rendimiento.
Si un servidor falla, envía el tráfico a los demás.

Palabra clave:
- Distribuye tráfico entre múltiples servidores.

Controlador de entrega de aplicaciones(ADC) es una versión más avanzada de un Balanceador de Carga, ADC nos proporcionará una serie de funcionalidades
más allá de la simple distribución de carga, ya que incluye funciones como la terminación SSL, la compresión HTTP y el almacenamiento en caché de contenidos.

- Mejora la eficacia y el rendimiento de nuestras redes de alta disponibilidad.

- garantiza la resistencia y fiabilidad de nuestros sitios web de alto tráfico, sistemas de aplicaciones críticas y amplias plataformas digitales en
diversas industrias y sectores.

2. Servidor Proxy

¿Qué hace?

Actúa como intermediario entre cliente y servidor para proporcionar diversas funciones como el almacenamiento de contenidos en caché, el filtrado de peticiones
y la gestión de inicios de sesión para mejorar la eficiencia y controlar el acceso a nuestros recursos dentro de una red determinada.

Funciones:

Cachea contenido.
Filtra solicitudes.
Controla acceso.
Oculta los servidores reales.

Ejemplo:
Un empleado entra a una web. Primero pasa por el proxy y luego sale a Internet.

Beneficios:

Más seguridad.
Menor consumo de ancho de banda.
Aplicación de políticas de empresa.

"Los servidores proxy contribuyen significativamente a la estabilidad y fiabilidad de nuestros sistemas de red al proporcionar otra capa de defensa contra amenazas externas, incluidas las de denegación de servicio distribuido o ataques DDoS, enmascarando los verdaderos puntos finales que se encuentran dentro de esa red."

Estos servidores proxy pueden aplicar protocolos de autenticación de usuarios para ayudar a dirigir el tráfico de forma más segura.

Algunos servidores proxy avanzados también pueden gestionar el cifrado de datos proporcionando túneles seguros para el transporte
de cualquier información sensible.

3. Sensor de red

¿Qué hace?

Monitorea el tráfico y detecta actividades sospechosas. Es decir, están diseñados para supervisar, detectar y analizar el tráfico y el flujo de datos a través de la red con el fin de identificar cualquier actividad inusual, posibles brechas de seguridad, problemas de rendimiento u otros tipos de ineficiencias operativas.

Se usa en:

IDS
IPS
Sistemas de monitoreo

Ejemplo:

Detecta que una IP está enviando miles de solicitudes por segundo y genera una alerta.

Beneficios:

Detecta ataques.
Ayuda a monitorear rendimiento.
Detecta anomalías de rendimiento, como picos de tráfico inesperados que podrían provocar una degradación del servicio


4. Jump Server/ Jump Box (Servidor de salto/Caja de salto)

¿Qué hace?

Es un servidor seguro que los administradores utilizan para acceder a sistemas críticos. Es decir, es una pasarela dedicada que utilizan los administradores de sistemas para acceder de forma segura a dispositivos situados en diferentes zonas de seguridad dentro de su red

es una parte crítica de una arquitectura de red de alta seguridad y alta disponibilidad porque actúa como una estación intermediaria para acceder a aquellos servidores y dispositivos de red dentro de su red de confianza.

Estos servidores de salto ofrecen una sólida capa de protección para los sistemas que no pueden permitirse ningún tiempo de inactividad o violación de datos asociada a ellos.

Ejemplo:

En lugar de conectarte directamente a un servidor de producción:

Tu PC → Jump Server → Servidor crítico

Beneficios:

Reduce superficie de ataque.
Centraliza accesos.
Facilita auditorías y registros.

En caso de un ciberataque, tendrán un registro detallado de cualquier acción o conexión que se haya realizado, por lo que podemos acelerar significativamente
el proceso de recuperación durante la respuesta a un incidente.

Palabra clave:
- Puerta de acceso segura para administradores.

### En Resúmen

Asi que Recuerde que los dispositivos de red son equipos de hardware dedicados con software preinstalado diseñados para proporcionar servicios de red específicos.

Los equilibradores de carga distribuyen el tráfico de red o de aplicaciones entre varios servidores para optimizar su rendimiento y evitar la sobrecarga de un único servidor.

Los servidores proxy también actuarán como intermediarios entre sus clientes y sus servidores para gestionar el flujo de datos y ofrecer mayores niveles de seguridad y control de contenidos.

Los sensores son herramientas o dispositivos que supervisan diversas condiciones físicas o de la red para proporcionar datos en tiempo real
para la optimización y seguridad del sistema.

Los servidores de salto o jump boxes son plataformas intermediarias seguras que los administradores pueden utilizar para acceder a dispositivos a través
de diferentes zonas de seguridad dentro de una red determinada.

Juntos, estos cuatro tipos de dispositivos de red nos ayudarán a garantizar la eficacia, seguridad y alto rendimiento de la infraestructura.

## Seguridad de puertos (Port Security)

Es una función de los switches que permite decidir qué dispositivos pueden conectarse a un puerto específico usando su dirección MAC de su tarjeta de interfaz de red.

Ejemplo:

Puerto 1 → solo puede conectarse la PC de recepción.

Puerto 1
↓
MAC: AA:BB:CC:11:22:33 (recepción)

El switch dice:
- "Esa MAC está autorizada."

Si conectan otra laptop, el switch la bloquea.

Un atacante desconecta la PC de Juan y conecta su laptop.

Puerto 1
↓
MAC: FF:EE:DD:44:55:66

El switch dice:
- "Esa MAC no es la que tengo autorizada." Y bloquea el acceso.

Objetivo: evitar dispositivos no autorizados en la red.

Todo esto estamos hablando fisicamente, aunque el atacante sin cable lo puede obtener el acceso cambiando el nombre de la MAC a la MAC que esta autorizada, en nuestro caso cambia de la MAC: FF:EE:DD:44:55:66 a la MAC: AA:BB:CC:11:22:33 (recepción). También tener en cuenta que nuestros conmutadores de red son dispositivos de red que van a operar en la capa 2 del modelo OSI (Enlace de Datos).

Estos dispositivos toman las decisiones de conmutación de tráfico basándose en la dirección MAC de los dispositivos emisores y receptores a través de un proceso denominado puente transparente. A diferencia de los concentradores, que son un tipo de dispositivo de red más antiguo, los conmutadores utilizan la inteligencia para evitar colisiones en la red 

Una colisión ocurre cuando dos dispositivos intentan transmitir datos al mismo tiempo por el mismo medio de comunicación, y sus datos "chocan".

Ejemplo: 

Antes, con un hub, todas las PCs compartían el mismo medio:

PC1 ─┐
PC2 ─┼─ HUB
PC3 ─┘

Si PC1 y PC2 enviaban datos al mismo tiempo:
- Colisión.

Con un switch:

PC1 ─ Puerto 1
PC2 ─ Puerto 2
PC3 ─ Puerto 3

Cada puerto tiene su propio canal, así que no chocan entre sí.

Hub → envía a todos.
Switch (conmutador) → envía solo al destinatario correcto usando la dirección MAC.

Funcionan en modo "Full Dúplex"

Significa que un dispositivo puede:

Enviar datos ➡️
Recibir datos ⬅️

al mismo tiempo.

Ejemplo:

Mientras tu navegador descarga una página web, también está enviando solicitudes al servidor.

No tiene que esperar a terminar una cosa para hacer la otra.

2. Tabla CAM

Es la memoria del switch donde guarda:

MAC → Puerto

Ejemplo:

MAC	Puerto
AA:BB:CC	Fa0/1
DD:EE:FF	Fa0/2

Gracias a esta tabla el switch sabe exactamente dónde enviar cada paquete.

- Piensa en ella como la "agenda de contactos" del switch.

3. MAC Flooding

Ataque donde un atacante envía miles de MAC falsas.

Resultado:

La tabla CAM se llena.
El switch ya no sabe dónde está cada equipo.
Empieza a comportarse como un hub.

Problema: el tráfico se envía a muchos puertos y puede ser espiado.

- Es un ataque para "confundir" al switch.

4. Sticky MAC (MAC Pegajosa)

Facilita la configuración de Port Security.

En vez de escribir manualmente la MAC permitida:

Se conecta el primer dispositivo.
El switch aprende automáticamente su MAC.
Esa MAC queda autorizada.

"Aprendizaje automático de la primera MAC".

Problema de usar solo MAC

Las MAC pueden falsificarse.

Esto se llama:

MAC Spoofing

El atacante cambia la MAC de su tarjeta de red por una MAC autorizada.

Entonces:

El switch cree que es un equipo legítimo.
Le permite entrar.

- Por eso Port Security sola no es suficiente.

802.1X (MUY IMPORTANTE)

Es un estándar que obliga a que un dispositivo se autentique antes de entrar a la red.

Piensa:

Port Security pregunta:

¿Tu MAC está permitida?

802.1X pregunta:

¿Quién eres? Demuéstralo.

Los 3 componentes de 802.1X

1. Supplicant (Solicitante)

El usuario o dispositivo que quiere entrar a la red.

Ejemplo:

Tu notebook.

2. Authenticator

El dispositivo que controla el acceso. También es el dispositivo a través del cual el solicitante intenta acceder a la red, como un switch, un punto de acceso inalámbrico o un concentrador VPN.

3. Authentication Server

Servidor que verifica las credenciales. que va a ser nuestro dispositivo centralizado que realiza la autenticación, y esto normalmente va a ser configurado como un servidor RADIUS o TACACS+.

Normalmente:

RADIUS

- Es un protocolo multiplataforma
- El más usado

TACACS+

- Más control pero más lento en las operaciones porque se basa en TCP para su protocolo de transporte, pero esto añade seguridad adicional y lleva a cabo de forma independiente la autorización de autenticación en el proceso de contabilidad mediante el uso de TACACS+.
- Principalmente Cisco

Regla de examen:

Red mixta → RADIUS
Todo Cisco → TACACS+

A la hora de diseñar la arquitectura de seguridad de la red de su empresa, debería utilizar 802. 1x como parte de sus defensas.

Utilizando 802. 1x es una de las mejores protecciones que puede añadir a su red interna para evitar que dispositivos no autorizados accedan a los dispositivos y recursos de nuestra organización.
Dado que proporciona autenticación basada en puertos, cualquier cosa que se conecte a un conmutador o a un punto de acceso inalámbrico deberá presentarse para la autenticación mediante ese 802. 1x antes de obtener acceso a toda la red.

El 802. 1x también puede utilizarse para encapsular EAP o el protocolo de autenticación extensible.

EAP (Extensible Authentication Protocol)

No es un protocolo único en sí mismo, sino que es un marco en una serie de protocolos que nos permite las numerosas formas
diferentes de llevar a cabo la autenticación, incluyendo cosas como el uso de contraseñas simples, el uso de certificados digitales y el uso de una infraestructura de clave pública.

Existen muchas variantes de EAP, como EAP-MD5, EAP-TLS, EAP-TTLS, EAP-FAST, PEAP y EAP-LEAP.

EAP MD5

Ventaja:

- Simple

Desventaja:

- Menos seguro

- Solo contraseñas.

EAP-TLS

Usa:

Certificado en cliente
Certificado en servidor

Ventaja:

Muy seguro (El más seguro porque usa certificados en ambos lados).

- Es el más seguro de los que viste.

Piensa:
Certificado + Certificado

EAP-TTLS

Usa:

Certificado en servidor
Contraseña en cliente

Más seguro que MD5.
Menos seguro que TLS porque no usa el certficado del cliente

- Certificado + Contraseña

EAP-FAST

Ahora bien, EAP-FAST es otra variante de EAP, y FAST significa autenticación flexible mediante túnel seguro, y utiliza una credencial de acceso
protegida en lugar de un certificado para establecer la autenticación mutua entre dos dispositivos.

Usa:

PAC (Protected Access Credential)

No necesita certificados.

- Alternativa más sencilla.

PEAP

Ahora, la variante PEAP protegida, va a soportar la autenticación mutua mediante el uso de un certificado de servidor y su base de datos de Microsoft Active Directory con el fin de autenticar una contraseña de su cliente dado.

Usa:

- Certificado en servidor
- Contraseña del usuario
- Muy común en empresas con Active Directory.

LEAP

Creado por Cisco.

Solo para entornos Cisco.

- Si ves "Cisco propietario", piensa en LEAP.

### Resúmen

Así que recuerde, la seguridad de puertos es una característica del conmutador de red que va a restringir qué dispositivos pueden conectarse a puertos específicos en función de sus direcciones MAC.

802. 1x es un estándar IEEE para el control de acceso a la red que va a autenticar los dispositivos en función de sus capacidades como se utiliza principalmente en la capa de enlace de datos, que es la capa 2 del modelo OSI.

El protocolo de autenticación extensible o EAP se considera un marco de autenticación flexible que se utiliza junto con 802. 1x para admitir varios métodos de autenticación mediante EAP-MD5, EAP-TLS, EAP-TTLS, EAP-FAST, PEAP o EAP-LEAP.

Al integrar la seguridad de puertos con 802. 1x y EAP, nuestras organizaciones pueden aumentar realmente la seguridad de su red garantizando que sólo los dispositivos autenticados y autorizados puedan acceder a nuestros recursos más críticos y sensibles.

## Protección de las comunicaciones de red (VPN, TLS e IPSec)

Protección de los datos cuando viajan por Internet mediante tres tecnologías principales:

1. VPN (Virtual Private Network)

Una VPN crea un túnel cifrado entre un usuario o una red y otra red remota para que los datos viajen seguros por Internet.

Tipos de VPN:

Sitio a sitio (Site-to-Site): conecta dos sedes u oficinas completas.
Cliente a sitio (Client-to-Site): conecta un dispositivo individual (laptop, celular) a la red corporativa.
Sin cliente (Clientless): se accede mediante un navegador web usando HTTPS.

2. VPN de túnel completo vs túnel dividido

Túnel completo (Full Tunnel):

Todo el tráfico pasa por la VPN.
Más seguro.
Menor rendimiento.

Ejemplo:

Tu PC
  |
 VPN
  |
Servidor VPN empresa
  |
  +----> Splunk
  |
  +----> Google
  |
  +----> YouTube

Si abres:

Splunk → VPN ✅
Google → VPN ✅
YouTube → VPN ✅

Todo se envía primero a la empresa.

Túnel dividido (Split Tunnel):

Solo el tráfico corporativo pasa por la VPN.
El resto va directo a Internet.
Más rápido.
Menos seguro.

Ejemplo:

Tu PC
  |
  +---- VPN ----> Red de la empresa
  |
  +------------> Google
  |
  +------------> YouTube

Si abres:

Splunk de la empresa → pasa por la VPN ✅
Microsoft Sentinel de la empresa → pasa por la VPN ✅
Google → sale directo a Internet ❌ VPN
YouTube → sale directo a Internet ❌ VPN

Ventajas
Más rápido.
Consume menos ancho de banda de la empresa.
Desventajas
La empresa tiene menos control sobre tu tráfico de Internet.

3. TLS (Transport Layer Security)

Es el protocolo que protege las conexiones HTTPS.

TLS utiliza el Protocolo de Control de Transmisión, conocido como TCP, para que podamos establecer nuestras conexiones seguras entre un cliente y un servidor. Pero esto puede ralentizar tu conexión
porque TCP tiene mucha más sobrecarga que una conexión UDP. 

Funciones:

Cifra la información.
Protege usuarios, contraseñas y datos.
Se usa diariamente al entrar en sitios web seguros.

DTLS es una versión de TLS que funciona sobre UDP y suele ser más rápida para video y streaming.

4. IPSec

Es el protocolo más utilizado para crear VPN modernas. En otras palabras es un conjunto de protocolos de red seguros que proporciona autenticación y cifrado de nuestros paquetes de datos para crear una ruta de comunicación cifrada segura entre dos ordenadores
a través de una red de protocolo de Internet.

Proporciona:

Confidencialidad: cifra los datos.
Integridad: verifica que no fueron modificados. os proporcionará la integridad que deseamos al garantizar que nuestros datos no han sido modificados en tránsito mediante la comprobación de su resumen hash justo antes de ser transmitidos
y de nuevo una vez recibidos para garantizar que coinciden.
Autenticación: verifica la identidad de los participantes. Es decir, La autenticación se realizará haciendo que cada parte verifique que es quien dice ser.
Antirrepetición: evita que un atacante reutilice paquetes capturados y impide la transmisión de paquetes duplicados

IPSec VPN se establece en 5 pasos en el proceso de establecer y utilizar un túnel VPN seguro cuando se utiliza IPSec:

Inicio de la conexión
   - Un dispositivo solicita crear el túnel VPN.
IKE Fase 1
   - Los dos extremos se autentican entre sí.
Crean un canal seguro para negociar.
   - IKE Fase 2
   - Se negocian las claves y parámetros de seguridad.
   - El túnel VPN queda completamente establecido.
Transferencia de datos
   - Los datos viajan cifrados por el túnel VPN.
Finalización
   - Se cierra el túnel y se eliminan las asociaciones de seguridad.

Modo Transporte vs Modo Túnel

Modo Transporte

- Cifra solo la carga útil del paquete.
- Mantiene la cabecera IP original.
- Se usa normalmente en VPN Cliente-Sitio.

Ejemplo:
Tu notebook desde tu casa se conecta a la VPN de la empresa.

Mantiene la cabecera IP original.
Solo cifra el contenido.
Agrega menos información extra.
Los paquetes son más pequeños.

Ventaja:

Menor consumo de ancho de banda.
Menos riesgo de fragmentación.

Uso típico:

VPN de usuario remoto → empresa.

Modo Túnel

- Encapsula el paquete completo dentro de otro paquete.
- Añade una nueva cabecera IP.
- Se usa normalmente en VPN Sitio-Sitio.
- Es más seguro, pero aumenta el tamaño de los paquetes.

Sucursal de California ↔ Oficina principal de Washington.

Se encapsula TODO el paquete original.
Se agrega una nueva cabecera IP.
El paquete crece de tamaño.

Piensa en esto:

Carta normal:

Carta + sobre = paquete original.

Modo túnel:

Carta + sobre.
Ese sobre se mete dentro de otro sobre.

Por eso se llama túnel.

¿Por qué aumenta el tamaño?

Porque se agrega:

Nueva cabecera IP.
Información IPSec.
Datos de cifrado.

Entonces:

Paquete original
+
Cabecera IPSec
+
Nueva cabecera IP
=
Paquete más grande

Si estás utilizando una VPN cliente-sitio, te recomiendo encarecidamente que utilices un modo de transporte como método IPSec, ya que no añade ningún relleno adicional al paquete y no aumenta su tamaño.
Sin embargo, si controlas toda tu red, puedes volver a utilizar tramas jumbo y llegar a un tamaño de hasta 9.000 bytes si quieres, pero esto sólo deberías hacerlo en tus propias redes de área local porque los paquetes
de 9.000 bytes tendrán problemas para atravesar toda Internet.

¿Qué es la MTU?

MTU (Maximum Transmission Unit) = tamaño máximo de paquete que una red puede transportar.

Normalmente:

MTU = 1500 bytes

Si el paquete supera ese tamaño:

Paquete → se fragmenta

y eso puede generar problemas o reducir el rendimiento de la VPN.

6. AH y ESP

AH (Authentication Header): se va a utilizar para proporcionar integridad de datos sin conexión y autenticación de origen de datos para datagramas IP, y proporciona protección contra ataques de repetición.

- No cifra los datos.

En su lugar, la cabecera de autenticación contiene un hash criptográfico de los datos, y esto simplemente actuará como información de identificación para proporcionar la integridad entre el remitente y el receptor 
de cada paquete que se está transmitiendo.

ESP (Encapsulating Security Payload): se va a utilizar para proporcionar autenticación, integridad, protección contra repeticiones y confidencialidad de tus datos.

- Proporciona cifrado.
- Es el mecanismo más utilizado en IPSec.

Usando ESP dentro de IPSec, puedes reescribir la carga útil del paquete dentro de un formato encriptado. Cuando usamos ESP, sólo protegemos la confidencialidad de la carga útil contenida en el paquete, no las cabeceras.
Así que si estás utilizando el modo de transporte, como en una VPN cliente-sitio, puedes utilizar cabeceras de autenticación para proporcionar integridad a tu cabecera TCP, y luego puedes añadir ESP o Encapsulating
Security Payload para poder cifrar la cabecera TCP y los datos dentro de la carga útil.

Esto no cifra el encabezado de extremo a extremo, por lo que las personas ajenas a tu organización podrán ver de dónde proceden los datos y a dónde van, pero no podrán leer los datos que contienen.
Ahora bien, si estás utilizando el modo túnel, como en una VPN de sitio a sitio, puedes utilizar tanto la cabecera de autenticación como la carga útil de seguridad encapsulada para proporcionar
integridad y cifrado de esa carga útil, incluida la cabecera de extremo a extremo.

Esto significa que nadie en Internet podrá ver el origen o el destino del tráfico dentro de las redes internas de su organización a ambos lados de esa conexión VPN.

### Resúmen

Así que recuerde, cuando se trata de proteger las comunicaciones de red, normalmente confiamos en una VPN, TLS o IPSec para garantizar que los datos permanezcan a salvo de miradas indiscretas 
mientras atraviesan una red no fiable o insegura como Internet. 

Una VPN o Red Privada Virtual es una conexión segura y encriptada entre el dispositivo de un usuario y un servidor remoto que permite
el acceso privado y anónimo a Internet. 

Una VPN de cliente a sitio permitirá a usuarios individuales conectarse remotamente a una red segura, mientras que una VPN de sitio a sitio establece una conexión segura entre dos ubicaciones de red separadas.

Una VPN sin cliente es una solución de acceso remoto que va a permitir a los usuarios acceder de forma segura a los recursos de red utilizando un navegador web sin necesidad de una pieza dedicada de software cliente que va a depender del protocolo TLS (Transport Layer Security) para su cifrado.

IPSec o Internet Protocol Security Suite es un conjunto de protocolos que se utiliza para proteger las comunicaciones de protocolo de Internet autenticando ¿y cifrando cada paquete IP en el flujo de datos.

IPSec puede configurarse para utilizar el modo transporte o el modo túnel.

El modo de transporte se utiliza normalmente para las VPN cliente-sitio, mientras que el modo túnel se utiliza normalmente para las VPN sitio-sitio.

## SD-WAN y SASE

Ahora que nuestras organizaciones dependen cada vez más de las aplicaciones basadas en la nube que utilizan nuestros trabajadores distribuidos geográficamente,
ha aumentado la demanda de una infraestructura de red ágil, segura y eficiente que se cree rápidamente.

Una red de área extensa definida por software, o SD-WAN, es un enfoque virtualizado para gestionar y optimizar las conexiones de red de área extensa
para dirigir eficazmente el tráfico entre sitios remotos, centros de datos y entornos de nube.

Por otro lado, el marco de borde de servicio de acceso seguro, o SASE, se utiliza para consolidar numerosas funciones de red y seguridad en un único servicio nativo de la nube, con el fin de garantizar un acceso seguro y sin fisuras para los usuarios finales, independientemente de su ubicación física real.

Juntos, SD-WAN y SASE representan una gran innovación en nuestras arquitecturas de red y seguridad.

SD-WAN (Software-Defined WAN)

Una SD-WAN permite administrar una red WAN mediante software, sin depender tanto de configuraciones manuales en equipos físicos específicos.

¿Qué quiere decir?

Antes, para controlar el tráfico entre sucursales se usaban equipos y tecnologías específicas (como MPLS) que requerían mucha configuración en el hardware.

Con SD-WAN, la inteligencia y las decisiones de la red se manejan desde un software centralizado. Así puedes configurar reglas, prioridades y rutas desde una consola, sin tener que modificar cada dispositivo físico.

Aspectos:

- Es una forma moderna de gestionar redes WAN mediante software.
- Permite conectar sucursales, centros de datos y la nube de forma más inteligente.
- Puede usar distintos tipos de conexión (Internet, fibra, celular, MPLS, etc.).
- Decide automáticamente la mejor ruta para el tráfico.
- Mejora el rendimiento, reduce cuellos de botella y simplifica la administración. Cuello de botella significa un punto de la red que es más lento que el resto y que termina frenando todo el tráfico.
- Con SD-WAN, el tráfico puede repartirse por distintas conexiones disponibles.

Ejemplo: En lugar de que todo el tráfico de una sucursal pase por la sede central, SD-WAN puede enviarlo directamente a Microsoft 365, Google o AWS si es más rápido.

Para crear una SD-WAN, puede utilizar una función de control centralizada para redirigir de forma segura e inteligente el tráfico
a través de la WAN. Nuestras WAN tradicionales, que nunca se desarrollaron con la idea de integrar servicios en la nube
en nuestras redes empresariales, sencillamente no son capaces de hacerlo.

Pero, en lugar de eso, podemos utilizar una SD-WAN porque están habilitadas para que las empresas que dan prioridad
a la nube ofrezcan experiencias de calidad asombrosas a sus usuarios finales. Pensemos en una empresa que tiene varias sucursales
y una sede central. En nuestras arquitecturas WAN tradicionales, cada una de esas sucursales estaría probablemente conectada
a la oficina central mediante una topología en estrella. Esto permitiría a la sede central llevar a cabo una seguridad avanzada de ese tráfico
a medida que pasara por las sucursales hasta la sede central, y luego a Internet. Esto es genial para la seguridad, seguro.

Pero realmente ralentiza todo el proceso para nuestros usuarios finales en esas sucursales, y se traduce en una mala experiencia de usuario
y pérdida de productividad.

Sin embargo, a diferencia de las arquitecturas tradicionales, las SD-WAN pueden resolver este problema mediante el uso de inteligencia
para identificar las aplicaciones de red que utilizan los usuarios finales y enrutar los datos a través de la WAN a los lugares adecuados.

Por lo tanto, si trabaja en una red de una gran empresa y tiene muchas sucursales, y todas ellas están intentando moverse cada vez más hacia la nube utilizando
cosas como IaaS, y PaaS, y SaaS, entonces puede que necesite utilizar una SD-WAN

Vamos a repasar brevemente los 3 servicios mencionados anteriormente: Iaas, PaaS y SaaS

IaaS (Infrastructure as a Service) → Te alquilan la infraestructura (servidores, almacenamiento, red). Tú instalas y administras el sistema operativo y las aplicaciones.
Ejemplo: máquinas virtuales en AWS o Azure.

PaaS (Platform as a Service) → Te dan una plataforma lista para desarrollar y ejecutar aplicaciones. Tú solo te preocupas por el código.
Ejemplo: Google App Engine.

SaaS (Software as a Service) → Te dan una aplicación lista para usar a través de Internet.
Ejemplo: Gmail, Google Drive, Microsoft 365.

SASE (Secure Access Service Edge/Borde de servicio de Acceso Seguro)

Es un nuevo tipo de arquitectura de red que combina la seguridad de la red y las capacidades de las redes de área amplia, o WAN, en una única solución.
El servicio de acceso seguro Edge se considera una forma de afrontar los retos de proteger y conectar a los usuarios y los datos distribuidos en múltiples ubicaciones, como sucursales, trabajadores remotos y usuarios móviles, además de la propia nube.

Un aspecto clave de la tecnología SASE es que utiliza redes definidas por software, o SDN, para proporcionar servicios de seguridad y redes desde la nube en lugar de desde dispositivos tradicionales basados en hardware.

Aspectos:

- Combina red y seguridad en un único servicio basado en la nube.
Incluye funciones como:
   - Firewall
   - VPN
   - Zero Trust
   - CASB (seguridad para aplicaciones en la nube)
- Protege a usuarios remotos, sucursales y dispositivos sin importar dónde estén.

Ejemplo: Un empleado trabajando desde casa puede conectarse de forma segura a las aplicaciones de la empresa sin necesidad de estar en la oficina.

Los principales proveedores de nube (AWS, Azure y Google Cloud) ofrecen servicios que ayudan a implementar conceptos similares a SASE (seguridad y conectividad en la nube), aunque cada uno les da nombres diferentes.

- AWS usa VPC (Virtual Private Cloud) para crear redes privadas y seguras en la nube.
- Azure ofrece Azure Virtual WAN y ExpressRoute para conectar sucursales, centros de datos y recursos en la nube de forma segura.
- Google Cloud utiliza Cloud Interconnect y Cloud VPN para conectar redes locales con la nube mediante conexiones privadas o túneles VPN.

Estas diferentes herramientas y protocolos se van a utilizar para ayudar a cifrar nuestros datos y protegerlos de posibles escuchas o modificaciones en su tránsito por Internet y otras redes inseguras.

#### Resúmen Breve

"Así que, recuerde, a medida que evolucionan las ciberamenazas y nuestros entornos de trabajo se dispersan cada vez más geográficamente, va a
ser importante que tenga en cuenta la comprensión y la implementación de soluciones como SD-WAN y SASE.

Estas tecnologías no se limitan a seguir el ritmo de la transformación digital, sino que en realidad se centran en anticipar el futuro,
prepararse para sus retos y aprovechar sus oportunidades potenciales.

Una SD-WAN, o red de área extensa definida por software, va a ser un enfoque virtualizado para gestionar y optimizar las conexiones de red de área extensa con el fin de dirigir eficazmente el tráfico entre sitios remotos, centros de datos y su entorno de nube.

Por su parte, el borde de servicio de acceso seguro, o SASE, es un marco de seguridad que combina la seguridad de la red y las
capacidades de la red de área amplia en un único servicio basado en la nube. Al aprovechar estas herramientas, somos capaces de elevar nuestra postura de seguridad organizativa y seguir avanzando en nuestras carreras de seguridad a medida que empezamos a migrar en mayor medida a entornos basados en la nube".

Diferencia entre ellas

SD-WAN: Optimiza y dirige el tráfico de red. Es decir se enfoca en la conectividad. Gestiona la WAN por software.

SASE: Optimiza el tráfico y además añade seguridad. Es decir se enfoca en conectividad + seguridad. Integra SD-WAN con firewall, VPN, Zero Trust, etc.

## Consideraciones de infraestructura de red

Al diseñar una red, hay que tomar decisiones importantes para que sea rápida, segura y confiable. La colocación adecuada garantizará un flujo de datos óptimo,
minimizará la latencia y proporcionará una sólida defensa contra posibles brechas de seguridad. Los puntos principales son:

1. Ubicación de los dispositivos

Los routers suelen ir en el borde de la red para controlar el tráfico que entra y sale(frontera o puerta principal de la red). Es decir, ayuda a dirigir y filtrar el tráfico entrante y saliente de forma mucho más eficaz.

Los switches/conmutadores (distribuidor interno que conecta los dispositivos dentro de la red), deben colocarse en una posición que permita conectar fácilmente los distintos dispositivos al segmento físico adecuado de la red. Si coloca sus dispositivos en los lugares equivocados, puede provocar cuellos de botella en la red, puntos vulnerables o incluso zonas sin conectividad.

Los puntos de acceso Wi-Fi deben ubicarse donde den buena cobertura sin generar interferencias. Deben colocarse estratégicamente para proporcionar una cobertura adecuada al tiempo que se intenta mantener todas las señales inalámbricas localizadas dentro de las instalaciones y garantizar que se evitan las interferencias entre el sistema y otros. Una mala ubicación puede provocar lentitud, zonas sin señal o problemas de seguridad.

La interferencia ocurre cuando dos o más puntos de acceso Wi-Fi usan canales iguales o muy cercanos y sus señales se solapan demasiado.

Por ejemplo:

✅ Bien: Dos puntos de acceso separados y configurados en canales diferentes para cubrir una oficina grande.
❌ Mal: Dos puntos de acceso muy cerca uno del otro usando el mismo canal, porque sus señales compiten y la red puede volverse más lenta.

2. Zonas de seguridad y subredes protegidas (DMZ)

Tenemos que considerar cómo vamos a configurar las zonas de seguridad y las subredes protegidas en nuestra arquitectura de red.
Ahora bien, una zona de seguridad es un segmento distinto dentro de una red, a menudo creado aislando lógicamente el segmento mediante un cortafuegos u otro dispositivo de seguridad. Estas zonas o segmentos de seguridad se diseñarán para contener dispositivos con requisitos de seguridad y niveles de confianza similares.

Por ejemplo, una empresa puede tener diferentes zonas para sus servicios de cara al público, los recursos internos de los empleados y el almacenamiento de datos sensibles, y cada una de ellas se configurará con diferentes controles de acceso y diferentes políticas de seguridad basadas en la sensibilidad o clasificación de los datos contenidos en cada una de esas zonas de seguridad.

Ahora, también se puede crear una subred apantallada para que actúe como capa protectora o zona tampón entre la red interna de una organización y una red externa no fiable como Internet.

Una subred protegida se utiliza para alojar servicios públicos como servidores web, servidores de correo electrónico y servidores DNS, al tiempo que garantiza que si se produce una brecha de seguridad dentro de esa subred protegida, el atacante no tendrá acceso directo a la red interna principal que contiene sus datos o sistemas más sensibles.

Esta subred apantallada se utilizará para proporcionar una capa adicional de seguridad que dificulte a un actor malicioso el acceso a las partes más internas y valiosas de la red de su organización. Si un atacante compromete un servidor de la DMZ, no tendrá acceso directo a la red interna, porque hay una separación y reglas de seguridad adicionales.

Arquitectura:

Internet
    │
[ Firewall ]
    │
[ Subred protegida / DMZ ]
    ├─ Servidor web
    └─ Servidor correo
    │
[ Firewall ]
    │
[ Red interna ]
    ├─ PCs
    └─ Bases de datos

Aptitudes:

- La red se divide en zonas según el nivel de seguridad.

- Los servicios públicos (web, correo, DNS) suelen colocarse en una subred protegida o DMZ.

- Si un atacante compromete un servidor de la DMZ, no tendrá acceso directo a la red interna.

3. Superficie de ataque

Es el conjunto de todos los puntos que un atacante podría intentar explotar.
- Cuantos más dispositivos, puertos abiertos y servicios haya, mayor será la superficie de ataque.
- Se reduce eliminando servicios innecesarios, cerrando puertos y corrigiendo vulnerabilidades.

La colocación incorrecta de dispositivos, dispositivos configurados incorrectamente, software obsoleto, puertos abiertos innecesarios y controles de acceso débiles que se están utilizando. Para reducir su superficie de ataque, debe identificar las vulnerabilidades y eliminarlas o implantar los controles adecuados para mitigar el riesgo asociado a dichas vulnerabilidades.

4. Diferentes Métodos de conectividad

La conectividad se refiere al modo en que los distintos componentes de una red van a comunicarse entre sí y con nuestras redes externas.

Ethernet (cable): más rápido y estable. La desventaja es que si queremos cambiar de sitio los cables cableados también tendrán que ser movidos, o nuevos tendrán que ser instalados para apoyar su nueva ubicación de la oficina.
Wi-Fi: más flexible, pero puede sufrir interferencias y riesgos de seguridad.
Fibra óptica: muy rápida y para largas distancias.
Microondas y satélite: útiles cuando no hay cableado, ofrece velocidad, flexibilidad y escalabilidad. Siempre cuando hablemos de Escalabilidad significa la capacidad de un sistema o red para crecer o soportar más usuarios, dispositivos o tráfico sin perder rendimiento.
Muchas empresas usan una combinación de varias tecnologías.

5. Atributos de los dispositivos que afectarán a su utilización en la arquitectura de nuestra red (Dispositivos activos y pasivos)

Activo: puede intervenir en el tráfico.

Ejemplo: IPS (Intrusion Prevention System).
Puede bloquear ataques.

Pasivo: solo observa y reporta.

Ejemplo: IDS (Intrusion Detection System).
No bloquea nada.

Los dispositivos de seguridad de red pueden instalarse como dispositivo en línea o como configuración basada en tomas. Además pueden instalarse:

En línea (Inline):

Todo el tráfico pasa a través del dispositivo.
Puede bloquear o filtrar.

Esto convierte a un dispositivo en línea, como un cortafuegos, un enrutador o un sistema de prevención de intrusiones, en una herramienta realmente
crítica para tareas como filtrar el tráfico malicioso u optimizar nuestros flujos de datos.

Tap(Escuchas)/Monitores:

Funcionan de forma mucho más discreta porque se colocan fuera de la ruta directa de la red y están configurados para limitarse a escuchar la actividad de la red capturando datos para su análisis sin afectar al tráfico real. Es decir:

- Solo recibe una copia del tráfico.
- Analiza sin afectar la red.

Esto los hace ideales para supervisar la salud, el rendimiento y la seguridad de la red sin arriesgarse a que se produzca ningún tipo de interrupción en la misma. Por lo tanto, a la hora de seleccionar un dispositivo de seguridad para su red, debe tener en cuenta si va a configurarlo como dispositivo en línea o de derivación para optimizar la seguridad y el rendimiento de la red.

Asegúrese siempre de alinear sus opciones con los objetivos y retos más amplios de la red.

Por ejemplo, una organización que requiera mitigar las amenazas en tiempo real podría dar prioridad a la instalación de un dispositivo de seguridad en línea, mientras que otra que se centre más en la supervisión podría optar por utilizar una escucha pasiva o un monitor.

6. Modos de fallo (Fail Modes)

Fail Open (fallo abierto):

Si el dispositivo falla, deja pasar todo el tráfico.
Mantiene la conectividad.
Reduce la seguridad.

Fail Closed (fallo cerrado):

Si falla, bloquea todo el tráfico.
Mantiene la seguridad.
Interrumpe el servicio.

Por ejemplo, un centro de datos que se utiliza para almacenar todos los datos financieros confidenciales de la organización podría optar por utilizar un modo cerrado ante fallos para mantener la seguridad de los datos en caso de fallo de un dispositivo.

Por otro lado, si está operando una red inalámbrica de invitados, es posible que prefiera utilizar un modo abierto ante fallos para garantizar el acceso ininterrumpido de todos sus usuarios, porque en realidad no está tratando de proteger ningún dato o servidor sensible dentro de esa red inalámbrica de invitados de todos modos.

#### Resúmen Breve

Así que recuerde, las consideraciones de infraestructura desempeñan un papel fundamental en la eficacia y seguridad de un entorno de red.

Por lo tanto, es importante tener en cuenta la ubicación de los dispositivos en la arquitectura de la red para optimizar
el flujo de datos y la seguridad.

Las zonas de seguridad y las subredes protegidas también pueden utilizarse para aislar y proteger segmentos de red dentro de su arquitectura. Como profesionales de la ciberseguridad, nuestro trabajo consiste en comprender la superficie de ataque de nuestra organización y proporcionar formas de minimizarla para que nuestra seguridad aumente.

Además, debemos tener en cuenta los distintos métodos de conectividad que puede utilizar en sus redes para poder elegir el adecuado que
le proporcione tanto el rendimiento como la flexibilidad que su organización necesita. Al instalar varios dispositivos de red y seguridad
en su arquitectura, también debe considerar si deben colocarse en un papel activo o pasivo, y si se van a instalar en línea o como posición de escucha o monitor.

Por último, debes ser consciente de que el modo de fallo de tus distintos dispositivos incluye cosas como fallo-abierto y fallo-cerrado, y necesitas saber
qué van a hacer y qué protecciones te proporcionarán o no si el dispositivo se sobrecarga o no funciona como está diseñado.

## Selección de controles de infraestructura

Un control es una medida de seguridad que se implementa para reducir riesgos y proteger los activos de una organización (por ejemplo: firewall, antivirus, autenticación multifactor, IDS/IPS, etc.).

#### Principios clave para seleccionar controles

Clave del Mínimo privilegio: cada usuario o sistema debe tener solo los permisos necesarios para realizar su trabajo. Seleccionar e implementar controles asociados con el principio del menor privilegio realmente ayuda a reducir la superficie potencial de ataque de su red.

Defensa en profundidad: usar varias capas de seguridad; si una falla, las demás siguen protegiendo.

Enfoque basado en riesgos: priorizar los controles según los riesgos más importantes, ya que no se puede proteger todo al máximo. Al fin y al cabo, ninguna organización dispone del tiempo ni del dinero suficientes para mitigar por completo todas y cada una de las amenazas o vulnerabilidades potenciales que existen. Así que tenemos que priorizarlos utilizando un enfoque basado en el riesgo para utilizar de forma más eficaz nuestros limitados recursos y, al mismo tiempo, ofrecernos la mejor protección para nuestras infraestructuras.

Gestión del ciclo de vida: revisar, actualizar y retirar controles periódicamente.

La Concentración de Principio de Diseño abierto: los controles deben ser transparentes y poder ser evaluados y auditados para comprobar su eficacia.

#### Metodología para seleccionar controles

La metodología básica que se recomienda consiste en evaluar el estado actual, realizar un análisis de carencias, fijar objetivos claros, llevar a cabo una evaluación comparativa, realizar un análisis de costes y beneficios, garantizar la participación de las partes interesadas y, a continuación, implantar
circuitos de supervisión y retroalimentación en su organización.

1. Evaluar el estado actual de la seguridad.
2. Realizar un análisis de brechas (comparar situación actual vs. deseada) que quiere lograr dentro de la red de su organización.
3. Definir objetivos claros.
4. Compararse con las mejores prácticas del sector (benchmarking).
5. Hacer un análisis costo-beneficio.
6. Involucrar a las partes interesadas y analizarlo (usuarios, directivos, técnicos).
7. Monitorear y mejorar continuamente los controles implementados (crear circuitos de seguimiento y retroalimentación para asegurarnos de que nuestros controles siguen siendo eficaces a lo largo del tiempo).

#### Mejores prácticas que se pueden utilizar durante la selección de diversos controles para las redes de su empresa.

1. Realizar evaluaciones de riesgo de forma periódica.
- Basarse en marcos reconocidos como:
   - NIST
   - ISO
   Estos marcos han publicado directrices que se han revisado y perfeccionado con el tiempo. Si se adhiere a estos marcos, puede
   estar seguro de que su enfoque es exhaustivo y se basa en metodologías probadas.

- Adaptar los controles a las necesidades específicas de la organización (Personalizar/Configurar los marcos a los objetivos de su organización).
- Capacitar continuamente a los usuarios y administradores.

Los controles de seguridad no se implementan una sola vez. Deben evaluarse, actualizarse y mejorarse constantemente para seguir siendo efectivos frente a nuevas amenazas.

#### Resúmen Breve

Así que recuerde, un control es una medida o salvaguarda que se aplica para mitigar los riesgos potenciales y proteger los activos de una organización.

La selección de controles eficaces garantizará que podamos prevenir las infracciones y minimizar las vulnerabilidades, al tiempo que nos aseguramos de que nuestros recursos se utilizan de forma eficiente.

Para seleccionar sus controles, debe utilizar una metodología estructurada como la metodología básica que he presentado, que incluye una evaluación del estado actual, un análisis de carencias, objetivos claros, evaluación comparativa, un análisis coste-beneficio, la participación de las partes interesadas y bucles de seguimiento y retroalimentación.

Además, esa selección de controles no va a ser un hecho puntual, sino que es algo que debemos practicar una y otra vez, y recomiendo que lo haga anual o trimestralmente en función de su negocio para garantizar que la infraestructura de su empresa sigue siendo segura.
