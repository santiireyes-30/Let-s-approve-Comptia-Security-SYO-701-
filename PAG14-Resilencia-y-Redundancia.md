## Resiliencia & Redundancia en ciberseguridad y Importancia en la Arquitectura de Seguridad

Resiliencia: capacidad de una organización para seguir funcionando y recuperarse rápidamente ante ciberataques o fallos técnicos.
Redundancia: tener sistemas, equipos o procesos de respaldo para evitar interrupciones si falla el sistema principal.

La sección se enfoca en cómo mantener la disponibilidad y recuperación de los sistemas mediante:

- Alta disponibilidad: uso de balanceo de carga, clustering y redundancia en servidores, energía, conexiones y proveedores.
- Redundancia de datos: uso de tecnologías como RAID para proteger la información.
- Planificación de capacidad: asegurar que personal, tecnología e infraestructura soporten momentos de alta demanda.
- Energía para centros de datos: utilización de generadores, UPS/SAI y distribución eléctrica redundante.
- Copias de seguridad: backups locales y externos, cifrado, snapshots, replicación y recuperación.
- BCDR (Business Continuity and Disaster Recovery): planes para mantener el negocio operativo durante incidentes o desastres.
- Sitios redundantes: sitios calientes, tibios y fríos, además de multicloud y dispersión geográfica.
- Pruebas de resiliencia: ejercicios de simulación, failover y pruebas de recuperación.

Idea principal
Las organizaciones necesitan sistemas redundantes y planes de recuperación para garantizar continuidad operativa, disponibilidad de datos y rápida recuperación ante fallos o ataques.

## Alta Disponibilidad

En las organizaciones modernas, donde los servicios deben funcionar casi sin interrupciones.

La alta disponibilidad busca minimizar el tiempo de inactividad utilizando:

- Equilibrio/Balanceo de carga (Load Balancing): distribuye las solicitudes entre varios servidores para evitar sobrecargas y mejorar el rendimiento. Una “solicitud” (request) es cuando un usuario o dispositivo le pide algo a un servidor.

Ejemplos:

Entrar a una página web.
Iniciar sesión.
Ver un video.
Descargar un archivo.
Consultar una API.

Por ejemplo:

10.000 personas entran a Instagram.
Cada persona genera muchas solicitudes:
cargar fotos,
enviar mensajes,
actualizar historias,
etc.

Si todo eso fuera a un solo servidor, se saturaría.
Entonces entra el load balancer (balanceador de carga):

Usuario → Load Balancer → Servidor 1
                         → Servidor 2
                         → Servidor 3

El balanceador reparte las solicitudes entre varios servidores para que ninguno colapse.

- Clustering: agrupa varios sistemas o servidores para mantener el servicio activo incluso si uno falla.
Ejemplo simple:

Supón que un banco tiene:

Servidor A
Servidor B

Ambos están en un cluster.

Si el servidor A falla:

el servidor B sigue funcionando,
los usuarios casi ni notan la caída.

Eso es alta disponibilidad.

- Redundancia: duplicación de componentes críticos como fuentes de energía, conexiones de red, servidores, servicios y proveedores. Es Decir para crear una infraestructura de alta disponibilidad,
hay que incorporar redundancia a los diseños instalando o añadiendo varias fuentes de alimentación, conexiones de red, servidores, servicios de software o proveedores de servicios al diseño de la arquitectura.

- Multicloud: uso de múltiples proveedores cloud para evitar depender de un solo servicio y mejorar la continuidad operativa. Sirve para distribuir nuestros datos, aplicaciones y servicios en varios entornos basados en la nube como forma
adicional de redundancia. Mediante la implementación de una arquitectura de múltiples nubes, puede mitigar el riesgo de un único punto de fallo, ya que si uno de sus proveedores de nube experimenta una interrupción, la carga de trabajo de su organización
se puede transferir rápidamente a otro proveedor de nube con interrupciones mínimas en sus operaciones.

También debemos tener en cuenta el concepto de uptime, medido en porcentajes:

99.999% (“cinco nueves”) ≈ solo 5 minutos de caída al año.
99.9999% (“seis nueves”) ≈ unos 31 segundos de caída anual.

Idea principal

La alta disponibilidad se logra diseñando arquitecturas resilientes con balanceo de carga, clustering, redundancia y multicloud para garantizar continuidad del servicio incluso ante fallos, mantenimiento o ataques.

## Redundancia de Datos

RAID: Son sistemas usados para crear redundancia de datos, mejorar el rendimiento y evitar la pérdida de información en servidores y empresas.

Un RAID combina varios discos físicos en un solo sistema lógico. Los tipos principales son:

RAID 0 (striping): divide los datos entre varios discos para aumentar la velocidad, pero no tiene redundancia. Si un disco falla, se pierde todo.
RAID 1 (mirroring): crea una copia exacta de los datos en dos discos. Si uno falla, el otro sigue funcionando.
RAID 5 (striping con paridad): distribuye datos y paridad entre al menos 3 discos. Permite reconstruir información si falla un disco.
RAID 6 (doble paridad): parecido al RAID 5, pero soporta la falla de hasta 2 discos gracias a una doble paridad.
RAID 10 (1+0): combina RAID 1 y RAID 0 para obtener velocidad y redundancia al mismo tiempo.

RAID es una forma de usar varios discos duros juntos para:

mejorar la velocidad,
proteger datos,
o ambas cosas.

Por ejemplo:

RAID 0 → más velocidad.
RAID 1 → copia espejo para protección.
RAID 10 → velocidad + protección.

RAID 10 → velocidad + protección.

Cuando se habla de “velocidad”, se refieren a:

leer archivos más rápido,
guardar datos más rápido,
cargar sistemas y bases de datos más rápido.

Ejemplo:
si un servidor tiene muchos discos trabajando juntos en RAID, puede:

abrir archivos más rápido,
responder más rápido,
manejar más usuarios al mismo tiempo.

También debemos tener en cuenta los siguientes conceptos como:

Resistente a fallos: puede seguir funcionando usando copias espejo.
Tolerante a fallos: mantiene operaciones incluso si falla hardware.
Tolerante a desastres: protege los datos ante fallos graves mediante copias completas.

La idea principal es que los RAID ayudan a mejorar la disponibilidad, la seguridad y la continuidad de los sistemas empresariales evitando pérdida de datos y reduciendo el tiempo de inactividad.

## Planificación de la capacidad

La planificación de la capacidad es un proceso estratégico que ayuda a una organización a prepararse para futuras demandas de forma eficiente y rentable. Se centra en cuatro áreas principales: personal, tecnología, infraestructura y procesos.

Personal: analiza las habilidades y cantidad de empleados actuales y futuras necesidades de contratación, capacitación o reducción de personal. Por ejemplo, contratar empleados temporales en épocas de alta demanda.
Tecnología: evalúa si el hardware y software actuales soportarán el crecimiento esperado. También considera el uso de servicios en la nube para aumentar o reducir capacidad según la demanda.
Infraestructura: planifica los espacios físicos y recursos necesarios, como oficinas, centros de datos, energía y refrigeración. Busca optimizar el uso del espacio y recursos disponibles.
Procesos: mejora y automatiza flujos de trabajo para soportar cambios en la demanda. Por ejemplo, automatizar la creación masiva de cuentas de usuario para nuevos empleados.

El objetivo de la planificación de la capacidad es garantizar que la organización pueda crecer, adaptarse a nuevas demandas y mantener operaciones eficientes tanto en el presente como en el futuro.

## Alimentacion de Centro de Datos

Los centros de datos necesitan energía constante para que los servidores y sistemas sigan funcionando.
Existen 5 problemas eléctricos principales:

  - Sobretensión (surge): pequeño aumento de voltaje.

  - Pico (spike): aumento muy fuerte y repentino de voltaje.

  - Caída (sag): pequeña disminución de voltaje.

  - Subtensión (brownout): reducción grande y prolongada de voltaje.

  - Pérdida total de energía (blackout): corte completo de electricidad.
  
Para proteger los sistemas se usan varias tecnologías:

1. Acondicionador de línea (Line conditioner)
Corrige pequeñas variaciones de voltaje.
Mantiene energía “limpia” y estable.
Protege el hardware de daños.

2. UPS o SAI (Sistema de Alimentación Ininterrumpida)
El UPS no viene incluido con las computadoras, ni de escritorio ni portátiles. Es un accesorio externo que se compra por separado. Su función principal es mantener el equipo encendido
y protegerlo ante apagones o fluctuaciones de voltaje.

Tiene baterías de respaldo.
Mantiene los equipos encendidos unos minutos cuando se corta la luz.
También actúa como acondicionador de línea.
Normalmente dura entre 15 y 60 minutos.

3. Generadores
Producen electricidad cuando falla la red principal.
Pueden funcionar por horas o días.
Tipos:
Portátiles a gasolina.
Permanentes (diésel, propano o gas natural).
Inversores con baterías.

4. PDC (Power Distribution Center)
Distribuye la energía dentro del centro de datos.
Equilibra cargas y protege circuitos.
Se conecta con UPS y generadores.

Funcionamiento típico en un centro de datos:
1. Se corta la luz.
2. El UPS mantiene los servidores encendidos.
3. En 30–60 segundos arrancan los generadores.
4. El PDC distribuye la energía del generador a todos los sistemas.

Objetivo:
Evitar apagados inesperados.
Proteger hardware y datos.
Mantener servicios y servidores siempre operativos.

## La importancia de las copias de seguridad de datos 

Principalmente para evitar pérdidas de información por errores, fallos o desastres. Una copia de seguridad consiste en crear duplicados de los datos para poder recuperarlos si ocurre algún problema.

Se explican dos tipos principales:

Copias de seguridad in situ: se almacenan en el mismo lugar físico que los sistemas originales.
Copias externas (offsite): se guardan en otra ubicación geográfica o en la nube para protegerse de incendios, inundaciones o ataques.

También se destaca que la frecuencia de las copias depende de cuánto dato esté dispuesta a perder una organización. Esto se relaciona con el RPO (Recovery Point Objective), que define el máximo de información que puede perderse.

El texto recalca la importancia del cifrado:

Datos en reposo: cifrados mientras están almacenados.
Datos en tránsito: cifrados mientras se transfieren por la red.

Luego se explican las instantáneas (snapshots), que capturan el estado de los datos en un momento específico y sólo guardan los cambios realizados desde la instantánea anterior, siendo más rápidas y eficientes que una copia completa.

También se habla de la recuperación de datos, que incluye:

elegir la copia correcta,
restaurar los datos,
validar su integridad,
probar el proceso,
documentar lo ocurrido.

Después se explica la replicación, que mantiene los datos sincronizados en dos lugares al mismo tiempo para garantizar continuidad sin interrupciones.

Finalmente, se describe el journaling (registro en diario), que guarda un historial detallado de todos los cambios realizados en los datos, útil para auditorías, cumplimiento normativo y recuperación precisa.

En resumen, una buena estrategia de backup combina:

copias locales y externas,
frecuencia adecuada,
cifrado,
snapshots,
recuperación probada,
replicación,
journaling,

todo con el objetivo de garantizar la disponibilidad, integridad y continuidad de los datos de una organización.

## La continuidad de operaciones busca que una empresa pueda seguir funcionando y recuperarse ante incidentes o desastres.

Hay dos conceptos principales:

BCP (Business Continuity Plan / Plan de Continuidad del Negocio):
Son los planes y procesos para responder a eventos que interrumpen el negocio, como ataques ransomware, caída de servicios, protestas, problemas con pagos online, etc.
DRP (Disaster Recovery Plan / Plan de Recuperación ante Desastres):
Es una parte del BCP enfocada específicamente en desastres graves, como incendios, inundaciones, huracanes o terremotos, y en cómo restaurar operaciones rápidamente.
- Si se trata de un incidente, será un problema de continuidad de la actividad (BCP).
- Si es un desastre, será un problema de recuperación(DRP).

El objetivo es mantener la empresa operativa usando:

sistemas de respaldo,
servidores en la nube,
personal distribuido en distintas regiones,
proveedores secundarios o terciarios,
y procedimientos previamente definidos.

La alta dirección es responsable de crear y apoyar estos planes, junto con un comité formado por diferentes áreas de la empresa (TI, seguridad, legal, comunicaciones, etc.).

La diferencia principal es:

BCP → responde a incidentes o interrupciones generales.
DRP → responde específicamente a desastres.

Ahora bien, otra parte clave de un buen plan de continuidad de la actividad es definir el alcance del propio plan. De lo contrario, podría enfrentarse a una ampliación del ámbito de aplicación.

Así que, recuerda, cuando se trata del plan de continuidad de las operaciones, vas a tener dos partes principales. Uno será su plan de continuidad de negocio, o plan BC, y el
segundo será su plan de recuperación de desastres, o DRP. Cuando se trata de su plan de continuidad de negocio, recuerde que se refiere a los planes y procesos que se utilizan
para su respuesta a un evento perturbador. Pero cuando se trata de un plan de recuperación en caso de catástrofe, se está hablando específicamente de los planes y procesos
que se van a utilizar para responder a una catástrofe determinada. Esa es realmente la mayor diferencia entre un plan de continuidad de negocio y un plan de recuperación
de desastres, porque en uno nos ocupamos de incidentes y problemas, y en el otro, de desastres.

## Consideraciones de Sitios Redundantes

La continuidad de operaciones busca que una empresa siga funcionando aunque ocurra un problema o desastre.
Para eso se usan sitios redundantes, que son lugares de respaldo donde se pueden mover las operaciones si el sitio principal falla.

Tipos de sitios redundantes
1. Hot Site (sitio caliente)

Es un sitio totalmente preparado y funcionando en todo momento.

Tiene servidores, internet, escritorios, computadoras y datos actualizados.
Permite cambiar las operaciones casi instantáneamente.
Tiene muy poco tiempo de inactividad.
Es el más caro porque necesitas “duplicar” casi todo.

Ejemplo:
Si tu empresa usa servidores en AWS en varias regiones, una región puede tomar el control inmediatamente si otra falla.

2. Warm Site (sitio templado)

Es un sitio parcialmente preparado.

Tiene edificio, energía e internet.
Pero faltan algunos equipos o configuraciones.
Puede estar operativo en horas o pocos días.
Más barato que un hot site.

Ejemplo:
La empresa tiene oficinas listas, pero debe instalar laptops y teléfonos cuando ocurra el desastre.

3. Cold Site (sitio frío)

Es básicamente un lugar vacío de respaldo.

Puede tener mesas, sillas y electricidad básica.
No tiene servidores ni red configurada.
Recuperarse puede tardar semanas o meses.
Es el más barato.

Ejemplo:
Un edificio alquilado que solo se usaría si la sede principal se destruye.

4. Mobile Site (sitio móvil)

Es un centro portátil.

Puede ser un camión, tráiler o carpa.
Lleva servidores, internet, energía y equipos.
Se transporta al lugar necesario.

Ejemplo:
El ejército usa centros móviles para operar después de terremotos o guerras.

5. Virtual Site (sitio virtual)

Es el enfoque moderno usando la nube.

Se basa en AWS, Azure o Google Cloud.
Los servicios están replicados en varias regiones.
Escala rápido y es más flexible.
Reduce costos comparado con tener edificios físicos duplicados.

Ejemplo:
Si un servidor en una región de AWS falla, otra región toma el control automáticamente.

Diversidad de plataformas

Consiste en usar tecnologías diferentes para evitar un único punto de fallo.

Ejemplo:

Sitio principal: equipos Cisco.
Sitio redundante: equipos Juniper.

Así, si aparece una vulnerabilidad grave en Cisco, el sitio secundario podría seguir funcionando.

Idea clave

Los sitios redundantes permiten mantener la empresa funcionando ante:

incendios,
inundaciones,
ataques ransomware,
cortes eléctricos,
fallos de internet,
desastres naturales.

Mientras más rápido quieras recuperarte:

más caro será el sistema.

Por eso:

Hot site = recuperación rápida + caro.
Cold site = recuperación lenta + barato.

## Pruebas de Resiliencia y Recuperación

Las pruebas de resiliencia y recuperación sirven para comprobar si una organización puede:

resistir ataques o fallos,
seguir funcionando,
y recuperarse rápidamente después de un desastre.

Son como “simulacros” para preparar a la empresa ante:

ransomware,
cortes eléctricos,
incendios,
caídas de servidores,
desastres naturales,
violaciones de datos.

Tipos principales de pruebas

1. Tabletop Exercise (ejercicio de mesa)

Es una simulación teórica. Un ejercicio de simulación es un debate basado en un escenario simulado entre las principales partes interesadas para evaluar y mejorar la preparación y la respuesta de la organización ante una situación específica
de emergencia o crisis sin necesidad de desplegar realmente sus recursos.

Los responsables se reúnen y discuten qué harían ante un incidente.
No se usan sistemas reales.
Solo se analiza el plan y la toma de decisiones.

Los tableros también se consideran una forma de creación de equipos, ya que todas las partes interesadas y sus equipos van a trabajar juntos para intentar resolver la catástrofe hipotética o las actividades maliciosas que se están inyectando en ese escenario dado.

Ejemplo:
“Un atacante comprometió el controlador de dominio. ¿Qué hacemos?”

Cada equipo explica:

cómo respondería,
qué acciones tomaría,
y se detectan errores o debilidades en el plan.

Barato y útil para entrenar equipos.

2. Failover Test (prueba de conmutación por error)

Se prueba el cambio de un sistema principal a uno de respaldo.

Ejemplo:

El centro de datos de EE.UU falla.
Se intenta mover todo al centro secundario.

Objetivo:

comprobar que el sitio redundante realmente funciona.

Generalmente:

Requiere más tiempo, más recursos, y planificación.

3. Simulation (simulación)

Es un entorno virtual más realista.

Por ejemplo, con nuestras modernas infraestructuras basadas en la nube, podemos crear una versión virtual o simulada de nuestra red corporativa dentro de la nube y hacer que un equipo rojo ataque esa red, mientras que nuestros defensores, 
conocidos como el equipo azul, intentan detectar los ataques del equipo rojo y utilizar sus técnicas de respuesta a incidentes para aislar a los atacantes de la red y eliminar los sistemas infectados de esa red simulada. Se recrea una red o infraestructura.

Permite probar:

herramientas,
personal,
procesos,
respuesta real ante ataques.

Muy útil para SOC y ciberseguridad.

4. Parallel Processing (procesamiento paralelo)

Consiste en ejecutar:

el sistema principal,
y el sistema secundario
al mismo tiempo.

Objetivo:

verificar que el sistema de respaldo puede manejar las operaciones correctamente.

Se usa para:

alta disponibilidad,
recuperación,
pruebas de estabilidad.
Idea principal

No basta con:

“tener un plan”.

También hay que:

probarlo,
actualizarlo,
practicarlo constantemente.

Porque un plan no sirve si falla durante una emergencia real.

