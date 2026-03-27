# Data Protection

La protección de datos es el proceso de resguardar la información frente a pérdida, robo o alteración, garantizando los tres pilares de la seguridad:

- Confidencialidad, Integridad y Disponibilidad (CIA)

Aspectos clave:

 Clasificación de datos: sensibles, confidenciales, públicos, privados, críticos

 Roles: propietario, controlador, procesador, custodio y administrador

Estados de los datos:

  - En reposo

  - En tránsito

  - En uso

Métodos de protección:

  - Cifrado

  - Hashing

  - Tokenización

  - Enmascaramiento

  - Segmentación

  - Control de accesos

Conceptos importantes:

Soberanía de datos: los datos deben cumplir las leyes del país donde se almacenan

Tipos de datos: financieros, legales, propiedad intelectual, regulados

DLP (Data Loss Prevention):

Estrategia para evitar que datos sensibles:

  - se filtren

  - se pierdan

  - o sean robados

# Clasificación de Datos

La clasificación de datos consiste en organizar la información según:

su valor para la organización y su nivel de sensibilidad

Esto lo define el propietario de los datos.

Objetivo principal... Proteger mejor la información:

🔴 Más sensible → más protección y recursos

🟢 Menos sensible → menos protección

⚠️ Evitar la sobreclasificación, ya que aumenta costos y complejidad innecesariamente.

Clasificación en empresas (5 niveles)

  - Público → sin impacto si se divulga

  - Sensible → impacto leve (ej dato finaciero de una organización)

  - Privado → uso interno (ej: registros personales, información salarial, cualquier otro dato que sólo se utilice dentro de la organización)

  - Confidencial → alto impacto (ej: Contiene elementos como secretos comerciales, propiedad intelectual o PI, código fuente y otros tipos de cosas que afectarán gravemente a la empresa si se revelan)

  - Crítico → extremadamente sensible (ej: tarjetas de crédito)

Clasificación gubernamental (5 niveles):

  - No clasificado (los datos no clasificados suelen poder hacerse públicos, ya sea en general o en virtud de la Ley de Libertad de Información)

  - Sensible pero no clasificado (incluyen cosas como historiales médicos, archivos personales y otros elementos que no perjudicarán a la seguridad nacional si se divulgan, pero que sí afectarían a aquellos cuyos datos se están utilizando en su interior)

  - Confidencial (incluyen datos tales como secretos comerciales, otra información que puede afectar seriamente al gobierno si se divulga sin autorización)

  - Secreto (los datos secretos van a incluir cosas como planes de despliegue militar, posturas defensivas y otra información que podría dañar seriamente la seguridad nacional si se divulga.

  - Alto secreto (Los datos de alto secreto pueden incluir los planos de un sistema de armamento u otra información que dañaría gravemente la seguridad nacional si fuera conocida por quienes no están autorizados para este nivel de información)

A mayor nivel, mayor impacto en la seguridad nacional.

Ciclo de vida de los datos, Los datos deben gestionarse correctamente:

  - Recolección

  - Almacenamiento

  - Retención

  - Eliminación

  - No deben guardarse para siempre.

  - Importante

Se deben definir políticas claras Cumplir con leyes y regulaciones

Determinar cuánto tiempo conservar los datos

Conclusión...

Clasificar bien los datos permite:

  - optimizar recursos

  - mejorar la seguridad

  - cumplir normativas

# Propiedad de los Datos

La propiedad de los datos define quién es responsable de proteger la información en términos de:

  - Confidencialidad

  - Integridad

  - Disponibilidad

  - Privacidad

# Roles principales:

#### Propietario de datos (Data Owner)

  - Rol ejecutivo de alto nivel, responsable de mantener la confidencialidad, integridad, y disponibilidad del activo de información

  - Define clasificación y controles de seguridad (responsable de etiquetar el activo, asegurándose de que está protegido con los controles adecuados)

#### #esponsable del tratamiento (Controller)

  - Decide cómo y para qué se usan los datos

  - Responsable legal ante incidentes

#### Procesador de datos (Processor)

  - Grupo o personas que ejecuta tareas como la recogida, el procesamiento y almacenamiento o el análisis de los datos.

  - Sigue instrucciones del responsable


#### Administrador de datos (Data Steward)

  - Alguien que trabaje para el propietario de los datos y garantiza calidad, clasificación y etiquetado, ej: todos los datos financieros deben etiquetarse  y tratarse como datos finacieros, el papael de administrador de datos sera asegurarse de qu eso ocurra

#### Custodio de datos  (Data custodian)

  - Función que se encarga de gestionar el sistema en el que se almacenan los activos de datos.
  
  - Administra sistemas (ej: IT)

  - Aplica controles: acceso, cifrado, backups las medidas de recuperación y las medidad de recuperación de copias de seguridad que protegen estos datos en función de los requisitos establecidos por el propietario de los datos.

#### Responsable de privacidad 

  - Supervisa datos sensibles (PII, PHI, etc.)

  - Asegura cumplimiento legal y normativo

  - Se encarga en caso de que violen nuestros datos

Punto clave a tener en cuenta

#### El propietario de los datos NO es IT

Debe ser alguien del negocio que entienda los datos (ej: finanzas, desarrollo, etc). IT actúa como custodio, no como dueño

Conclusión y en resumém...

Una correcta asignación de roles permite:

  - mejor seguridad

  - cumplimiento legal

  - gestión eficiente de los datos

# Estado de Datos (Data States)

Los datos pasan por 3 estados principales, y cada uno requiere medidas de seguridad específicas:

## 1. Datos en reposo

Datos almacenados (discos, servidores, bases de datos)

No están en movimiento

Protección:

Cifrado (disco, archivos, bases de datos, etc.)

Control de accesos (ACL)

👉 Son un objetivo común porque están “quietos”

## 2. Datos en tránsito

Datos que se están moviendo por la red (Internet o red interna)

⚠️ Riesgo: interceptación

🔐 Protección:

TLS / SSL

VPN

IPSec

## 3. Datos en uso

Datos que se están procesando (leer, modificar, ejecutar)

⚠️ Son vulnerables porque deben estar descifrados

🔐 Protección:

Controles de acceso

Cifrado a nivel de aplicación

Entornos seguros (enclaves)

🎯 Conclusión

Cada estado tiene riesgos distintos

Es clave aplicar seguridad específica en cada uno

Esto reduce filtraciones y protege la información
