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
Fail Open: si falla el dispositivo, deja pasar el tráfico.
Fail Closed: si falla el dispositivo, bloquea el tráfico.

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
Puerto 137, 138 y 139 – Se utilizan para NetBIOS. NetBIOS es un conjunto de protocolos de red. NetBIOS se utiliza dentro de un entorno de dominio Windows para poder compartir cosas 
como nombres de red internos, así como para compartir archivos e impresoras en un entorno Windows local. (TCP & UDP)
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
