## Riesgos de los proveedores externos

El riesgo de terceros se refiere a los problemas de seguridad y operación que pueden surgir al trabajar con proveedores externos (hardware, software o servicios).

#### Idea principal
Al integrar proveedores, la organización abre puertas a vulnerabilidades y amenazas que pueden afectar:
  - Seguridad de datos
  - Operaciones
  - Continuidad del negocio

#### Ejemplos de riesgos
  - Hardware con fallas o vulnerabilidades
  - Software con puertas traseras
  - Proveedores con acceso a datos pero mala seguridad

#### Qué se estudia en este tema
  - Vectores de ataque y vulnerabilidades
  - Riesgos en la cadena de suministro
  - Ataques reales (ej: comprometer un proveedor para atacar a muchos)
  - Evaluación de proveedores antes de contratarlos
  - Monitoreo continuo del proveedor
  - Contratos y acuerdos (SLA, NDA, etc.)

#### Idea clave

Un proveedor puede convertirse en el punto más débil de toda la organización.

#### Resúmen Breve

Riesgo de terceros = los peligros que traen los proveedores al sistema
Solución = evaluarlos, controlarlos y monitorearlos constantemente

## Riesgos de la cadena de suministro

Los riesgos de la cadena de suministro son vulnerabilidades que pueden aparecer a través de hardware, software y proveedores de servicios que usa una organización.

### Tipos principales de riesgos

1. Hardware
Componentes vienen de múltiples proveedores
Pueden estar manipulados o falsificados
Riesgo: malware, acceso no autorizado, fallos

"Para las entidades con un apetito de riesgo mínimo, como el Departamento de Defensa, se han implantado medidas como el programa Trusted Foundry para garantizar que todo el hardware
que se instala en sus redes ha sido sometido a una estricta comprobación para garantizar que son auténticos y que los microprocesadores que contienen han sido fabricados de forma 
segura para realizar únicamente las funciones designadas sin ningún tipo de desviación de la línea de base buena conocida.

Otro riesgo que a menudo se pasa por alto es la compra de hardware adicional de fuentes secundarias o posventa. Aunque estas opciones pueden ser asequibles, el riesgo de adquirir dispositivos falsificados
o manipulados puede ser bastante alto. Estos dispositivos pueden haber sido manipulados, y su código podría estar modificado para incluir malware como un troyano, o podrían permitir el acceso remoto o el acceso
no autorizado a las redes de su empresa, o podrían causar todo tipo de fallos operativos."

2. Software
Puede tener vulnerabilidades o código malicioso
Debe verificarse:
- Licencia
- Integridad
- Seguridad (antivirus, análisis)

3. Proveedores de servicios (MSP)
Tienen acceso a datos sensibles
Riesgos:
- Mala seguridad
- Fugas de datos
- Mala respuesta ante incidentes

"Desde la tangibilidad del hardware hasta la intangibilidad de los servicios, todos los aspectos deben someterse a una auditoría y evaluación de la cadena de suministro."

#### Idea clave

Cada proveedor puede ser un punto de entrada para ataques
“La cadena es tan fuerte como su eslabón más débil”

#### Qué deben hacer las organizaciones
- Evaluar proveedores (seguridad, reputación)
- Auditar hardware y software
- Monitorear continuamente
- Elegir según su apetito de riesgo

#### Resúmen Breve

Riesgos de cadena de suministro = problemas que vienen de hardware, software o proveedores externos
Solución = evaluar, verificar y controlar todo

Quiero que tengamos en cuenta estos conceptos:

Actor de Amenaza → quién ataca
Vector de Amenaza → método general
Vector de Ataque → la vía específica por donde entra

## Ataques a la Cadena de Suministro

Un ataque a la cadena de suministro ocurre cuando un atacante explota el punto más débil (proveedor o componente) para llegar al objetivo principal, en lugar de atacarlo directamente.

#### Idea clave

Los atacantes usan proveedores, hardware o software vulnerables como puerta de entrada a organizaciones más grandes.

#### Ejemplos
Hardware: dispositivos falsificados o chips manipulados con malware
Software: caso SolarWinds, donde se distribuyó malware a miles de organizaciones mediante actualizaciones
Fabricación externa: riesgo de puertas traseras o rootkits(tipo de malware diseñado para ocultarse en el sistema y permitir acceso no autorizado sin ser detectado)

#### Impacto
Puede afectar a miles de empresas y gobiernos
Una sola vulnerabilidad puede causar efectos en cadena

#### Cómo prevenir de los ataques de suministros en su organización
1. Evaluar proveedores (diligencia debida): Analizar antes de contratar si el proveedor es seguro y confiable
2. Auditorías períodicas y monitoreo continuo/supervisión: Revisar y vigilar constantemente para detectar riesgos o fallas a tiempo
3. Educación y colaboración: Mantener a todos informados y trabajar con otros para prevenir amenazas
4. Contratos con requisitos de seguridad/incorporación de salvaguardias contractuales: Exigir por contrato que el proveedor cumpla normas de seguridad (clausula de dercho de auditoria)

Por ejemplo, si una empresa contrata a una empresa de gestión de datos para que maneje los datos de sus clientes, la cláusula de derecho de auditoría permitiría a la empresa inspeccionar 
periódicamente las prácticas de manejo, almacenamiento y protección de datos del proveedor que haya seleccionado.

#### Idea principal
La cadena de suministro es un gran punto de ataque indirecto y protegerla es crítico para toda la organización

#### Resúmen Breve

Ataque de cadena de suministro = atacar al proveedor para llegar al objetivo
Solución = controlar, auditar y asegurar toda la cadena

## Evaluación de proveedores

La evaluación de proveedores es un proceso clave para verificar la seguridad, confiabilidad y rendimiento de terceros (proveedores, vendedores y MSP=proveedores de servicio gestionado como AWS, Google Cloud), ya que un fallo en ellos puede afectar a toda la organización.

"Los proveedores suelen ser empresas o particulares que proporcionan bienes o servicios a una organización."

#### Qué incluye
- Evaluar proveedores antes de trabajar con ellos
- Pruebas de penetración para detectar vulnerabilidades
- Revisión de contratos (incluyendo derecho de auditoría)
- Auditorías internas y externas para validar seguridad. Una auditoría interna se refiere a la autoevaluación de un proveedor, en la que evalúa sus propias prácticas en relación con las normas del sector o los requisitos de la organización.
Por ejemplo, un proveedor de servicios en la nube podría auditar periódicamente sus medidas de protección de datos para garantizar que los protocolos de cifrado están actualizados y se aplican eficazmente.
- Análisis de la cadena de suministro completa, es decir, profundizar en toda la cadena de suministro de un proveedor y evaluar la seguridad y fiabilidad de cada eslabón.

#### Idea clave

- No basta con confiar en el proveedor
- Hay que verificar continuamente su seguridad

#### Objetivo
Detectar riesgos antes de que afecten
Asegurar que el proveedor cumple estándares
Reducir vulnerabilidades externas

#### Resumen Breve

Evaluar proveedores = revisar, probar y controlar su seguridad para evitar riesgos externos

## Selección y seguimiento de proveedores 

La selección y supervisión de proveedores es un proceso clave para elegir socios adecuados y asegurar que cumplan continuamente con los objetivos, seguridad y rendimiento de la organización.

#### Selección de proveedores
- Diligencia debida: evaluar finanzas, reputación, prácticas y seguridad
- Evitar conflictos de interés: decisiones transparentes
- Cuestionarios: recopilar información para comparar proveedores
- Reglas de interacción: definir cómo se comunica y trabaja con ellos
Objetivo: elegir un proveedor confiable y alineado

#### Supervisión de proveedores
- Revisiones de rendimiento: verificar calidad y cumplimiento
- Feedback continuo: comunicación bidireccional
- Monitoreo constante: asegurar que siga cumpliendo con el tiempo

Objetivo: garantizar que el proveedor siga siendo adecuado

#### Idea clave

- No basta con elegir bien
- Hay que controlar y evaluar al proveedor continuamente

#### Resumen Breve

Elegir bien + monitorear siempre = menos riesgos y mejor rendimiento

## Contratos y acuerdos

Los contratos y acuerdos son documentos clave que definen derechos, responsabilidades y expectativas entre las partes, asegurando relaciones claras más allá de la confianza.

#### Tipos principales
- Contrato básico: establece términos generales (pagos, plazos, responsabilidades)
- SLA (Acuerdo de Nivel de Servicio): define el nivel de servicio esperado, ejemplo contrata a una empresa para que gestione su infraestructura informática

#### MOA vs MOU (Documentos):
MOA (Memorándum de Acuerdo) → más formal y específico
MOU (Memorándum de Entendimiento) → intención mutuas, menos vinculante
MSA (Contrato Marco): reglas generales (pagos, confidencialidad)
SOW (Declaración de Trabajo): sirve para definir los detalles específicos de un proyecto, como:
- Entregables (qué se va a entregar)
- Fechas y plazos
- Hitos (etapas importantes)
NDA: protege información confidencial
Acuerdo de Asociación Empresarial(BPA/JV): colaboración y reparto de beneficios

#### Idea clave

- No alcanza con confiar
- Hay que definir todo legalmente y por escrito
- Relaciones personales = riesgo de conflicto de intereses
- Realizar debida diligencia = evaluar bien a los proveedores

#### Objetivo
Evitar conflictos
Proteger información y responsabilidades
Asegurar cumplimiento y claridad

#### Resúmen Breve

Contratos = reglas claras para trabajar seguros y sin problemas
