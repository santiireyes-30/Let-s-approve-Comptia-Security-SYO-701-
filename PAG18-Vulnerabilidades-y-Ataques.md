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

Es un ataque en el que un atacante inyecta código JavaScript malicioso en un sitio web vulnerable o de otra manera de decirlo, es un potente exploit que se basa en que su sitio web no realiza
una "validación adecuada de las entradas". Cuando otro usuario visita ese sitio, el navegador ejecuta ese código como si fuera confiable.

Procesos

1. Identificación de una vulnerabilidad de validación de entrada
2. El atacante crea una URL para realizar la inyección de código contra ese sitio web de confianza. Al mismo tiempo, el atacante necesita conseguir que
alguien haga clic en esa URL maliciosamente codificada.
3. El sitio de confianza devolverá una página que contiene el código malicioso inyectado, así como el código normal del sitio.
Esto ocurre una vez que el usuario hace clic en la URL codificada y el sitio de confianza ejecuta el código inyectado.
4. El código malicioso se ejecuta en el navegador del cliente, finalizando así el ataque de secuencias de comandos entre sitios.

Cuando esto ocurre, el código ejecutará el nivel de permiso del sitio de confianza porque el sistema cree que el sitio de confianza envió ese código, lo que técnicamente hizo porque
se inyectó en la respuesta procedente de ese servidor de confianza al navegador del usuario final. Esta es la razón por la que lo llamamos un ataque de scripting entre sitios porque 
el código malicioso va a ser inyectado y servido por el sitio de confianza a sus usuarios.

Ahora bien, esto no es culpa del navegador, sino que se debe a que están diseñados para ejecutar scripts que reciben de sitios de confianza. Así es como está diseñado Internet.

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

- "Solo funciona cuando la víctima hace clic en el enlace".
-  El atacante no modifica realmente la URL de tu servidor, sino que crea una URL especialmente construida que incluye una carga (payload) maliciosa en alguno de los parámetros. Luego intenta que la víctima haga clic en ella.

Ejemplo conceptual

Supongamos que tienes un buscador:

- https://mitienda.com/buscar?q=laptop

El parámetro "q" contiene lo que el usuario busca.

Si la aplicación es vulnerable y no valida ni escapa correctamente ese valor, un atacante puede construir una URL como:

https://mitienda.com/buscar?q=[código malicioso/payload]

Cuando el servidor devuelve la página incluyendo ese contenido sin filtrarlo, el navegador de la víctima puede interpretarlo como código en lugar de texto.

Lenguaje: 

HTML → sirve para insertar elementos en la página.
JavaScript → realiza la acción maliciosa (leer información de la página, modificarla, enviar datos al atacante, etc.).

- No suele usarse SQL aquí, porque SQL Injection es un ataque diferente dirigido a bases de datos.

2. Stored XSS (Persistente)

El código queda guardado en la base de datos.

Ejemplo:

Un atacante comenta:

<script>...</script>

Cada usuario que vea ese comentario ejecutará el script.

Es el tipo más peligroso.

3. DOM-Based XSS

Modelo de objetos de documentos va a explotar el navegador web del cliente utilizando scripts del lado del cliente para modificar el contenido y el
diseño de la página web.

El ataque ocurre completamente en el navegador.

Ejemplo:

document.cookie
document.write()
document.location

La palabra document. suele indicar un ataque basado en el DOM.

¿Cómo reconocer XSS?

Busca cosas como:

script
alert
document.cookie
document.location
document.write

Si ves JavaScript dentro de una URL o formulario, probablemente sea XSS.

¿Cómo prevenir XSS?

Validación de entrada.
Sanitización de datos.
Escapar caracteres especiales.
Content Security Policy (CSP).
Cookies HttpOnly.
Frameworks modernos que escapan HTML automáticamente.

### Consejos para el Exámen

Ahora, para el examen, déjame darte un par de consejos rápidos. En primer lugar, cada vez que usted está buscando en un fragmento de registro o URLs capturadas que tienen la secuencia de comandos
o cualquier tipo de JavaScript dentro de ellos, lo más probable es que va a ser un ataque de secuencias de comandos entre sitios que va a ser la respuesta correcta a esa pregunta.

Y segundo, si ves algo con document dot algo en él, como document dot cookie o document dot right, esto debería decirte que es un ataque basado en DOM, cross-site scripting porque está afectando 
al modelo de objetos de documento de tu navegador. Si tienes en cuenta estos dos consejos, te irá genial en el examen.

2. Gestión de sesiones

Cuando inicias sesión, el servidor necesita recordar quién eres.

Para ello utiliza:

Cookies
Tokens de sesión
Bases de datos de sesiones
Cookies

Son pequeños archivos que identifican al usuario.

Cookie: Una cookie es esencialmente un archivo de texto que se utiliza para almacenar información sobre un usuario cuando visita el sitio web. Esa cookie se creará cuando el servidor envíe por
primera vez la cabecera de respuesta HTTP con esa cookie al cliente. cualquier encabezado de solicitud posterior que envíe el cliente al servidor debe incluir esa cookie con la información más actualizada.

Hay dos tipos: Persistentes y No Persistentes

Las cookies pueden ser persistentes o no persistentes. Ahora bien, una cookie no persistente también se conoce como cookie de sesión.

Las cookies de sesión residen en la memoria y se utilizan durante un periodo de tiempo muy corto. Sin embargo, otras cookies son más persistentes y se almacenan en la caché del
navegador hasta que el usuario las borra o caducan.

Por ejemplo, si mi sitio web utiliza cookies para rastrear sus movimientos y están configuradas para caducar a los siete días, se considerarían cookies persistentes.
Si has terminado tu trabajo hoy, pero vuelves dentro de tres días, la cookie recuerda dónde estabas y te devuelve ese progreso.

Por otro lado, si te vas durante dos semanas, cuando vuelvas, el sistema podría pensar que eres un usuario nuevo porque tus cookies ya han caducado después de estar fuera siete días.

Cuando se trata de cookies, éstas deben estar encriptadas y protegidas, ya que también pueden contener información confidencial.

3. Session Hijacking (Secuestro de sesión)

Tipo de ataque de suplantación de identidad en el que el atacante desconecta un host y luego lo sustituye por su propia máquina suplantando la IP del host original o utilizando algún
otro mecanismo de toma de control.

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

Los ataques de predicción de sesión son simplemente un tipo de ataque de suplantación de identidad en el que el atacante intenta predecir el testigo de sesión para secuestrar su sesión.
Para evitar los ataques de predicción de sesión, los testigos de sesión deben generarse mediante un algoritmo no predecible y deben ser realmente aleatorios.

4. Falsificación de Petición Entre Sitios/Cross-Site Request Forgery (CSRF o XSRF)

¿Qué es?

Es un ataque donde el atacante aprovecha que el usuario ya inició sesión en un sitio para obligarlo a realizar acciones sin darse cuenta. En otros términos es un script malicioso que va a ser alojado
en el sitio de un atacante que puede ser utilizado para explotar una sesión iniciada en otro sitio dentro del mismo navegador web. Para que esto funcione, el atacante necesita convencer a la víctima
para que inicie una sesión con el sitio web objetivo. Una vez que esto ocurre, el atacante puede pasar una petición HTTP al navegador de la víctima y simularla como una acción en el sitio objetivo.

La víctima ejecuta una acción sin saberlo.

¿Cómo funciona?

Para que el ataque tenga éxito deben cumplirse estas condiciones:

✅ La víctima ya inició sesión (por ejemplo, en su banco).
✅ El sitio usa cookies de sesión para autenticar al usuario.
✅ El atacante logra que la víctima visite una página maliciosa.
✅ El sitio web no tiene protección contra CSRF.

Ejemplo bancario

Imagina que tienes dos pestañas abiertas:

Pestaña 1

Banco.com

Ya iniciaste sesión.

El navegador guarda una cookie como:

SESSION_ID=ABCD1234

Pestaña 2

Entras en:

pagina-maliciosa.com

Sin que lo notes, esa página contiene un formulario HTML oculto o un script que envía una solicitud al banco para cambiar tu correo o contraseña.

El navegador, al enviar la petición al banco, adjunta automáticamente la cookie de sesión, porque tú ya estabas autenticado.

El banco interpreta que la solicitud proviene de ti.

Lo peligroso

A diferencia del XSS:

No siempre necesitas hacer clic en un botón.
Basta con visitar una página maliciosa.

El navegador puede enviar la solicitud automáticamente usando elementos HTML ocultos, por ejemplo:

Formularios (<form>)
Imágenes (<img>)
Iframes (<iframe>)
Scripts (<script>)
Objetivos comunes

Un atacante puede intentar:

Cambiar tu contraseña.
Cambiar tu correo electrónico.
Cambiar datos personales.
Realizar una transferencia bancaria.
Agregar un nuevo beneficiario.
Comprar un producto.

Todo utilizando tu propia sesión.

¿Qué NO hace el atacante?

No necesita:

Conocer tu contraseña.
Hackear el servidor.
Romper el cifrado.

Solo aprovecha que ya estás autenticado.

Cómo prevenir CSRF

Los desarrolladores pueden implementar varias medidas:

1. Token CSRF (la protección más importante)

Cada formulario incluye un token único y aleatorio.

Cuando el formulario llega al servidor:

Si el token es válido → se procesa.
Si no existe o es incorrecto → se rechaza.

2. Autenticación de dos factores (2FA)

Para acciones importantes:

Cambiar contraseña.
Transferir dinero.
Cambiar correo.

Se solicita un código adicional.

3. Solicitar la contraseña actual

Antes de cambiar una contraseña, el sistema pide la contraseña vigente.

Así, aunque el navegador envíe la solicitud automáticamente, el atacante no conoce ese dato.

4. Tokens de sesión aleatorios

Los identificadores de sesión deben ser largos e impredecibles para evitar que puedan adivinarse.

#### Consejos de la Sección

Ahora para el examen, recuerde, que si alguien está tratando de conseguir una víctima para llevar a cabo involuntariamente una acción en un sitio web, esto normalmente va a ser una forma
de falsificación de petición cross-site. Esto suele ocurrir intentando que la víctima realice algún tipo de actualización desconocida en su dirección de correo electrónico predeterminada
o cambiando la contraseña de ese usuario, así que tenlo en cuenta para el examen. Si ves que:

- El usuario ya inició sesión.
- El atacante quiere que el usuario realice una acción sin darse cuenta.
- Se habla de cookies, sesiones o cambiar contraseña/correo.

➡️ La respuesta probablemente sea CSRF (Cross-Site Request Forgery).

Truco para recordar

XSS = Ejecutar código.
CSRF = Ejecutar acciones usando una sesión ya iniciada.

## Desbordamiento de Búfer (Overflow Buffer)

¿Qué es un buffer?

Un buffer es un espacio de memoria temporal que un programa utiliza para almacenar datos mientras los procesa.

Ejemplo:

Un vaso de agua arriba de una mesa con capacidad para 16 onzas (representa el buffer).
Si viertes 20 onzas, el agua se derrama/rebalsa y la mesa se va a mojar.
En informática ocurre lo mismo: si un programa recibe más datos de los que su buffer puede almacenar, los datos "se derraman" sobre otras zonas de memoria.

¿Qué es un Buffer Overflow?

Es una vulnerabilidad que ocurre cuando un programa escribe más datos de los que el buffer fue diseñado para almacenar, sobrescribiendo memoria adyacente.

El problema no es únicamente que falle el programa.
El verdadero peligro es que un atacante pueda sobrescribir información crítica y ejecutar código malicioso.

Ejemplo sencillo

Supongamos que una aplicación reserva memoria para guardar un número telefónico.

Buffer:

Capacidad: 8 caracteres

[ ][ ][ ][ ][ ][ ][ ][ ]

Número normal: 5551234

Todo entra correctamente.
Ahora guardamos: 4105551234 (10 dígitos)

El resultado:
Buffer A: 41055512

Buffer B: 34

Los últimos caracteres invaden otro espacio de memoria, eso es un desbordamiento.

¿Por qué es peligroso?

Porque después del buffer existen otras zonas importantes de memoria.

Por ejemplo:

Variables
Direcciones de retorno
Punteros
Funciones

Si el atacante controla qué datos se escriben, puede modificar esas zonas.

La pila (Stack)

La pila es una región de memoria donde un programa guarda información temporal cuando ejecuta funciones.

A continuación mostraremos una estructura e imagen para visualizarlo y que quede una idea mejor

Bottom of Memory
      │
      │
Buffer 2
Local Variable 2
---------------------
New Code (/bin/sh)
---------------------
New Pointer to exec code
---------------------
Function Call Arguments
      │
Top of Memory

Lo primero que confunde es esto:

Bottom of Memory está arriba

Top of Memory está abajo

Parece al revés.

Pero es simplemente la forma tradicional de dibujar la memoria.

En muchas arquitecturas:

las direcciones pequeñas están arriba
las direcciones grandes abajo

y "la pila crece hacia abajo".

Por eso aparece la flecha:

Fill Direction
↓

Es decir:

cada dato nuevo que se guarda ocupa memoria hacia abajo.

2. ¿Qué significa "Primero en entrar, último en salir"?

La pila funciona como una pila de platos.

Pones un plato
Pones otro
Pones otro

Para sacar uno:

sale el último

Nunca sale el primero.

Eso se llama

LIFO

Last In First Out.

3. Ahora imaginemos un programa normal. Supongamos que Word ejecuta una función.

En ella guarda:

variables locales
parámetros
direcciones de retorno de funciones

Ejemplo muy simplificado:

--------------------
Dirección de retorno
--------------------
Variables
--------------------
Buffer
--------------------

4. Ahora llega el atacante

Si el buffer se llena demasiado, tenia disponibilidad de 100 caracteres y termina poniendo 500 caracteres...

AAAAAAAAAAAAAAAAAAAA...

los caracteres comienzan a sobrescribir la dirección de retorno.

¿Qué hace el atacante?

En lugar de escribir texto cualquiera, introduce:

NOP
NOP
NOP
NOP
NOP
Código malicioso
Nueva dirección de retorno

Cuando el programa termina una función debe volver mediante esa dirección.

Pero ahora esa dirección apunta al código del atacante.

Resultado:

Programa →
           dirección modificada →
                                malware
Smashing the Stack

Cuando un atacante sobrescribe la dirección de retorno del Stack para ejecutar su propio código.

Es el ataque clásico de Buffer Overflow.

NOP Sled

Antes del código malicioso se colocan muchas instrucciones NOP.

NOP significa:

No Operation

La CPU simplemente pasa a la siguiente instrucción.

Visualmente:

NOP
NOP
NOP
NOP
NOP
Código malicioso

Si el programa cae en cualquiera de los NOP:

↓

NOP
↓

NOP
↓

NOP
↓

Código malicioso

terminará ejecutando el malware.

Por eso se llama NOP Sled ("trineo NOP"), porque el flujo "se desliza" hasta el payload.

¿Qué busca el atacante?

Principalmente:

ejecutar malware
abrir una shell (/bin/sh en Linux)
ejecutar comandos remotos
escalar privilegios
tomar control del sistema

Mitigación: ASLR

ASLR (Address Space Layout Randomization)

Aleatoriza las direcciones de memoria donde se cargan:

DLL
Stack
Heap
librerías
programas

Antes:

Microsoft Word

Siempre en:

0x12345678

El atacante sabía exactamente dónde atacar.

Ahora con mitigación ASLR, las direcciones cambian constantemente:

Hoy:
0x5FAE1234

Mañana:
0x98BC7821

Luego:
0x2AAE9944

Esto dificulta muchísimo que el atacante adivine dónde está su código o la dirección de retorno.

¿ASLR elimina el problema?

No completamente.

Existen técnicas para evadirlo, como:

Ataques de canal lateral (Side Channel)
Return Oriented Programming (ROP)
Fugas de memoria (Memory Leaks)

Pero ASLR aumenta mucho la dificultad del ataque.

Señales para el examen

Si ves palabras como:

Buffer Overflow
Stack Overflow
Stack Smashing
NOP Sled
Dirección de retorno
Return Address
ASLR

➡️ Están hablando de un ataque de desbordamiento de búfer.

#### Resúmen de Conceptos Vistos en la Sección

| Concepto            | Descripción                                                                                                                                                                                         |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Buffer**          | Espacio temporal de memoria para almacenar datos.                                                                                                                                                   |
| **Buffer Overflow** | Se escriben más datos de los que el buffer soporta.                                                                                                                                                 |
| **Stack**           | Zona de memoria donde se guardan variables y direcciones de retorno.                                                                                                                                |
| **Stack Smashing**  | Sobrescribir la dirección de retorno para ejecutar código malicioso.                                                                                                                                |
| **NOP Sled**        | Cadena de instrucciones NOP que guía la ejecución hasta el malware.                                                                                                                                 |
| **Objetivo**        | Ejecutar código arbitrario (RCE), abrir una shell o tomar control del sistema.                                                                                                                      |
| **Mitigación**      | ASLR (aleatoriza las direcciones de memoria) y prácticas seguras de programación (validación de límites, uso de lenguajes con protección de memoria, compilación con Stack Canaries, DEP/NX, etc.). |

Ahora bien, se trata de un concepto muy técnico y no es necesario comprenderlo en profundidad para este examen de certificación en concreto.

Si más adelante sigues adelante con algunas certificaciones de pruebas de penetración, como el examen CompTIA PenTest+, entonces vas a volver y mirar los desbordamientos
de búfer en una profundidad mucho más técnica. Pero para este examen, sólo tienes que recordar que un desbordamiento de búfer se va a utilizar para poner más datos en la memoria de lo que está
diseñado para contener para que el atacante pueda tratar de conseguir que su código malicioso se ejecute.

Esto se hace en un intento de desbordar el búfer de ese programa no malicioso para que el atacante pueda introducir su programa malicioso en la memoria y permitir que
se ejecute en su lugar. Así que tenlo en cuenta para el examen.
