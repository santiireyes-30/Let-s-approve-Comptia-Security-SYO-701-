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


4. Jump Server (Servidor de salto)

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

### Breve

Asi que Recuerde que los dispositivos de red son equipos de hardware dedicados con software preinstalado diseñados para proporcionar servicios de red específicos.

Los equilibradores de carga distribuyen el tráfico de red o de aplicaciones entre varios servidores para optimizar su rendimiento y evitar la sobrecarga de un único servidor.

Los servidores proxy también actuarán como intermediarios entre sus clientes y sus servidores para gestionar el flujo de datos y ofrecer mayores niveles de seguridad y control de contenidos.

Los sensores son herramientas o dispositivos que supervisan diversas condiciones físicas o de la red para proporcionar datos en tiempo real
para la optimización y seguridad del sistema.

Los servidores de salto o jump boxes son plataformas intermediarias seguras que los administradores pueden utilizar para acceder a dispositivos a través
de diferentes zonas de seguridad dentro de una red determinada.

Juntos, estos cuatro tipos de dispositivos de red nos ayudarán a garantizar la eficacia, seguridad y alto rendimiento de la infraestructura.
