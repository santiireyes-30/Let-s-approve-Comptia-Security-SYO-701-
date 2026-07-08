## Vulnerabilidades y Ataques

Las vulnerabilidades son debilidades o fallos en el hardware, software, configuraciones o procesos que pueden ser explotados por un atacante. Los ataques son acciones maliciosas que aprovechan 
esas vulnerabilidades para comprometer la confidencialidad, integridad o disponibilidad de un sistema. Haremos un breve repaso primero de lo que veremos (11 puntos + algúnos conceptos importantes)

Principales temas

1. Vulnerabilidades de hardware

Afectan a servidores, computadoras, dispositivos móviles, routers, switches e IoT, enrutadores, dispositivos de red. Las causas más comunes son:

Firmware desactualizado.
Sistemas heredados (Legacy) o sin soporte.
Falta de parches.
Configuraciones incorrectas.

Mitigación: aplicar parches, endurecimiento (hardening), retirar equipos obsoletos y segmentar la red.

2. Ataques a Bluetooth

Los principales ataques son:

Bluesnarfing: robo de información mediante Bluetooth.
Bluejacking: envío de mensajes no solicitados.
Bluebugging: toma de control del dispositivo.
Bluesmack: ataque de denegación de servicio (DoS).
BlueBorne: explotación de vulnerabilidades para ejecutar código sin emparejamiento.

3. Vulnerabilidades en dispositivos móviles

Incluyen:

Sideloading: instalar aplicaciones desde fuentes no oficiales.
Jailbreaking/Rooting: eliminar restricciones del sistema operativo.
Conexión a redes Wi-Fi o Bluetooth inseguras.

Mitigación: MDM (Mobile Device Management), actualizaciones y bloqueo del sideloading y rooting.

4. Vulnerabilidades de Día Cero (Zero-Day)

Son fallos recién descubiertos que aún no tienen un parche disponible, por lo que son especialmente peligrosos y muy utilizados por ciberdelincuentes y grupos patrocinados por estados.

5. Vulnerabilidades del sistema operativo

Las más comunes son:

Sistemas sin actualizar.
Vulnerabilidades Zero-Day.
Configuraciones inseguras.
Fuga de datos.
Actualizaciones maliciosas.

Mitigación: parches, cifrado, antivirus/EDR, firewall del host, IPS, listas blancas de aplicaciones y controles de acceso.

6. Inyección SQL (SQL Injection)

Ataque donde se introducen comandos SQL maliciosos para acceder, modificar o eliminar información de una base de datos.

7. Inyección XML (XPath Injection)

Manipulación de datos XML para acceder de forma no autorizada o alterar el funcionamiento de aplicaciones que procesan XML.

8. Cross-Site Scripting (XSS)

El atacante inserta código JavaScript malicioso en una página web para que se ejecute en el navegador de otros usuarios.

9. Cross-Site Request Forgery (CSRF/XSRF)/Falsificaciones De Peticiones Entre Sitios

El atacante engaña a un usuario autenticado para que realice acciones en un sitio web sin darse cuenta.

10. Desbordamiento de búfer (Buffer Overflow)

Ocurre cuando un programa escribe más datos de los que un espacio de memoria puede almacenar, permitiendo ejecutar código malicioso o provocar fallos.

11. Condición de carrera (Race Condition)

Sucede cuando varios procesos acceden simultáneamente a un mismo recurso, generando resultados inesperados o vulnerabilidades por el orden de ejecución.

Medidas de mitigación más importantes

- Mantener sistemas y firmware actualizados.
- Aplicar parches de seguridad.
- Implementar hardening.
- Segmentar la red.
- Utilizar MDM en dispositivos móviles.
- Configurar correctamente permisos y controles de acceso.
- Implementar firewall, IPS y protección de endpoints.
- Utilizar listas blancas de aplicaciones (Application Allowlisting).

Conceptos clave para recordar

- Vulnerabilidad: debilidad de un sistema.
- Ataque: explotación de una vulnerabilidad.
- Zero-Day: vulnerabilidad nueva sin parche disponible.
- SQL Injection: manipulación de bases de datos mediante consultas SQL.
- XSS: ejecución de scripts maliciosos en el navegador de la víctima.
- CSRF: obliga a un usuario autenticado a realizar acciones sin su consentimiento.
- Buffer Overflow: escritura fuera de los límites de memoria.
Race Condition: acceso simultáneo a un recurso compartido que genera comportamientos inesperados

Aquí en esta sección también vamos a cubrir algunos términos clave como el tiempo de comprobación, el objetivo de la evaluación y el tiempo de uso, ya que también
se relacionan con las condiciones de carrera.

## Vulnerabilidades de Hardware

Las vulnerabilidades de hardware son fallos o debilidades en los componentes físicos o en su diseño que pueden ser explotados para comprometer la confidencialidad, integridad o disponibilidad de un sistema.

Principales vulnerabilidades

1. Firmware vulnerable

El firmware es el software de bajo nivel que controla el funcionamiento del hardware (routers, BIOS/UEFI, dispositivos IoT, etc.).

Riesgos:

Control total del dispositivo por parte del atacante.
Acceso no autorizado.
Robo de datos.
Toma completa del equipo.

Mitigación:

Actualizar el firmware periódicamente.
Realizar auditorías de seguridad.
Aplicar hardening (endurecimiento).

2. Sistemas al final de su vida útil (End of Life - EOL)

Son equipos o software cuyo fabricante ya no ofrece soporte ni actualizaciones.

Riesgos:

Vulnerabilidades sin corregir.
Mayor exposición a ataques conocidos.

Mitigación:

Reemplazar o retirar estos sistemas.
Si no es posible, aislarlos de la red.

3. Sistemas heredados (Legacy) y sin soporte

Son tecnologías antiguas que siguen en uso, pero ya no reciben soporte técnico ni parches de seguridad.

Riesgos:

Vulnerabilidades permanentes.
Incompatibilidad con nuevas medidas de seguridad.

Mitigación:

Migrar a tecnologías modernas.
Segmentar o aislar los sistemas mientras continúan en uso.

4. Sistemas sin parches (Unpatched Systems)

Son dispositivos o aplicaciones que no tienen instaladas las últimas actualizaciones de seguridad.

Riesgos:

Explotación de vulnerabilidades conocidas.
Robo de información.
Interrupción de servicios.

Mitigación:

Implementar una política de gestión de parches.
Actualizar sistemas de forma periódica.

Estos tres conceptos son muy similares entre sí(Unpatched Systems, Legacy, End of Life), y a menudo se utilizan indistintamente cuando se habla del final de la vida útil, de sistemas y aplicaciones heredados y sin soporte.
Este tipo de sistemas y aplicaciones son especialmente vulnerables porque cualquier fallo de seguridad existente no se solucionará con parches o actualizaciones, y esto deja al sistema
expuesto a esas vulnerabilidades conocidas.

5. Configuraciones incorrectas (Misconfiguration)

Se producen cuando un dispositivo está configurado de forma insegura o incorrecta.

Ejemplos:

Puertos abiertos innecesariamente.
Contraseñas por defecto.
Permisos excesivos.
Servicios innecesarios habilitados.

Mitigación:

Auditorías periódicas.
Aplicar configuraciones seguras.
Automatizar la detección de errores.
Capacitar al personal.
Técnicas para mitigar vulnerabilidades

Hardening (Endurecimiento)

Consiste en reforzar la seguridad del sistema:

Cerrar puertos innecesarios.
Desactivar servicios innecesarios.
Configurar correctamente permisos.
Gestión de parches

Actualizar regularmente:

Sistema operativo.
Firmware.
Aplicaciones.
Refuerzo de configuración

Aplicar configuraciones seguras y estandarizadas para evitar errores de configuración.

Desmantelamiento (Decommissioning)

Retirar de la red los equipos antiguos, heredados o sin soporte cuando representan un riesgo.

Aislamiento (Isolation)

Separar un sistema vulnerable del resto de la red para reducir el impacto de un posible ataque.

Segmentación (Segmentation)

Dividir la red en diferentes segmentos para evitar que un atacante pueda desplazarse fácilmente si compromete un dispositivo.

Conceptos clave para recordar

- Firmware: software de bajo nivel que controla el hardware.
- End of Life (EOL): producto sin soporte ni actualizaciones del fabricante.
- Legacy: tecnología antigua que aún se utiliza.
- Unpatched System: sistema sin los últimos parches de seguridad.
- Misconfiguration: configuración incorrecta que genera vulnerabilidades.
- Hardening: fortalecimiento de la seguridad del sistema. 
- Decommissioning: retirada definitiva de equipos inseguros.
- Isolation: separación de sistemas vulnerables.
- Segmentation: división de la red para limitar la propagación de ataques.

#### Resúmen Breve

Así pues, recuerde que las vulnerabilidades de hardware son fallos o debilidades de seguridad inherentes a los componentes físicos o al diseño de un dispositivo que pueden aprovecharse
para comprometer la integridad, confidencialidad o disponibilidad del sistema y sus datos.

Existen numerosas vulnerabilidades de hardware que debemos tener en cuenta, como el firmware del dispositivo, el hardware que ha llegado al final de su vida útil, el hardware heredado, 
los sistemas y aplicaciones no compatibles, los sistemas sin parches y los errores de configuración del hardware.

Para mitigar estos tipos de vulnerabilidades de hardware, debe llevar a cabo el endurecimiento, la aplicación de parches, el refuerzo de la configuración, el desmantelamiento, el aislamiento
y la segmentación para mitigar cualquier vulnerabilidad conocida en sus dispositivos y sistemas.

## Vulnerabilidades y ataques de Bluetooth
¿Qué es Bluetooth?

Bluetooth es una tecnología inalámbrica de corto alcance que permite conectar e intercambiar datos entre dispositivos sin necesidad de Internet (celulares, auriculares, autos, teclados, etc.).

Vulnerabilidades de Bluetooth

Las principales debilidades son:

Emparejamiento inseguro(insecure device pairing): se produce cuando los dispositivos bluetooth establecen una conexión sin autenticación adeacuada o con autenticación débil, permitiendo accesos no autorizados.
Suplantación de dispositivos (Spoofing): un atacante se hace pasar por un dispositivo Bluetooth legítimo.
Ataque en ruta (Man-in-the-Middle): el atacante intercepta y puede modificar la comunicación entre dos dispositivos, este explota una vulnerabilidad en el protocolo de comunicaciones Bluetooth

Ataques Bluetooth más comunes:

Bluejacking: envío de mensajes no solicitados. Generalmente es una broma o para probar la vulnerabilidad del dispositivo sin causar ningún tipo de daño grave.y no roba información.
Bluesnarfing: acceso no autorizado para robar contactos, mensajes, registros de llamadas y otros datos.
Bluebugging: el atacante toma el control del dispositivo, pudiendo realizar llamadas, enviar mensajes o acceder a Internet.
Bluesmack: ataque de denegación de servicio (DoS) que satura el dispositivo hasta bloquearlo.
Blueborne: explota vulnerabilidades de Bluetooth para infectar dispositivos cercanos (puede propagarse a través del aire), sin que el usuario intervenga.

Buenas prácticas para proteger Bluetooth

Desactivar Bluetooth cuando no se utilice.
Mantener el dispositivo en modo no detectable por defecto.
Actualizar regularmente el firmware del dispositivo.
Emparejar únicamente con dispositivos conocidos y de confianza.
Utilizar PIN o claves de acceso únicas durante el emparejamiento.
No aceptar solicitudes de conexión o archivos de desconocidos.
Utilizar cifrado para transferir información sensible.

Idea clave para recordar

Bluetooth = Corto alcance, pero también puede ser una puerta de entrada para ataques.

Los ataques más importantes son:

Bluejacking: envía mensajes.
Bluesnarfing: roba información.
Bluebugging: controla el dispositivo.
Bluesmack: provoca un DoS.
Blueborne: infecta dispositivos automáticamente.

La mejor defensa consiste en mantener Bluetooth apagado cuando no se use, actualizar el firmware y conectarse solo a dispositivos de confianza.

## Vulnerabilidades y ataques móviles

Los dispositivos móviles (smartphones, tablets y wearables) almacenan gran cantidad de información personal y empresarial, por lo que son un objetivo frecuente de los atacantes. Las principales vulnerabilidades son:

1. Sideloading (Carga lateral)

Consiste en instalar aplicaciones desde fuentes no oficiales, evitando la tienda oficial del sistema operativo.

Riesgo: puede instalar malware o aplicaciones modificadas.
Mitigación: descargar aplicaciones únicamente desde tiendas oficiales (Google Play, App Store).

2. Jailbreaking y Rooting

Jailbreaking: elimina las restricciones de seguridad en dispositivos iPhone/iPad.
Rooting: otorga privilegios de administrador en dispositivos Android.

Riesgos:

Desactiva protecciones del fabricante.
Puede impedir recibir actualizaciones de seguridad.
Facilita la instalación de malware y el acceso no autorizado.

Mitigación: mantener el dispositivo con su configuración de seguridad original y evitar rootearlo o hacer jailbreak.

3. Métodos de conexión inseguros

Las conexiones inalámbricas pueden ser un punto de ataque.

Ejemplos:

Redes Wi-Fi públicas o abiertas.
Conexiones Bluetooth con dispositivos desconocidos.

Riesgos:

Ataques Man-in-the-Middle (MitM).
Robo de información.
Espionaje del tráfico.
Acceso no autorizado.

Mitigación:

Preferir la red móvil (4G/5G) cuando sea posible.
Utilizar redes Wi-Fi protegidas (WPA2/WPA3).
Emparejar Bluetooth solo con dispositivos confiables.
Mantener Bluetooth oculto cuando no se utilice.
Gestión de Dispositivos Móviles (MDM)

Una solución MDM (Mobile Device Management) permite administrar y proteger todos los dispositivos móviles de una organización desde un panel centralizado.

Sus funciones principales son:

Aplicar parches y actualizaciones automáticamente.
Configurar políticas de seguridad estándar.
Detectar dispositivos con root o jailbreak.
Bloquear la instalación mediante sideloading.
Obligar el uso de VPN para acceder a recursos corporativos.
Gestionar configuraciones y permisos de todos los dispositivos.
Buenas prácticas de seguridad móvil
Descargar aplicaciones solo desde tiendas oficiales.
No realizar root ni jailbreak.
Mantener el sistema operativo y las aplicaciones actualizadas.
Evitar redes Wi-Fi públicas o abiertas.
Conectarse únicamente a dispositivos Bluetooth conocidos.
Utilizar VPN para acceder a información corporativa.
Mantener Bluetooth desactivado cuando no se utilice.
Aplicar políticas de seguridad mediante una solución MDM.

#### Resúmen Breve

Los dispositivos móviles presentan vulnerabilidades como el sideloading, el jailbreaking/rooting y las conexiones inalámbricas inseguras. Para reducir estos riesgos se deben aplicar buenas prácticas de seguridad (actualizaciones, tiendas oficiales, redes seguras y Bluetooth controlado) y, en entornos empresariales, utilizar una solución MDM para administrar y proteger todos los dispositivos de forma centralizada.

Así pues, recuerde que nuestros dispositivos móviles son potentes y cómodos, pero también vulnerables a una amplia gama de amenazas y ataques.
Ya sea la tentación de cargar de forma lateral esa aplicación imprescindible, el atractivo de hacer jailbreak o rootear el dispositivo para disponer de funcionalidades y opciones de configuración adicionales,
o el descuido de conectarse a una red Wi-Fi no segura.

El riesgo para sus dispositivos y los datos que contienen es muy real. Sin embargo, si conoce estas diferentes vulnerabilidades y aplica las mejores prácticas, así como una sólida solución de gestión de dispositivos móviles, podrá disfrutar
de las ventajas de sus dispositivos y, al mismo tiempo, garantizar que sus datos permanezcan seguros y protegidos.

## Vulnerabilidades y exploits de Día Cero (Zero-Day)

Una vulnerabilidad de día cero (Zero-Day Vulnerability) es una falla de seguridad desconocida por el fabricante del software o hardware, pero que ya ha sido descubierta por un atacante. Como aún no existe un parche, el sistema permanece expuesto.

Exploit de Día Cero

Un exploit de día cero (Zero-Day Exploit) es el código o técnica utilizada por un atacante para aprovechar esa vulnerabilidad antes de que el fabricante publique una solución.

¿Por qué son tan peligrosos?

No existe un parche para corregir la vulnerabilidad.
Los antivirus y antimalware tradicionales no pueden detectarlos inicialmente porque aún no poseen firmas para ese ataque o no han sido escrita para esa pieza de software.
Pueden permanecer ocultos durante días, semanas o incluso años.
Valor de los Zero-Day

Las vulnerabilidades y exploits de día cero son extremadamente valiosos porque:

Requieren mucho tiempo y conocimiento para descubrirse.
Empresas ofrecen programas de recompensas (Bug Bounty) para que los investigadores reporten estas vulnerabilidades de forma responsable.
También pueden venderse por grandes sumas de dinero a gobiernos, agencias de inteligencia o, ilegalmente, en la dark web.

¿Quién suele utilizarlos?

Debido a su alto costo, normalmente son utilizados por:

Estados o agencias gubernamentales.
Grupos APT (Amenazas Persistentes Avanzadas).
Ciberdelincuentes que buscan atacar objetivos de alto valor.

Generalmente no se desperdician en ataques comunes, sino contra organizaciones importantes o infraestructuras críticas.

Mitigación

Aunque no exista un parche, se pueden reducir los riesgos mediante:

Mantener el software y el antivirus siempre actualizados.
Aplicar medidas de seguridad en capas (defensa en profundidad).
Monitorizar continuamente la actividad del sistema.
Detectar comportamientos anómalos mediante herramientas como EDR, IDS e IPS.

En resumen

Una vulnerabilidad de día cero es una falla desconocida por el fabricante y sin parche disponible. Un exploit de día cero es el método utilizado para explotarla. 
Son ataques muy peligrosos porque las defensas tradicionales no pueden detectarlos inicialmente, por lo que suelen reservarse para objetivos de alto valor hasta que el fabricante desarrolla y publica una corrección.

Ahora, recuerde, cuando se trata de un día cero, esto significa que su sistema puede ser vulnerable durante días, semanas o incluso años sin que usted siquiera lo sepa porque el propio desarrollador
del software no sabe que existe esa vulnerabilidad y, por lo tanto, no puede hacer un parche para ella.

## Vulnerabilidades del Sistema Operativo

El sistema operativo (SO) es el encargado de administrar el hardware y el software de un dispositivo. Si presenta vulnerabilidades, un atacante puede comprometer la confidencialidad, integridad y disponibilidad del sistema.

1. Sistemas sin parches (Unpatched Systems)

Son sistemas que no han instalado las últimas actualizaciones de seguridad.

Riesgo: los atacantes pueden explotar vulnerabilidades conocidas.
Mitigación: aplicar parches y mantener las actualizaciones automáticas activadas.

2. Vulnerabilidades de Día Cero (Zero-Day)

Son fallas de seguridad desconocidas por el fabricante, por lo que aún no existe un parche.

Riesgo: son difíciles de detectar y explotar.
Mitigación: implementar defensa en profundidad, mantener el sistema actualizado y utilizar herramientas como HIPS (Host Intrusion Prevention System).

3. Errores de Configuración (Misconfigurations)

Ocurren cuando el sistema está configurado incorrectamente.

Ejemplos:

Contraseñas por defecto.
Servicios innecesarios habilitados.
Funciones de seguridad desactivadas.
Riesgo: crean vulnerabilidades que pueden ser explotadas.
Mitigación: utilizar herramientas de gestión de configuración, aplicar configuraciones seguras y realizar auditorías periódicas.

4. Exfiltración de Datos (Data Exfiltration)

Consiste en la transferencia no autorizada de información desde un sistema hacia un atacante.

Riesgo: robo de información confidencial.

Mitigación:
Cifrar los datos.
Utilizar protección de endpoints (EDR/antivirus).
Implementar firewalls basados en host(Significa instalar y configurar un firewall dentro de un equipo específico (host), como una PC, servidor o notebook, para controlar el tráfico de red que entra y sale de ese dispositivo).
Supervisar el tráfico de salida.

5. Actualizaciones Maliciosas (Malicious Updates)

Son actualizaciones falsas que aparentan ser legítimas, pero contienen malware.

Riesgo: comprometen el sistema al instalar código malicioso.

Mitigación:
Descargar actualizaciones únicamente desde fuentes oficiales.
Verificar la auntenticidad de las actualizaciones mediante firmas digitales o hashes.
Utilizar listas de aplicaciones permitidas (Application Allowlisting).
Medidas generales de protección
Aplicar parches y actualizaciones regularmente.
Utilizar HIPS para detectar actividades sospechosas.
Implementar una correcta gestión de configuraciones.
Cifrar los datos almacenados.
Utilizar firewalls y protección de endpoints.
Verificar siempre la autenticidad de las actualizaciones.
Aplicar el principio de defensa en profundidad.

## Resúmen breve

Así que recuerde que, aunque las vulnerabilidades de los sistemas operativos pueden ser variadas y sofisticadas, incluidos los sistemas sin parches, las vulnerabilidades de día cero,
las configuraciones erróneas, la filtración de datos y las actualizaciones maliciosas, sus medidas de protección no siempre tienen que ser complejas para que sean eficaces.

Desde la aplicación periódica de parches hasta el cifrado y la gestión de la configuración, podemos mejorar considerablemente la seguridad de nuestros dispositivos y nuestros datos aplicando
algunas medidas comunes de defensa en profundidad.


## Vulnerabilidades y ataques de Inyección SQL y XML

¿Qué es un ataque de inyección?

Un ataque de inyección ocurre cuando un atacante introduce código malicioso en un sistema para que este lo interprete como parte de una consulta o comando legítimo.

Su objetivo es manipular el funcionamiento de la aplicación, acceder a información o ejecutar acciones no autorizadas.

SQL (Structured Query Language)

SQL es el lenguaje utilizado para comunicarse con las bases de datos.

Las operaciones principales son:

SELECT: leer datos.
INSERT: insertar datos.
UPDATE: modificar datos.
DELETE: eliminar datos.

¿Qué es una Inyección SQL (SQL Injection)?

Es un ataque donde el atacante introduce código SQL malicioso en un campo de entrada (login, formularios, URL, cookies, encabezados HTTP, etc.) para manipular la consulta que realiza la aplicación sobre la base de datos.

Ejemplo normal

Un usuario inicia sesión con:

Usuario: Jason
Contraseña: Pass123

La aplicación consulta:

SELECT * FROM Users
WHERE user='Jason'
AND password='Pass123';

Si coinciden los datos, permite el acceso.

Ejemplo de SQL Injection

El atacante escribe:

Usuario: Jason
Contraseña: ' OR 1=1 --

La consulta queda:

SELECT * FROM Users
WHERE user='Jason'
AND password=''
OR 1=1;

Como 1=1 siempre es verdadero, la condición completa resulta verdadera y el atacante obtiene acceso sin conocer la contraseña.

En un examen

Si ves algo como:

' OR 1=1
' OR 7=7
' OR 15=15

Piensa inmediatamente en:

SQL Injection

¿Dónde puede inyectarse el código?

Un atacante puede introducir SQL mediante:

Formularios web.
Parámetros en la URL.
Cookies.
Cabeceras HTTP.
Campos de entrada.

¿Cómo prevenir una SQL Injection?

La defensa más importante es:

Validación y sanitización de entradas (Input Validation)

Consiste en revisar y limpiar todos los datos enviados por el usuario antes de enviarlos a la base de datos.

También es recomendable:

Utilizar consultas parametrizadas (Prepared Statements).
Implementar un Web Application Firewall (WAF), entre el servidor web y el cliente
Restringir privilegios de la base de datos.
Restringir el uso de apostrófos y de (N°=N°)

Para el examen: Si preguntan cómo prevenir SQL Injection, la respuesta principal es Validación/Sanitización de entradas.

¿Qué es XML?

XML (Extensible Markup Language) es un formato utilizado para intercambiar datos entre aplicaciones.

Ejemplo:

<$xml version="1.0" encoding="UTF-8"?> (Versión+TipoDeCodificación)
<Question>
   <ID>001</ID>
   <Title>¿Qué es XML?</Title>
</Question>

Se utiliza para:

Autenticación.
Autorización.
Intercambio de información.
Servicios web.

¿Qué es una Inyección XML?

Consiste en introducir datos XML maliciosos para manipular el procesamiento que realiza una aplicación.

Puede provocar:

Acceso no autorizado.
Lectura de archivos.
Robo de datos.
Denegación de servicio.

¿Cómo proteger XML?

Siempre debe utilizarse:

TLS para cifrar los datos en tránsito.
Validación de entrada.
Sanitización de datos.

Ataques XML importantes

1. XML Bomb (Billion Laughs)

Es un ataque de Denegación de Servicio (DoS).

El atacante crea entidades XML que se expanden miles o millones de veces hasta consumir toda la memoria del servidor.

Resultado:

Alto consumo de RAM.
Caída del servidor.
Denegación del servicio.

2. XXE (XML External Entity)

El atacante utiliza entidades XML externas para que el servidor lea archivos locales.

Ejemplo:

<!ENTITY xxe SYSTEM "file:///etc/shadow">

En Linux intenta leer:

/etc/shadow

Archivo que contiene los hashes de las contraseñas del sistema.

Consecuencias:

Robo de archivos.
Exposición de credenciales.
Acceso a información sensible.

Mitigación:

Utilizar Validación de entrada adecuada.
Sanatización de entradas

#### Definiciones Breve

- Inyección: envío de código malicioso para alterar el comportamiento de una aplicación.
- SQL Injection: inserta código SQL para manipular una base de datos.
- XML Injection: inserta código XML para explotar aplicaciones que procesan XML.
- ' OR 1=1 es el ejemplo clásico de SQL Injection.
- XML Bomb: provoca una denegación de servicio consumiendo memoria.
- XXE: permite leer archivos del sistema o acceder a recursos internos.

La mejor defensa para SQL y XML Injection es la validación y sanitización de entradas, complementada con el uso de TLS (en XML) y un WAF cuando sea posible.

#### Resúmen Breve

Así que recuerde, una inyección se produce cuando un atacante envía datos maliciosos a un sistema, y luego va a ser procesado como parte de
una consulta de comandante que puede conducir a consecuencias no deseadas.

Una inyección SQL es una técnica de ataque en la que se inserta código SQL malicioso en campos de entrada para manipular o explotar una aplicación basada en bases de datos.
Si ves algo como apóstrofe uno es igual a uno, esto va a ser una inyección SQL. Por otro lado, las inyecciones XML son una técnica de ataque en la que se inserta código XML malicioso en campos
de entrada para manipular o explotar una aplicación o servicio basado en XML.

Si ves algún código que parece estar escrito en formato XML en un fragmento de registro en el examen, puedes suponer con seguridad que se trata de una inyección XML que está siendo intentada por un atacante.

## Cross-Site Scripting (XSS) y Cross-Site Request Forgery (CSRF/XSRF)

1. Cross-Site Scripting (XSS)

¿Qué es?
Es un ataque en el que un atacante inyecta código JavaScript malicioso en un sitio web vulnerable. Cuando otro usuario visita ese sitio, el navegador ejecuta ese código como si fuera confiable.

La víctima ejecuta el código.

¿Cómo funciona?

El atacante encuentra un formulario vulnerable (comentarios, búsqueda, chat, etc.).
Inserta código JavaScript malicioso.
El sitio web lo almacena o lo devuelve al usuario.
El navegador de la víctima ejecuta el script.

Objetivos del atacante:

Robar cookies de sesión.
Robar credenciales.
Instalar malware.
Redirigir al usuario a otro sitio.
Modificar la página (defacement).
Registrar lo que escribe el usuario (keylogging).

Tipos de XSS

1. Reflected XSS (No persistente)

El código viaja en una URL.

Ejemplo:

https://sitio.com/search?q=<script>alert('XSS')</script>

Solo funciona cuando la víctima hace clic en el enlace.

2. Stored XSS (Persistente)

El código queda guardado en la base de datos.

Ejemplo:

Un atacante comenta:

<script>...</script>

Cada usuario que vea ese comentario ejecutará el script.

Es el tipo más peligroso.

3. DOM-Based XSS

El ataque ocurre completamente en el navegador.

Ejemplo:

document.cookie
document.write()
document.location

La palabra document. suele indicar un ataque basado en el DOM.

¿Cómo reconocer XSS?

Busca cosas como:

<script>
alert(
document.cookie
document.location
document.write(

Si ves JavaScript dentro de una URL o formulario, probablemente sea XSS.

¿Cómo prevenir XSS?

Validación de entrada.
Sanitización de datos.
Escapar caracteres especiales.
Content Security Policy (CSP).
Cookies HttpOnly.
Frameworks modernos que escapan HTML automáticamente.

2. Gestión de sesiones

Cuando inicias sesión, el servidor necesita recordar quién eres.

Para ello utiliza:

Cookies
Tokens de sesión
Bases de datos de sesiones
Cookies

Son pequeños archivos que identifican al usuario.

Hay dos tipos:

Cookies de sesión

Desaparecen al cerrar el navegador.

Ejemplo:

Banco
Correo
Campus virtual
Cookies persistentes

Permanecen días o meses.

Ejemplo:

"Recordarme"

3. Session Hijacking (Secuestro de sesión)

El atacante roba la cookie o el token de sesión.

Entonces puede hacerse pasar por la víctima sin conocer la contraseña.

Ejemplo:

Usuario inicia sesión

↓

El atacante roba la cookie

↓

La usa en su navegador

↓

Ya está autenticado
Session Prediction

Si los tokens son fáciles de adivinar:

Sesion001
Sesion002
Sesion003

Un atacante puede predecirlos.

Por eso deben ser totalmente aleatorios.

4. Cross-Site Request Forgery (CSRF o XSRF)

¿Qué es?

Es un ataque donde el atacante aprovecha que el usuario ya inició sesión en un sitio para obligarlo a realizar acciones sin darse cuenta.

La víctima ejecuta una acción sin saberlo.

¿Cómo funciona?

Supongamos:

Estás conectado a tu banco.
Sin cerrar sesión, visitas una página maliciosa.

Esa página envía una petición como:

Cambiar contraseña

o

Transferir dinero

o

Cambiar email

El navegador envía automáticamente la cookie del banco.

El banco cree que la solicitud es legítima.

Ejemplo de CSRF

Estás conectado al banco.

Luego visitas:

sitio-malicioso.com

Ese sitio envía:

POST

Cambiar email

Nuevo email:
hacker@gmail.com

Como tu navegador ya tiene la cookie del banco, el banco acepta la solicitud creyendo que fuiste tú.

¿Cómo prevenir CSRF?

Tokens CSRF únicos en cada formulario.
Pedir la contraseña actual para cambios importantes.
Autenticación de dos factores (2FA).
Cookies con atributo SameSite.
Tokens de sesión aleatorios.
