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

Antes de hablar de los estados de datos debemos tener en cuenta el concepto del Cifrado quien es que convierte los datos legibles en datos codificados y garantiza que, aunque usuarios no autorizados accedan a los datos.
Los datos pasan por 3 estados principales, y cada uno requiere medidas de seguridad específicas:

## 1. Datos en reposo

Los datos en reposo se refieren a cualquier dato almacenado en bases de datos, sistemas de archivos u otros sistemas de almacenamiento, en fin son datos almacenados (discos, servidores, bases de datos), que no están en movimiento es decir que si esta apagada 

Protección:

- Cifrado (disco, archivos, bases de datos, etc.). Los tipos de Cifrados son: 

                                                 - Cifrado de disco completo: Cuando el sistema está apagado, los datos están encriptados, cuando el sistema está encendido y el usuario ha iniciado sesión, los datos se descifran.

                                                 - Cifrado de particiones: Ssólo encripta particiones específicas de un disco duro, dejando otras particiones sin encriptar. Por ejemplo, puedes cifrar la unidad D de tu estación de trabajo porque incluye información de trabajo confidencial a la que no quieres que accedan otras personas que utilicen tu estación de trabajo.

                                                 - Cifrado de archivos: Este método encripta archivos individuales, suele utilizarse cuando hay que proteger archivos específicos. Por ejemplo, cifrar un archivo en tu estación de trabajo que incluya los códigos secretos de tus trucos para GTA.

                                                 - Cifrado de volúmenes: Este método encripta un conjunto de archivos o directorios seleccionados. Al igual que en los ejemplos anteriores, puedes seleccionar y cifrar varios archivos y directorios si optas por el cifrado a nivel de volumen o de carpeta.

                                                 - Cifrado de bases de datos: Este método encripta los datos almacenados en la base de datos. Puede hacerse a nivel de columna, fila o tabla.

                                                 - Cifrado de registros/Record Encryption: Este método encripta campos específicos dentro de un registro de base de datos. Esto podría ser beneficioso cuando varios usuarios acceden a la misma base de datos, pero no todos tienen los mismos derechos de acceso y visualización, por lo que algunos registros quedarían encriptados de esos usuarios.

- Control de accesos (ACL)

Son un objetivo común porque están “quietos”

## 2. Datos en tránsito

Datos que se están moviendo por la red de un lugar a otro (Internet o red interna)

Riesgo: interceptación

Protección:

 - TLS / SSL

 - VPN

 - IPSec

SSL (Secure Socket Layer) y TLS (Transport Layer Security): Son protocolos criptográficos diseñados para garantizar la seguridad de las comunicaciones a través de redes informáticas.

Las VPN o redes privadas virtuales son tecnologías que crean conexiones seguras a través de una red menos segura, como Internet. Garantiza que los datos enviados y recibidos estén encriptados y a salvo de miradas indiscretas.

IPSec o Protocolo de Seguridad de Internet: Este conjunto de protocolos se utiliza para proteger las comunicaciones del protocolo de Internet autenticando y cifrando cada paquete IP en un flujo de datos.

## 3. Datos en uso

se refieren a los datos en proceso de creación, recuperación, actualización o eliminación. En otras palabras, son datos que se procesan activamente (leer, modificar, ejecutar)

Proteger los datos en uso es todo un reto, ya que hay que descifrarlos para poder procesarlos.

Protección:

 - Controles de acceso

 - Cifrado a nivel de aplicación

 - Entornos seguros (enclaves)

Además algunos mecanismos, como el software guard de Intel, son capaces de cifrar los datos mientras existen en la memoria, de modo que un proceso que no sea de confianza no pueda descifrar la información.

Conclusión:

Cada estado tiene riesgos distintos, es clave aplicar seguridad específica en cada uno, esto reduce filtraciones y protege la información

## Tipos de Datos

Los datos son clave en las organizaciones, pero no todos requieren el mismo nivel de protección. Cada tipo tiene riesgos y normativas distintas.

Principales tipos de datos

#### Datos regulados

- Los datos regulados son información controlada por leyes, reglamentos o normas industriales. Esto incluye datos como información de identificación personal, historiales médicos e información de tarjetas de crédito. Las
organizaciones que manejan estos datos deben cumplir e incluir:

 - PII (datos personales: nombre, DNI, dirección)
 - PHI: Es cualquier información sobre el estado de salud, la prestación de asistencia sanitaria o el pago de la misma que pueda vincularse a una persona concreta.(datos de salud)
 - Requieren cumplimiento legal (ej: GDPR, HIPAA)
   
### Secretos comerciales

un tipo de información empresarial confidencial que proporciona a una empresa una ventaja competitiva. Esto puede incluir procesos de fabricación, estrategias de marketing, software propietario
y listas de clientes, pero en si es Información que da ventaja competitiva

están protegidos por ley, y su divulgación no autorizada puede acarrear graves sanciones legales.

Ej: estrategias, procesos, clientes

### Propiedad intelectual (PI)

Creaciones de la mente (software, simbolos, diseños, contenido).

Protegidas por patentes, copyright, marcas registradas y derechos de autor.

### Información legal

La información jurídica incluye cualquier dato relacionado con procedimientos judiciales, contratos o cumplimiento de la normativa.

Este tipo de datos es sensible y requiere altos niveles de protección para mantener la confidencialidad del cliente y cumplir con el secreto profesional.

Contratos, juicios, cumplimiento
Alta confidencialidad

### Información financiera

Incluye datos como: Facturas, transacciones, bancos, documentos fiscales, facturas, etc

Estos datos suelen ser objetivo de los ciberdelincuentes con fines de fraude o usurpación de identidad.

Esta información financiera suele estar sujetada a normativas como la PCI y DSS (que es la Norma de Seguridad de Datos del Sector de Tarjetas de Pago)

### Datos legibles vs no legibles (Datos legibles por humanos y no humanos)

Legibles: documentos de textos y hojas de calculos

No legibles: código binario o máquina, pueden ser mas dificiles de interpretar  y manipular por el ser humano, ya que puede contener información sensible (los datos no legibles por el ser humano son información que requiere una máquina o un programa informático para ser interpretada)

 - Ambos requieren protección
   
### Conclusión...

En conclusión, comprender los distintos tipos de datos y sus requisitos de seguridad asociados es crucial para cualquier organización. Al clasificar los datos correctamente y aplicar las medidas de seguridad adecuadas, las organizaciones pueden proteger sus valiosos activos de datos, cumplir la normativa y mantener la reputación y la confianza con clientes y socios.

### Soberanía de los Datos

La soberanía de los datos significa que los datos están sujetos a las leyes del país donde se almacenan o procesan.
Cada país tiene sus propias normativas de privacidad y protección de datos. Las empresas deben cumplir esas leyes según dónde estén sus datos

### Importancia en la nube

En la nube, los datos pueden estar en distintos países, esto hace más difícil cumplir con todas las regulaciones

#### Consideraciones geográficas

##### Regulaciones diferentes
Ej: GDPR (Europa) → reglas estrictas de privacidad

##### Restricciones de países
Ej: China o Rusia → obligan a almacenar datos dentro del país

##### Riesgos
Multas por incumplimiento

##### Control necesario
Saber dónde están los datos
Cómo se transfieren entre países

### Desafíos
- Empresas multinacionales deben cumplir múltiples leyes
- Acceso desde distintas ubicaciones puede complicar la seguridad
  
#### Conclusión...
Es clave saber:
 - dónde se almacenan los datos
 - dónde se procesan
 - Cumplir con las leyes evita sanciones y protege la información

## Protección de Datos

La seguridad de los datos es esencial y requiere múltiples técnicas para proteger la información frente a amenazas.

Entre los principales métodos están:

- Restricciones geográficas (geofencing): limitan el acceso según la ubicación.
- Cifrado: de texto plano convierte los datos en formato ilegible y solo accesible con una clave de cifrado o mediante algoritmo protege los datos en transito y en reposo.
- Hashing: El hashing es una técnica que convierte datos en un tamaño fijo de caracteres numéricos o alfanuméricos, conocido como valor hash. A diferencia del cifrado, el hashing es una función unidireccional.
  Una vez que los datos se han cifrado, no se pueden revertir ni descifrar. El hashing se utiliza a menudo para almacenar datos sensibles, como contraseñas, y también para comprobar la integridad de los archivos. Ejemplo, Texto Original: hola123. Conversión del Hash: 5d41402abc4b2a76b9719d911017c592
- Enmascaramiento: oculta datos sensibles sustituyéndolos por un marcador de posición o caracter, como X. Ejemplo, cuando nos mandan un gmail de recuperación a dicho número (****32), Una vez que se enmascaran los datos, se trata de un proceso unidireccional que no puede revertirse, lo que lo convierte en un método de desidentificación.
- Tokenización: reemplaza datos reales por tokens seguros. Los datos originales se almacenan de forma segura en una base de datos independiente con un token que sirve de referencia a los datos originales.
- Ofuscación: hace los datos difíciles de entender y poco claros para los usuarios no autorizados, implica diversas técnicas como cifrado, el enmascaramiento de datos y el uso de seudonimos.
- Segmentación: divide la red para evitar movimientos laterales de atacantes.
- Control de permisos (RBAC): restringe el acceso a datos especificos y que puede hacer con ellos solo a usuarios autorizados.

En resumen: proteger datos implica combinar varias técnicas según el contexto para reducir riesgos y evitar accesos no autorizados.

## Prevención de Pérdida de Datos

La Prevención de Pérdida de Datos (DLP) es un conjunto de herramientas que monitorea y protege la información para evitar robos o filtraciones, ya sea cuando los datos están en uso, en tránsito o en reposo.
Con la evolución tecnológica (portátiles, USB, nube), el robo de datos se volvió más fácil y masivo, por lo que las empresas necesitan DLP para proteger su información y propiedad intelectual.

Tipos principales de DLP:
- Endpoint DLP: se instala en computadoras y controla lo que hacen los usuarios con los datos, si alguien intenta transferir un archivo nos lo detectara o nos alerta de ese movimiento de forma parecida a un IDS O IPS, pero centrado en los datos. Los DLP pueden configurarse en modo de detención o prevención.
- Network DLP: pieza de hardware o software que monitorea el tráfico de red, especialmente los datos que entran y salen (la mayoría quieren detectar datos en tránsito que no deberían salir del edificio).
- Storage/Almacenamiento DLP: Se trata de un software que se instala en un servidor en los centros de datos e inspecciona los datos mientras están direccionados en el servidor. Esto suele deberse a que los han cifrado o les han puesto una marca de agua, y queremos asegurarnos de que nadie accede a los datos en momentos en que no debería.
- Cloud DLP: protege datos en servicios en la nube como Google Drive.

👉 Resumen: DLP ayuda a detectar y prevenir que los datos sensibles sean robados o compartidos sin autorización, aplicando reglas de seguridad en todos los entornos.
