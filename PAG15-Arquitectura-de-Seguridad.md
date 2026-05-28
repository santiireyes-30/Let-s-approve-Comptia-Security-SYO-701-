## Arquitectura de Seguridad

La arquitectura de seguridad es el diseño y organización de la seguridad de una empresa para proteger sus sistemas, redes y datos. Incluye hardware, software, procesos y personas. En otras palabras
Cuando hablamos de se refiere al diseño, la estructura y el comportamiento del entorno de seguridad de la información de una organización.

Temas principales:
On-premise(en las instalaciones) vs nube
On-premise: servidores y sistemas dentro de la empresa.
Nube: servicios alojados en Internet usando proveedores como Amazon Web Services, Microsoft Azure o Google Cloud Platform.

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

Seguridad y arquitectura

La arquitectura de seguridad protege hardware, software, redes, datos y usuarios.
Se estudian tecnologías como:

Virtualización: varias máquinas virtuales dentro de un servidor físico.

Contenedores: aplicaciones ligeras y aisladas.

Serverless: el proveedor administra servidores automáticamente.

Microservicios: aplicaciones divididas en pequeños servicios independientes.

SDN: redes configuradas por software.

IaC (Infrastructure as Code): infraestructura configurada automáticamente con código.
Otros temas importantes

IoT: dispositivos conectados a Internet.

ICS/SCADA: sistemas industriales para fábricas, energía o agua.

Sistemas embebidos: computadoras dedicadas a funciones específicas.

Idea principal
On-premise = más control, pero más mantenimiento y costo.
Cloud = más flexibilidad, escalabilidad y rapidez.
Híbrido = mezcla de ambos para aprovechar ventajas de cada uno.
