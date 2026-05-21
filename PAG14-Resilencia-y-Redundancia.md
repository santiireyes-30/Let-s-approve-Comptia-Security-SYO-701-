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

## 
