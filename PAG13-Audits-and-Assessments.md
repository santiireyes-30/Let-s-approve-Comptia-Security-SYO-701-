## Auditorías y Evaluaciones

las auditorías y evaluaciones son fundamentales para revisar la seguridad, detectar vulnerabilidades y asegurar el cumplimiento de normas como GDPR, HIPAA y PCI DSS.

Auditorías: son revisiones sistemáticas de sistemas, aplicaciones y controles de seguridad para medir su eficacia.

Internas: realizadas por el propio equipo de la empresa.

Externas: hechas por terceros independientes.

Sirven para identificar fallos en políticas y controles, y verificar el cumplimiento normativo.

Evaluaciones: analizan sistemas y riesgos para detectar vulnerabilidades y amenazas antes de implementar cambios importantes.
Pueden ser:

Evaluaciones de riesgos

Evaluaciones de vulnerabilidades

Evaluaciones de amenazas

También mencionamos las pruebas de penetración (pen testing), donde se simulan ataques reales para encontrar fallos explotables en redes o sistemas utilizando herramientas como Nmap y Metasploit.
Además, se explica el concepto de certificación de resultados, que es la confirmación formal y escrita de los hallazgos obtenidos en una auditoría o evaluación.
En resumen, auditorías, evaluaciones y pruebas de penetración ayudan a fortalecer la postura de seguridad de una organización, detectar debilidades y mejorar el cumplimiento y la protección de sus sistemas.

## Auditorías y Evaluaciones internas 

Como procesos clave para mantener la seguridad y el cumplimiento dentro de una organización. Las auditorías internas son revisiones sistemáticas realizadas por el propio equipo de auditoría de la empresa para verificar la eficacia de los controles internos, la seguridad y el cumplimiento de normas y políticas. Se enfocan en aspectos como contraseñas, controles de acceso, seguridad de red y respuesta a incidentes. Por ejemplo, revisan si los empleados tienen únicamente los permisos necesarios según su trabajo y si se respetan principios como el menor privilegio.

También se destaca el concepto de cumplimiento (compliance), que consiste en asegurarse de que la organización siga leyes, regulaciones y estándares de seguridad. Para supervisarlo, muchas empresas cuentan con un comité de auditoría, encargado de supervisar auditorías, controles internos y requisitos legales.

Por otro lado, las evaluaciones internas buscan identificar riesgos y vulnerabilidades técnicas dentro de los sistemas de la organización. A diferencia de las auditorías, estas se centran más en detectar problemas de seguridad antes de implementar nuevos sistemas o cambios importantes.

Las evaluaciones pueden incluir:

Escaneo de vulnerabilidades.
Modelado de amenazas.
Evaluación de riesgos.
Recomendaciones de mitigación.

Por ejemplo, antes de lanzar una nueva aplicación web, el equipo puede analizar amenazas como SQL Injection, XSS o ataques DoS, evaluar el impacto de esas amenazas y proponer mejoras de seguridad.

En conclusión:

Las auditorías internas verifican controles y cumplimiento.
Las evaluaciones internas identifican riesgos y vulnerabilidades.

Ambas ayudan a mejorar la postura de seguridad de la organización y a mantener el cumplimiento continuo de normas y políticas.

## Comité de auditoría 

Normalmente no realiza las tareas técnicas como pentesting o configuración de controles de seguridad. Su función principal es de supervisión y gobierno.

El comité:

- Supervisa que las auditorías se hagan correctamente.
- Revisa informes de seguridad y cumplimiento.
- Evalúa riesgos a nivel organizacional.
- Verifica que la empresa cumpla normativas.
- Da seguimiento a problemas detectados.

Las tareas técnicas las realizan otros equipos:

Pentesting → lo hacen pentesters, red team o consultores de seguridad.
Controles de seguridad → los implementan administradores, ingenieros de seguridad, SOC analysts, etc.
Auditorías técnicas → las hace el equipo de auditoría interna o auditores externos.

El comité recibe los resultados y decide:

Qué riesgos son prioritarios, qué debe corregirse, y si la organización está cumpliendo correctamente.

Ejemplo simple:

El pentester descubre una vulnerabilidad crítica.
El equipo de seguridad la corrige.
El comité revisa el informe y verifica que el problema se haya tratado adecuadamente.

## Proceso de una Evaluación Interna de seguridad para una aplicación.

Primero, el equipo realiza un modelado de amenazas para identificar posibles ataques, como SQL Injection, XSS y ataques DoS.

Luego, llevan a cabo una evaluación de vulnerabilidades usando herramientas automáticas y pruebas manuales para encontrar fallos y debilidades en el código.

Después, realizan una evaluación de riesgos, analizando:

la probabilidad de explotación,
el impacto potencial,
y el costo de implementar medidas de seguridad.

Con base en los resultados, el equipo propone estrategias de mitigación, como:

corregir el código,
agregar controles de seguridad,
o modificar la arquitectura de la aplicación.

El objetivo final es reducir riesgos y prevenir incidentes de seguridad antes de que la aplicación sea lanzada al entorno de producción.

## Como se Realiza una Evaluación Interna de Ciberseguridad

Utilizando listas de comprobación o autoevaluaciones para identificar riesgos y vulnerabilidades dentro de una organización.

Como ejemplo, se utiliza la "Cybersecurity Self-Assessment Checklist" creada por el MCIT, una organización gubernamental. Esta lista contiene preguntas de “sí o no” sobre temas de seguridad y además incluye:

Comentarios, acciones correctivas, responsables asignados, y seguimiento de tareas.

Cada acción debe asignarse a una persona o equipo específico para asegurar que se implementen las correcciones necesarias.

La evaluación debe involucrar a distintas áreas de la organización, como:

Administración, personal de TI, y profesionales de ciberseguridad.

Entre las preguntas evaluadas se encuentran:

si hubo incidentes de ciberseguridad recientes,
si existe un plan de respuesta a incidentes,
si hay un plan de continuidad del negocio,
si los dispositivos tienen antivirus actualizado,
y si existe una política de dispositivos móviles.

El objetivo de estas autoevaluaciones es obtener una visión general de la postura de seguridad de la organización para detectar debilidades y reducir riesgos relacionados con la ciberseguridad y la exposición de datos.

### Cómo una organización revisa su propia seguridad internamente para detectar riesgos antes de que ocurra un problema grave.

La idea principal es esta:

Una empresa no espera a ser hackeada para actuar. En cambio, realiza una autoevaluación interna usando una lista de preguntas para revisar si su seguridad está bien organizada o si tiene debilidades.

Esa lista funciona como un “checklist” de ciberseguridad.

Por ejemplo, la organización se pregunta:

¿Tuvimos ataques o incidentes recientemente?
¿Tenemos un plan de respuesta a incidentes?
¿Tenemos un plan de continuidad del negocio?
¿Los dispositivos tienen antivirus actualizado?
¿Existe una política para celulares y laptops personales?

Después de responder:

se anotan problemas encontrados,
se crean acciones correctivas,
y se asigna un responsable para solucionarlos.

El texto también quiere decirte que:

la evaluación no la hace una sola persona,
sino varios equipos juntos:
administración,
TI,
ciberseguridad,
etc.

Porque los riesgos afectan a toda la empresa.

En resumen, el mensaje central del texto es:

Las organizaciones usan autoevaluaciones internas para identificar riesgos, vulnerabilidades y malas prácticas de seguridad antes de sufrir incidentes graves, asignando responsables y acciones para corregir esos problemas.

## Pruebas de Pentesting

Las pruebas de penetración (pentesting o hacking ético) y los distintos tipos que existen para evaluar la seguridad de una organización.

Las pruebas de penetración consisten en simular ataques reales para encontrar vulnerabilidades antes de que sean explotadas por atacantes.

Se describen cuatro tipos principales:

Pruebas de penetración físicas:
Evalúan la seguridad física de la empresa, como puertas, tarjetas de acceso y cámaras. Buscan detectar debilidades que permitan accesos no autorizados.

Pruebas ofensivas (Red Teaming):
Los especialistas intentan atacar y explotar vulnerabilidades activamente, simulando ataques reales para descubrir fallos de seguridad y ayudar a corregirlos.

Pruebas defensivas (Blue Teaming):
Se enfocan en detectar ataques, responder a incidentes y reforzar sistemas para mejorar la capacidad defensiva de la organización.

Pruebas integradas (Purple Teaming):
Combinan equipos ofensivos y defensivos trabajando juntos. El Red Team ataca y el Blue Team intenta detectar y responder, permitiendo mejorar tanto la detección como la defensa.

El objetivo general del pentesting no es causar daño, sino identificar y corregir vulnerabilidades para fortalecer la seguridad de la organización.

## El Reconocimiento 

Es la primera fase de una prueba de penetración (pentest), donde el atacante o pentester recopila información sobre el objetivo antes de intentar explotarlo. Cuanta más información obtenga, mejor podrá planificar el ataque y aumentar sus probabilidades de éxito.

Puntos principales:
El reconocimiento es como un ladrón observando una casa antes de entrar: analiza horarios, seguridad y puntos débiles.
En ciberseguridad, se recopilan datos como:
- Direcciones IP, dominios, servidores, sistemas de seguridad, posibles vulnerabilidades.

Tipos de reconocimiento:
Activo:
El atacante interactúa directamente con el objetivo (por ejemplo, escaneando puertos con Nmap).
Da mucha información, pero puede ser detectado fácilmente.

Pasivo:
El atacante obtiene información sin tocar directamente el sistema (WHOIS, redes sociales, fuentes públicas, etc.).
Es más sigiloso, aunque obtiene menos datos.

Tipos de entornos en pentesting:
Entorno conocido (white box):
El pentester recibe mucha información previa del sistema (IPs, diagramas, credenciales).
Se enfoca más en encontrar vulnerabilidades profundas.

Entorno parcialmente conocido (gray box):
El pentester recibe información limitada y debe descubrir el resto mediante reconocimiento.

Entorno desconocido (black box):
El pentester casi no recibe información.
Debe comenzar desde cero, como un atacante real externo.

## Idea clave:
El reconocimiento es fundamental porque permite identificar vulnerabilidades, planificar ataques y reducir el riesgo de fallar o ser detectado durante una prueba de penetración.

## Pasos de Pentest

Un pentest incluye reconocimiento, escaneo y explotación de vulnerabilidades. Para ello se usan herramientas como Nmap y Metasploit.

Nmap se utiliza para:
Descubrir dispositivos en la red.
Escanear puertos abiertos.
Identificar servicios y posibles vulnerabilidades.
Metasploit es un framework de pentesting que permite:
Realizar reconocimiento.
Ejecutar exploits.
Hacer tareas de post-explotación.

Metasploit contiene varios módulos:

Exploits: código que aprovecha vulnerabilidades.
Auxiliary: herramientas como escáneres o sniffers.
Post: acciones posteriores al acceso, como persistencia o recopilación de datos.
Payloads: lo que se ejecuta tras explotar una vulnerabilidad (por ejemplo, abrir una shell).
Encoders: ayudan a evitar detección.
Nops: estabilizan cargas útiles.
Evasion: técnicas para esquivar defensas.

sigue este proceso:

Reconocimiento y escaneo
Se usa Nmap para encontrar una máquina vulnerable en la red.
Se identifican puertos y servicios activos.
Identificación de vulnerabilidad
Se detecta un servicio vulnerable (UnrealIRCd).

Uso de Metasploit
Se selecciona un exploit adecuado.
Se configura el RHOST (IP objetivo) y el puerto.
Se elige un payload que determine qué hacer tras explotar el sistema.

Explotación
Se ejecuta el exploit.
Se obtiene acceso remoto al sistema vulnerable.

Post-explotación y sesiones
Una vez dentro, el pentester puede:
Ver archivos.
Crear o eliminar directorios.

Ejecutar comandos.
Metasploit permite manejar múltiples sesiones al mismo tiempo.

Idea principal:
El objetivo del pentesting no es dañar sistemas, sino identificar vulnerabilidades antes que un atacante real. El video busca que entiendas qué hacen herramientas como Nmap y Metasploit y cómo piensa un pentester, no que memorices comandos para el examen.

## La atestación de hallazgos 

Es una validación formal que confirma que una auditoría, evaluación o prueba de penetración realmente se realizó y que los resultados obtenidos son auténticos y confiables.
En pentesting, la atestación sirve para demostrar con evidencia que las vulnerabilidades encontradas existen de verdad. Esto suele requerirse cuando la organización debe cumplir normativas como:

HIPAA
PCI DSS
GLBA
Sarbanes-Oxley Act

La empresa de pentesting puede entregar una carta de atestación, que incluye:

Resumen de hallazgos.
Confirmación de que la evaluación se realizó.
Evidencias y pruebas técnicas.

La diferencia principal entre un reporte y una atestación es que:

El reporte muestra hallazgos y recomendaciones.
La atestación además incluye pruebas y validación formal de que la explotación ocurrió realmente.

Las pruebas pueden incluir:

Logs.
Capturas.
Datos técnicos.
Explicaciones.
Código de explotación.

El texto también explica otros tipos de atestación:

Atestación de software: verifica que el software no fue alterado.
Atestación de hardware: valida la integridad del hardware usando tecnologías como TPM.
Atestación de sistemas: confirma que un sistema cumple estándares de seguridad como:
ISO 27001
SOC 2

Además:

Las auditorías internas usan atestación para validar controles internos y cumplimiento.
Las auditorías externas usan atestación para confirmar información financiera, operativa o regulatoria mediante terceros independientes.
Idea principal

La atestación sirve para generar:

Confianza.
Transparencia.
Responsabilidad.
Evidencia formal de seguridad y cumplimiento.
