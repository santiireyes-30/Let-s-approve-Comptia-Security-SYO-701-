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
