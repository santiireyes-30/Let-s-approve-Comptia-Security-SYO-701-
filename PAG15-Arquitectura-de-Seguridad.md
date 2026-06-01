## Arquitectura de Seguridad

La arquitectura de seguridad es el diseño y organización de la seguridad de una empresa para proteger sus sistemas, redes y datos. Incluye hardware, software, procesos y personas. En otras palabras
Cuando hablamos de se refiere al diseño, la estructura y el comportamiento del entorno de seguridad de la información de una organización.

Temas principales:
On-premise(en las instalaciones) vs nube
On-premise: servidores y sistemas dentro de la empresa.
Nube: servicios alojados en Internet usando proveedores como Amazon Web Services, Microsoft Azure o Google Cloud Platform.
Híbrido: mezcla de ambos para aprovechar ventajas de cada uno.

Seguridad en la nube
  - Riesgos como mala configuración, fallas de autenticación, servidores compartidos y puntos únicos de fallo.

Virtualización y contenedores
  - Permiten ejecutar varios sistemas o aplicaciones en un mismo hardware.
  - También tienen riesgos como escape de máquinas virtuales.

Serverless
  - El proveedor cloud administra los servidores automáticamente y el desarrollador solo se enfoca en el código.

Microservicios
  - Aplicación dividida en pequeños servicios independientes.

Arquitectura de red
  - Uso de separación física o lógica, subredes y segmentación para mejorar seguridad.

SDN (Software Defined Networking)
  - Redes administradas por software para mayor automatización y control.

IaC (Infrastructure as Code)
  - Infraestructura configurada automáticamente mediante código.

Arquitecturas centralizadas vs descentralizadas
  - Centralizada: todo depende de un punto principal.
  - Descentralizada: recursos distribuidos para mayor resiliencia.

IoT (Internet of Things)
  - Dispositivos conectados a Internet que intercambian datos.

ICS y SCADA
  - ICS: Sistemas de control industriales usados en fábricas, energía, agua y transporte. Se utilizan en la producción industrial, como la fabricación,
    el transporte, la energía y los servicios públicos.
  - SCADA: significa control de supervisión y adquisición de datos, y es un subconjunto de ICS. Los sistemas SCADA se utilizan para controlar
    y supervisar procesos físicos como la transmisión de electricidad, el transporte de gas, la distribución de agua y la recogida de aguas residuales.
    
Sistemas empotrados/
  - Computadoras integradas dentro de dispositivos específicos. cumple 1 o 2 funciones específicas, Este sistema forma parte de un dispositivo completo que incluye también componentes eléctricos y mecánicos.

En resumen, esta sección explica diferentes modelos y tecnologías utilizadas para diseñar infraestructuras seguras y resilientes.

A continuación, vamos a hablar de la seguridad en la nube y, en esa lección, abordaremos todas las consideraciones de seguridad al utilizar la nube, incluidas las vulnerabilidades
de los servidores físicos compartidos, la seguridad inadecuada de los entornos virtuales, la gestión del acceso de los usuarios, la falta de medidas de seguridad actualizadas, los puntos únicos
de fallo, las prácticas deficientes de autenticación y cifrado, las políticas poco claras y los restos de datos.

## Implementación Local Frente a la Nube

On-premise: la empresa tiene sus propios servidores físicos en su edificio.
Ellos mismos manejan hardware, energía, seguridad y mantenimiento.

Cloud (nube): los servidores están en centros de datos de empresas como Amazon Web Services, Microsoft Azure o Google Cloud Platform.
Se accede por Internet y el proveedor gestiona gran parte de la infraestructura.

Modelo híbrido: combina servidores locales con servicios en la nube.

#### Conceptos importantes

Matriz de responsabilidades: divide qué seguridad y mantenimiento hace el proveedor cloud y qué hace el cliente.

Proveedores externos: agregan herramientas de seguridad, monitoreo o administración. Por ejemplo, Cloud Health de VMware proporciona gestión de costes, gobernanza, automatización
y seguridad para entornos multicloud.

Soluciones Hibridas: Las soluciones híbridas combinan servidores locales (on-premise), nube privada y nube pública.
Esto permite mover aplicaciones o datos entre distintos entornos según la necesidad de la empresa.

Ventajas
  - Más flexibilidad.
  - Mejor escalabilidad.
  - Posibilidad de mantener datos sensibles localmente.
  - Uso de la nube para tareas más pesadas o masivas.
Aspectos importantes a considerar
  - Seguridad de datos: proteger información sensible.
  - Cumplimiento normativo: seguir leyes y regulaciones.
  - Interoperabilidad: que todos los sistemas puedan comunicarse entre sí.
  - Costo: que la solución sea rentable.
Ejemplo
Una empresa de salud puede:
  - Guardar datos confidenciales de pacientes en servidores locales por seguridad y regulaciones.
  - Usar la nube para correos electrónicos, análisis de datos o tareas de gran volumen.
Así obtiene:
  - Mayor control y seguridad sobre datos críticos.
  - Escalabilidad y reducción de costos usando la nube para otras funciones.

Soluciones in situ: Las soluciones in situ se refieren a la infraestructura informática que se encuentra físicamente en las instalaciones de una empresa.
La empresa es responsable del mantenimiento del hardware, el software y otros recursos. En una infraestructura local (on-premise), el departamento de TI de la empresa
administra todo internamente. Esto le da a la empresa:

- Control total sobre sus datos.
- Mayor privacidad para información sensible.
- Menor dependencia de proveedores externos.
- Acceso inmediato a los datos y sistemas.

Esto es importante en sectores como el jurídico o salud, donde la información es muy sensible y se necesita acceso rápido y seguro.

Luego, al pasar a la computación en nube, las empresas deben considerar factores importantes como:

seguridad,
disponibilidad,
costos,
escalabilidad,
recuperación de datos,
y administración de la infraestructura.

Escalabilidad: la nube permite aumentar recursos rápidamente.

Alta disponibilidad: La disponibilidad se refiere a la posibilidad de acceder al sistema cuando sea necesario. Los servicios en nube suelen ofrecer una alta disponibilidad
debido a su naturaleza distribuida, lo que significa que pueden seguir funcionando aunque uno de los centros de datos sufra una interrupción. 

Ejemplo: AWS, ofrece acuerdos de nivel de servicio que prometen un porcentaje anual de tiempo de actividad de al menos el 99%. 99% para sus servicios Amazon S3 y Amazon EC2 (Alto Nivel).

Resiliencia: es la capacidad del sistema para recuperarse de los fallos y seguir funcionando. Ejemplo: si un servidor o región falla, otra toma el control.

Costo: la nube evita grandes gastos iniciales, pero el uso continuo puede volverse caro.

Capacidad de Respuesta: La capacidad de respuesta se refiere a la velocidad a la que el sistema puede adaptarse a los cambios en la demanda. Los servicios en la nube tienen una 
gran capacidad de respuesta, lo que permite a las empresas aumentar o reducir rápidamente los recursos en función de las necesidades. Por ejemplo, un sitio de comercio electrónico podría utilizar
la función de autoescalado de Microsoft Azure para gestionar el aumento de tráfico durante una venta. Esto garantiza que su sitio web siga siendo receptivo y proporcione una experiencia fluida al cliente.

Facilidad de despliegue: Los servicios en nube suelen ser más fáciles de implantar que las soluciones in situ. No requieren instalación física y pueden configurarse en cuestión de minutos u horas.
(crear servidores o servicios en la nube es rápido).

Transferencia de riesgo: parte del mantenimiento y la infraestructura quedan a cargo del proveedor. Sin embargo, el cliente sigue siendo responsable de la seguridad de sus datos y aplicaciones.
Por poner un ejemplo, una empresa que utiliza Salesforce transfiere a Salesforce el riesgo del mantenimiento del software CRM y la seguridad de la infraestructura.
Sin embargo, la empresa sigue siendo responsable del acceso de los usuarios, la seguridad y la protección de datos.

Facilidad de recuperación: Los servicios en la nube suelen ofrecer soluciones sencillas de recuperación de datos y copias de seguridad, protegiendo a las empresas de la pérdida de datos.
Una empresa que utilice Dropbox para el almacenamiento en la nube puede recuperar fácilmente los archivos eliminados accidentalmente, protegiéndola de posibles pérdidas de datos.

Parches: muchas actualizaciones las aplica automáticamente el proveedor cloud.

La disponibilidad de parches: Los proveedores de servicios en la nube publican periódicamente parches para corregir vulnerabilidades. Los clientes no tienen que preocuparse
de buscar y aplicar estos parches por sí mismos. Microsoft lanza periódicamente parches para su suite Office 365. Los clientes reciben estas actualizaciones automáticamente,
lo que garantiza que su software esté siempre al día y sea seguro.

La imposibilidad de aplicar parches: A veces, las empresas no pueden aplicar los parches debido a problemas de compatibilidad o a la falta de control
sobre el entorno de la nube. Por ejemplo, es posible que una empresa que utilice una aplicación heredada en la nube no pueda aplicar un parche si no es compatible con
la versión anterior del software que está utilizando.

Poder/Power: Para los clientes, una de las ventajas de la computación en nube es que no tienen que preocuparse por el consumo de energía. El proveedor de servicios en nube
se encarga de toda la infraestructura, incluido el suministro eléctrico. Esto no sólo reduce los costes para el cliente, sino que también elimina la necesidad de gestionar 
los problemas de suministro eléctrico.

Computa/Compute: Computación y computación en nube se refiere a la cantidad de recursos computacionales que un cliente puede utilizar. Esto incluye el número de CPU, la
cantidad de memoria y el tipo y tamaño del almacenamiento. Los proveedores de servicios en la nube ofrecen una gama de opciones informáticas que se adaptan a las distintas necesidades.
Por ejemplo, Amazon Web Services o AWS ofrece una gran variedad de instancias de computación, desde instancias pequeñas y de bajo coste para tareas sencillas hasta instancias
de alto rendimiento para cargas de trabajo de computación intensiva.

Así que recuerde, la computación en nube ofrece flexibilidad, escalabilidad y rentabilidad, pero las empresas deben tener en cuenta el reparto de responsabilidades, los proveedores externos y los costes corrientes.
Las soluciones locales ofrecen altos niveles de control y seguridad, pero pueden ser caras y difíciles de mantener y ampliar. 
Las soluciones híbridas ofrecen flexibilidad y control, pero las empresas deben tener en cuenta la seguridad de los datos, la conformidad, la interoperabilidad y el coste.
Las consideraciones clave a la hora de elegir una solución son la disponibilidad, la resistencia, el coste, la capacidad de respuesta, la escalabilidad, la facilidad de implantación, la transferencia de riesgos, la disponibilidad
de parches, la imposibilidad de aplicar parches, la potencia y la informática.

## Seguridad en la Nube

La seguridad en la nube busca proteger datos, aplicaciones y servidores dentro de entornos cloud.
Aunque la nube ofrece flexibilidad y escalabilidad, también tiene riesgos de seguridad.

Principales amenazas en la nube

Servidores físicos compartidos: varios clientes usan el mismo hardware, por lo que una falla podría afectar a otros. Este entorno compartido puede dar lugar a vulnerabilidades si los datos de un usuario se ven comprometidos, afectando
potencialmente a otros usuarios del mismo servidor. Para mitigar este riesgo, los proveedores de la nube deben implantar mecanismos de aislamiento sólidos, como la protección del hipervisor y el multi-tenancy seguro,
para garantizar que las actividades en un entorno virtual no afecten a los demás. El escaneo periódico de vulnerabilidades y la aplicación de parches también pueden ayudar a identificar y corregir posibles brechas de seguridad.

Seguridad débil en máquinas virtuales: puede permitir accesos no autorizados o robo de datos. La virtualización es la piedra angular de la computación en nube. Sin embargo, una seguridad inadecuada en el entorno virtual puede
dar lugar a accesos no autorizados, violaciones de datos y otros incidentes de seguridad. Es crucial implantar medidas de seguridad sólidas en las máquinas virtuales. Esto incluye plantillas de máquinas virtuales seguras,
actualización y parcheado periódicos de las máquinas virtuales y supervisión de las máquinas virtuales para detectar actividades inusuales. Además, la segmentación de la red puede ayudar a aislar las máquinas virtuales entre sí, reduciendo
el riesgo de movimiento lateral por parte de los atacantes.

Mala gestión de usuarios/Gestión de los accesos de los usuarios: contraseñas débiles o permisos excesivos o falta de supervisión de la actividad de los usuarios. Es esencial aplicar políticas estrictas de control de acceso.
Esto incluye la aplicación de políticas de contraseñas seguras, el uso de autenticación multifactor, la limitación de permisos de usuario basada en el principio del menor privilegio y la supervisión de las actividades de los usuarios para 
detectar cualquier comportamiento sospechoso.

Falta de medidas de seguridad (actualizaciones y parches): deja sistemas vulnerables a ataques. incluye mantener parcheados el software y los sistemas, revisar y actualizar periódicamente las políticas de seguridad y mantenerse informado sobre 
las últimas amenazas y las mejores prácticas de seguridad.

Punto único de fallo: si un recurso crítico falla, puede afectar todo el servicio. Los servicios en nube suelen depender de recursos o procesos específicos. Si estos fallan, puede producirse un corte completo del sistema que afecte a todos los usuarios.
Implantar procedimientos de redundancia y conmutación por error puede ayudar a evitar un único punto de fallo. Esto incluye el uso de varios servidores, centros de datos o proveedores en la nube, y la comprobación periódica
de los procedimientos de conmutación por error para garantizar que funcionan como se espera. Qujiere decir que no debes depender de una sola cosa crítica, porque si esa única cosa falla, todo el sistema cae.

Ejemplo simple:

Tienes una sola región de AWS en EE.UU.
Ahí están todos tus servidores y datos.
Si esa región falla → tu aplicación deja de funcionar.

Para evitar eso se usa:

#### Redundancia

Tener copias o recursos duplicados.
Ejemplo:

Otro servidor.
Otra región.
Otro centro de datos.
Incluso otro proveedor cloud.
Conmutación por error (Failover)

Es el cambio automático al sistema de respaldo cuando el principal falla.

Ejemplo:

Tu servidor principal en EE.UU. se cae.
Automáticamente el tráfico pasa al servidor de Europa.
Los usuarios casi no notan la caída.

Autenticación y cifrado débiles: exponen cuentas y datos. las prácticas deficientes de autenticación y cifrado. Una autenticación deficiente puede permitir a usuarios no autorizados acceder a los sistemas en nube.
Mientras que un cifrado débil puede dejar los datos expuestos durante su transmisión o almacenamiento. Las prácticas de autenticación y cifrado sólidas son cruciales.
Esto incluye el uso de autenticación multifactor, algoritmos de cifrado fuertes y prácticas de gestión seguras.

Políticas poco claras: generan errores y malas prácticas de seguridad.

Las políticas poco claras en la seguridad de la nube se refieren a la falta de directrices o procedimientos claros para diversos aspectos de la seguridad, como el manejo de datos, el control de acceso, la respuesta a incidentes, etc.
Sin políticas claras, puede haber confusión e incoherencia en la aplicación y gestión de las medidas de seguridad, lo que puede dar lugar a vulnerabilidades.

Por ejemplo, sin una política clara de tratamiento de datos, los empleados podrían desconocer los procedimientos correctos para almacenar, compartir o eliminar datos, lo que podría dar lugar a filtraciones o violaciones de datos.
Para hacer frente a esto, las organizaciones deben desarrollar políticas de seguridad claras y completas que cubran todos los aspectos de la seguridad en la nube. Estas políticas deben revisarse y actualizarse periódicamente
para reflejar todos los aspectos de la seguridad en la nube y deben comunicarse eficazmente a todas las partes interesadas.

Los programas periódicos de formación y concienciación también pueden ayudar a garantizar que todo el mundo entiende y sigue las políticas. 

Restos de datos: datos eliminados que aún pueden recuperarse.

Los restos de datos se refieren a los datos residuales que quedan tras los procesos de eliminación o borrado. En un entorno de nube, cuando se borran los datos puede que no se eliminen por completo debido a diversas razones,
como procedimientos de borrado inadecuados, políticas de copia de seguridad o problemas técnicos.

Estos restos de datos pueden suponer un riesgo potencial para la seguridad, ya que pueden ser recuperados y explotados por agentes malintencionados.
Para evitar que queden restos de datos, las organizaciones deben aplicar procedimientos seguros de eliminación de datos.

Esto incluye el uso de métodos de eliminación seguros que anulen los datos. Gestionar las copias de seguridad de forma segura y verificar que los datos se han eliminado por completo tras su borrado.

Así que recuerde, la seguridad en la nube es una responsabilidad compartida. Mientras que los proveedores de la nube son responsables de asegurar la estructura subyacente, los usuarios son responsables
de asegurar sus datos y aplicaciones. Los servidores físicos compartidos y los entornos virtuales pueden ser vulnerables a los ataques. Siempre debes implementar mecanismos de aislamiento fuertes y medidas
de seguridad robustas para las máquinas virtuales. La gestión del acceso de los usuarios es crucial. Aplique siempre políticas de contraseñas seguras, utilice autenticación multifactor y limite los permisos de los usuarios.
Si conoce estas vulnerabilidades y sus soluciones, podrá adoptar un enfoque proactivo de la seguridad en la nube y proteger sus valiosos datos y aplicaciones.

Medidas de protección:
- Aislamiento fuerte entre clientes y máquinas virtuales.
- Actualización y parcheo constante.
- Uso de MFA (autenticación multifactor).
- Aplicar el principio de menor privilegio.
- Cifrado fuerte para datos almacenados y transmitidos.
- Redundancia y failover para evitar interrupciones.
- Políticas claras de seguridad y capacitación.
- Eliminación segura de datos.

Idea principal
La seguridad en la nube es una responsabilidad compartida:
El proveedor cloud protege la infraestructura.
El cliente protege sus datos, usuarios y aplicaciones.

## La Virtualización y la Contenedorización

Vamos a cubrir tanto la virtualización como la contenedorización, el beneficio y los riesgos de ambas, algunas vulnerabilidades que amenazan tus máquinas virtuales y cómo asegurarlas.

La virtualización permite crear varias máquinas virtuales dentro de un mismo servidor físico, donde cada una tiene su propio sistema operativo.
Estas máquinas funcionan gracias a un hipervisor, que administra recursos como CPU, RAM y almacenamiento. Es decir, Un hipervisor es un software que permite crear y ejecutar Máquinas Virtuales (VM).

Las máquinas virtuales (VMs) necesitan un hipervisor para funcionar. El hipervisor es el software que:

- crea las VMs,
- reparte recursos (CPU, RAM, disco),
- y hace que varias VMs puedan ejecutarse en un mismo servidor físico.

Ejemplo:
Tienes un servidor físico con:

64 GB RAM
16 CPU

El hipervisor divide esos recursos:

VM1 → 8 GB RAM
VM2 → 16 GB RAM
VM3 → 4 GB RAM

Y cada VM cree que tiene “su propia computadora”.

En contenedores

Los contenedores normalmente NO necesitan hipervisor. Porque:

- no crean sistemas operativos completos,
- usan directamente el sistema operativo del host.

Por eso Docker es mucho más ligero que una VM.

Ejemplo: cuando en un laboratorio Soc te dan una VM ya creada por ellos

Tipos de hipervisores

Tipo 1 (Bare-Metal): Se instala directamente sobre el hardware físico. Es el más rápido y eficiente, ideal para entornos empresariales y servidores.
Algunos ejemplos de hipervisores de tipo 1 son Hyper-V de Microsoft, XenServer de Citrix y ESXi y vSphere de VMware.

Tipo 2 (Alojado): Se ejecuta como una aplicación sobre un sistema operativo ya instalado (ej. Windows, Linux). Es más fácil de usar, pero tiene menor rendimiento

La contenedorización es una alternativa más ligera a las máquinas virtuales. 
En vez de crear sistemas operativos completos, encapsula aplicaciones en contenedores que comparten el mismo sistema operativo del host.
Contenedor: todos comparten el Sistema Operativo del host.

Ventajas de contenedores:
- Más rápidos y ligeros.
- Portables.
- Escalables.
- Aislados entre sí.
- Consistentes en distintos entornos.

Tecnologías populares:

- Docker
- Kubernetes
- OpenShift
- Riesgos y vulnerabilidades

VM Escape: salir de una máquina virtual y atacar el hipervisor. 

El escape de la máquina virtual o VM escape se produce cuando un atacante es capaz de salir de una de estas máquinas virtuales normalmente aisladas y pueden
empezar a interactuar directamente con el hipervisor subyacente. Desde esta posición, el atacante podría migrar a otra máquina virtual alojada en el mismo servidor físico.

Si varias VMs van a compartir el mismo servidor físico, al menos deberían pertenecer al mismo host, nivel de seguridad o segmento de red.
Así, si ocurre un VM Escape, el atacante no saltaría de una VM “poco importante” a otra súper crítica.

Ejemplo:

Mejor práctica:

VM de empleados normales
VM de pruebas internas

Todas juntas en un mismo host porque tienen clasificación similar.

Mala práctica:

VM pública expuesta a Internet
VM con base de datos crítica bancaria

Ambas en el mismo host físico.

Escalada de privilegios: obtener permisos de administrador.

Migración en vivo: posible robo de datos durante el traslado de una VM.

Cuando una máquina virtual necesita "moverse" de un host físico a otro, esto se denomina migración en vivo. Si un atacante consigue introducirse en su red y situarse entre estas dos máquinas físicas, puede
implementar una forma de ataque de intermediario en el que puede capturar los datos que se envían entre dos servidores físicos.

Estos datos no han sido encriptados. Esto puede permitir al atacante violar la confidencialidad. 

¿A que se refiere con "moverse"?

Se transfieren:

RAM de la VM,
estado actual,
procesos,
conexiones,
configuración.

La VM sigue funcionando casi sin interrupción.

¿Dónde está el riesgo de seguridad?
Durante el traslado:

los datos viajan por la red entre hosts físicos.

Si un atacante logra ponerse “en el medio”:

podría espiar tráfico,
capturar datos,
hacer un ataque Man-in-the-Middle.

Especialmente si la migración NO está cifrada.

Reutilización de recursos: exposición de datos residuales. también puede introducir un tipo de vulnerabilidad conocida como vulnerabilidad de reutilización de recursos. Una vulnerabilidad de reutilización de recursos
se produce cuando un recurso del sistema, como la memoria, no se borra o restablece correctamente antes de asignarlo a otra tarea.

### Contenedores

En contenedores, si se compromete el sistema operativo compartido, todos los contenedores pueden verse afectados. Una máquina virtual infectada con malware debería
permanecer aislada de otras máquinas virtuales alojadas en el mismo hipervisor, siempre que las configuraciones de aislamiento se implementen correctamente.

Las conexiones entre una máquina virtual y un recurso compartido, como un servidor de archivos de red, pueden permitir el paso de datos entre diferentes máquinas virtuales, rompiendo
el aislamiento. Por lo tanto, se aconseja minimizar y eliminar cualquier característica innecesaria para apoyar las operaciones, reduciendo la superficie de ataque y las vulnerabilidades potenciales. 
Si un atacante compromete una máquina virtual y la obliga a utilizar una gran cantidad de recursos del servidor físico, puede afectar a otras máquinas virtuales alojadas en el mismo servidor, lo que
podría provocar una denegación de servicio. Para mitigarlo, considere la posibilidad de distribuir sus máquinas virtuales entre varios servidores físicos.

Cómo protegerlas...
- Actualizar hipervisores y sistemas.
- Instalar antivirus y firewalls.
- Usar contraseñas seguras.
- Limitar conexiones innecesarias.
- Aplicar segmentación y aislamiento.
- Cifrar archivos de máquinas virtuales.
- Evitar la proliferación descontrolada de VMs.

Un último concepto 
### Active:
El cifrado del archivo que aloja las máquinas virtuales para garantizar la seguridad y la confidencialidad. Esto protege los archivos de la máquina virtual de accesos no autorizados en el servidor.

## Sin Servidor/Serveless

La computación serverless es un modelo donde el proveedor cloud administra los servidores, bases de datos y parte de la infraestructura, permitiendo que los desarrolladores se enfoquen solo en escribir código.

Aunque se llama “sin servidor”, los servidores sí existen, pero el usuario no los gestiona directamente.

Funciona mediante Funciones como Servicio (FaaS):

- Se ejecutan solo cuando ocurre un evento, y consumen recursos únicamente cuando son necesarias.

Ejemplos:

Amazon Web Services con AWS Lambda
Google Cloud con Google Cloud Functions

Ventajas:

menor costo (se paga solo por uso),
escalado automático,
despliegue rápido,
menos administración de infraestructura.

Riesgos y desafíos:

dependencia del proveedor cloud,
menor flexibilidad para migrar,
mejores prácticas aún en evolución,
fuerte dependencia del servicio del proveedor.

Serverless es útil para aplicaciones escalables y rápidas, pero no siempre es la mejor opción para todos los proyectos.
 
Comparado con SOC:

Evento → Regla Analítica → Alerta → Función Serverless → Respuesta Automática

Así que recuerde, aunque la computación sin servidor ofrece numerosos beneficios, no es una solución única. Es esencial tener en cuenta las necesidades y requisitos de su aplicación específica.
Aunque la tecnología sin servidor elimina muchas complejidades, también introduce nuevos retos, como la dependencia del proveedor y la dependencia crítica del proveedor de servicios.

## Microservicios (Importante conocer las Palabras de las Ventajas)

Los microservicios son una arquitectura de software que divide una aplicación grande en pequeños servicios independientes, donde cada uno realiza una función específica del negocio y puede ejecutarse por separado.

Ejemplo: Netflix utiliza microservicios para gestionar funciones como recomendaciones, registro de usuarios y codificación de video de manera independiente.

Ventajas
Escalabilidad: cada servicio puede ampliarse según la demanda.
Flexibilidad: pueden utilizar distintos lenguajes y tecnologías.
Resiliencia: si un servicio falla, el resto del sistema sigue funcionando.
Despliegue rápido: los servicios pueden actualizarse de forma independiente.

Desafíos
- Mayor complejidad de gestión:

La gestión de múltiples servicios puede resultar compleja. Esto incluye la gestión de la comunicación entre servicios, la coherencia de los datos y las pruebas de sistemas distribuidos.

- Coherencia de datos: más difícil entre múltiples bases de datos. 

La gestión de datos. Cada microservicio puede tener su propia base de datos, lo que puede dificultar el mantenimiento de la coherencia de los datos en algunos servicios.

- Latencia de red por la comunicación entre servicios. 

El aumento de la comunicación entre servicios puede provocar latencia en la red y ralentizar los tiempos de respuesta. Más riesgos de seguridad debido a una mayor superficie de ataque.

- Seguridad:

Con muchos servicios comunicándose a través de una red, aumenta la superficie de ataque a la que tenemos que hacer frente.

Comparación rápida
Monolito: toda la aplicación está unida; un fallo puede afectar a todo el sistema.
Microservicios: la aplicación está dividida en servicios independientes; los fallos suelen quedar aislados.

Así que recuerde, aunque los microservicios ofrecen muchas ventajas, también introducen nuevas complejidades. Por lo tanto, tampoco son una solución única. Es importante tener en cuenta las necesidades
y capacidades específicas de su organización antes de decidirse a adoptar estos estilos arquitectónicos. Sin embargo, cuando se implementan correctamente, los microservicios pueden proporcionar beneficios
significativos en términos de escalabilidad, flexibilidad y resistencia.

Definición para examen:

Los microservicios son una arquitectura que divide una aplicación en servicios pequeños e independientes, permitiendo mayor escalabilidad, flexibilidad y resiliencia.

## Infraestructura de Red

Separación Física vs Separación Lógica

La infraestructura de red es el conjunto de hardware, software y servicios que permiten el funcionamiento de una red. Para mejorar la seguridad, los sistemas pueden separarse de forma física o lógica.

1. Separación Física (Air Gap)

Consiste en aislar completamente un sistema de otras redes, incluyendo Internet, Wi-Fi y Bluetooth.

Ejemplos:

Redes militares con información clasificada.
Sistemas ICS de centrales eléctricas o plantas de agua. Utilizado en infraestructuras críticas, como centrales eléctricas o instalaciones de tratamiento de aguas. Estos sistemas suelen estar protegidos
por Air-Gap para evitar posibles ataques cibernéticos y físicos que podrían provocar daños en el mundo real, Sin embargo no son infalibles.

Ventajas:

Máximo nivel de seguridad.
Muy difícil acceder desde el exterior.

Desventajas:

Más costosa y difícil de gestionar.
No es invulnerable (ejemplo: el malware Stuxnet logró afectar sistemas aislados).

2. Separación Lógica

Consiste en crear divisiones dentro de la misma red utilizando:

Firewalls, VLANs (Redes Locales Virtuales) que controlar el tráfico basondose en Reglas y políticas de acceso.

Ejemplos:

Separar el departamento de RR.HH. del de Marketing mediante VLANs. Segmenta una red lógica dentro de la misma infraestructura física.
Crear una DMZ (subred de pantalla) para servidores expuestos a Internet (zona aislada donde se colocan servidores expuestos a Internet).


Ventajas:

Más flexible.
Más fácil y económica de implementar.

Desventajas:

Menos segura que un Air Gap.
Una mala configuración puede permitir accesos no autorizados.
Para examen
Air Gap (separación física): aislamiento completo de otras redes.
Separación lógica: segmentación mediante firewalls, VLANs y políticas.
Física = más segura.
Lógica = más flexible y fácil de implementar.

Así que recuerde que tanto la separación física como la lógica desempeñan un papel crucial en la infraestructura y la seguridad de la red. La separación física o Air Gapping proporciona un alto nivel de seguridad al aislar
completamente un sistema de otras redes. La separación lógica, aunque no es tan segura como la física, ofrece más flexibilidad y es más fácil de aplicar.

## Redes Definidas Por Software (SDN)

Las SDN (Software-Defined Networks) son una forma moderna de gestionar redes donde el control se centraliza y puede configurarse mediante software.

Su objetivo es hacer que la red sea:

Más flexible.
Más fácil de administrar.
Más automatizada.
Más eficiente.
¿Qué cambia respecto a una red tradicional?

En una red tradicional:

Cada router o switch toma sus propias decisiones.

En una red SDN:

Existe un controlador central que decide cómo debe comportarse toda la red.
Los 3 planos de una SDN

1. Plano de Datos (Data Plane)

Mueve los paquetes de datos.
Se encarga del tráfico real.
Utiliza routers y switches.

Por ejemplo: cuando envías un correo electrónico, el plano de datos de tu red se encarga de trasladar los datos de tu correo desde tu dispositivo al del destinatario.

2. Plano de Control (Control Plane)

Es el "cerebro" de la red.
Decide por dónde debe viajar el tráfico.
Está centralizado en un controlador SDN.

3. Plano de Aplicación (Application Plane)

Contiene las aplicaciones que dan órdenes al controlador.
Permite automatizar y gestionar la red.

Ejemplo sencillo

Imagina una empresa con 100 switches.

Red tradicional:

Debes configurar cada switch por separado.

SDN:

Configuras una sola vez el controlador central.
El controlador envía las reglas a todos los switches automáticamente.

Para examen "SDN (Software-Defined Network)":

Arquitectura de red que separa el control del tráfico del movimiento de datos, permitiendo administrar toda la red desde un controlador central mediante software.

Planos:

Datos: mueve paquetes.
Control: decide rutas y tráfico.
Aplicación: envía instrucciones al controlador.
Relación con un SOC

Las SDN son útiles porque permiten:

Aplicar reglas de seguridad rápidamente.
Segmentar redes automáticamente.
Aislar equipos comprometidos desde un único punto de administración.
Responder más rápido ante incidentes de seguridad.

Así que recuerde, las redes definidas por software son un enfoque transformador de la gestión de redes que separa la red en tres planos distintos: el plano de datos, el plano de control y el plano de aplicación.

- El plano de datos se encarga de mover los paquetes de datos.

- El plano de control decide dónde se envía el tráfico,

- El plano de aplicación alberga las aplicaciones de red que dan  instrucciones al controlador.
