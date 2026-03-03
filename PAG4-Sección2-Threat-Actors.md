# En esta Sección consta de 2 Dominios: 
# Dominio 1: Conceptos Generales de Seguridad 

Cabe aclarar que son conceptos muy básicos que debes tener en cuenta y que algunos conceptos ya hemos repasado, pero estos son los totales en esta Sección!

# 1.0 Conceptos Generales de Seguridad

# Introducción
1.2 Resumir conceptos fundamentales de seguridad

• Confidencialidad, Integridad y Disponibilidad (CIA)

• No repudio
 
• Autenticación, Autorización y Contabilidad (AAA)

      Autenticación de personas

      Autenticación de sistemas

      Modelos de autorización

• Análisis de brechas (Gap analysis)

• Confianza Cero (Zero Trust)

      Plano de control

      Identidad adaptativa

      Reducción del alcance de amenazas

      Control de acceso basado en políticas

      Administrador de políticas

      Motor de políticas

      Plano de datos

      Zonas de confianza implícitas

      Sujeto/Sistema

      Punto de aplicación de políticas

• Seguridad física

      Bolardos

      Vestíbulo de control de acceso (mantrap)

      Cercado

      Videovigilancia

      Guardia de seguridad

      Tarjeta de acceso

      Iluminación

      Sensores

            Infrarrojo

            Presión

            Microondas

            Ultrasonido
      
# Dominio 2: Amenazas, Vulnerabilidades y Mitigaciones

# Actores de Amenazas y Motivaciones Comúnes

Un actor de amenaza es cualquier persona o entidad que realiza ataques contra sistemas o datos. Puede ir desde un hacker inexperto hasta grupos criminales organizados o incluso Estados-nación.

• Motivaciones principales, Los actores atacan por diferentes razones:

      Ganancia financiera

      Espionaje

      Exfiltración de datos

      Interrupción o sabotaje

      Guerra o caos

      Ideologías políticas o sociales

      Venganza

      Atributos

• Se diferencian por:

     Internos vs externos

     Nivel de recursos y financiamiento

     Grado de sofisticación

• Tipos principales

     Script kiddies → Poca experiencia, usan herramientas ya hechas.

     Hacktivistas → Motivación ideológica.

     Crimen organizado → Buscan dinero (ransomware, fraude).

     Estado-nación → Ataques avanzados patrocinados por gobiernos.

     Amenazas internas → Empleados maliciosos o descuidados.

• Vectores y superficie de ataque, Incluyen:

     Emails y mensajes

     Archivos e imágenes

     Llamadas (vishing)

     Dispositivos removibles

     Redes inseguras

     También se menciona el riesgo del Shadow IT (uso de sistemas sin aprobación).

2.1 Comparar y contrastar actores de amenazas comunes y sus motivaciones.

• Actores de amenazas

      Estado-nación

      Atacante sin habilidades (inexperto)

      Hacktivista

      Amenaza interna

      Crimen organizado

      TI en la sombra (Shadow IT)

• Atributos de los actores

      Interno/externo
  
      Recursos/financiamiento

      Nivel de sofisticación/capacidad

• Motivaciones

      Exfiltración de datos

      Espionaje
  
      Interrupción del servicio

      Chantaje

      Ganancia financiera

      Creencias filosóficas/políticas

      Ética

      Venganza

      Disrupción/caos

      Guerra

2.2 Explicar vectores de amenaza comunes y superficies de ataque.

• Basados en mensajes

      Correo electrónico

      Servicio de Mensajes Cortos (SMS)
  
      Mensajería instantánea (IM)

• Basados en imágenes

• Basados en archivos

• Llamada de voz

• Dispositivo extraíble

• Software vulnerable

      Basado en cliente vs. sin agente

• Sistemas y aplicaciones sin soporte

• Redes no seguras

      Inalámbricas

      Cableadas

      Bluetooth

• Puertos de servicio abiertos

• Credenciales predeterminadas

• Cadena de suministro

      Proveedores de servicios gestionados (MSP)

      Vendedores

      Proveedores

• Vectores humanos / ingeniería social
  
      Phishing

      Vishing

      Smishing

      Información errónea / desinformación

      Suplantación de identidad

      Compromiso de correo electrónico empresarial (BEC)

      Pretexting (creación de pretextos)

      Watering hole (ataque de abrevadero)

      Suplantación de marca

      Typosquatting**
      
# Actores de Amenazas

Un actor de amenazas es una persona o entidad responsable de incidentes que afectan a la seguridad y la protección de datos. Estos actores, que pueden ser desde hackers solitarios hasta grupos de delincuencia organizada o incluso entidades
estatales, iniciarán ataques para robar, alterar o destruir sus datos. Comprender a los actores de la amenaza y sus motivaciones es una parte crucial del desarrollo de estrategias eficaces de ciberseguridad. un Actor de Amenaza puede ser cualquier
cosa, desde el niño del vecindario, que está tratando de descifrar su contraseña de wifi para disfrutar de un poco de Internet gratis, hasta organizaciones financiadas por el gobierno que están tratando de causar el caos y la interrupción entre
sus enemigos.

• Motivaciones: 

     Exfiltración de Datos, Chantaje, Espionaje, Interrupción del servicio, Beneficio Económico, Creencias Filosóficas o políticas, Razones éticas, Venganza, Caos/Interrupción y la Guerra Cibernética.

1. Exfiltración de Datos → La exfiltración de datos se refiere a la transferencia no autorizada de datos desde un ordenador. Ej: si un atacante es capaz de entrar en uno de los ordenadores de su organización y robar la información de contacto de sus clientes, significa que ha conseguido filtrar datos de su organización.

Los datos robados pueden venderse en la web oscura, usarse para robo de identidad o para obtener ventaja competitiva. Por eso, la filtración de datos es una de las principales motivaciones de muchos actores de amenaza.

2️. Chantaje → Amenazan con divulgar información sensible (ej: sextorsión, doxxing).
3. Espionaje → Robo de información estratégica o competitiva.
4. Interrupción del servicio → Ataques como DDoS para causar caos o exigir rescate.
5. Beneficio económico → Ransomware, robo bancario, fraude.
6. Creencias políticas o filosóficas → Hacktivismo para promover una causa.
7. Razones éticas → Hackers éticos que buscan mejorar la seguridad.
8. Venganza → Empleados descontentos o atacantes con resentimiento.
9. Caos o desorganización → Atacan por desafío o por causar daño.
10. Guerra cibernética → Ataques entre naciones por objetivos geopolíticos.

📌 Idea clave

Comprender las motivaciones permite anticipar ataques y diseñar mejores defensas, ya que cada tipo de actor actúa según objetivos distintos: dinero, ideología, venganza, espionaje o guerra.
    
Atributos y Tipos de Actores de Amenaza:

Los atributos de los actores de amenaza son las características que los diferencian, como:
Principales atributos

1. Nivel de sofisticación (Qué tan avanzadas son sus habilidades técnicas)

      Bajo → Script kiddies

      Medio → Crimen organizado

      Alto → Estado-nación

2️. Recursos / financiamiento

      Cuánto dinero, herramientas e infraestructura tienen.

      Pocos recursos → Atacante individual

      Muchos recursos → Gobierno o grupo organizado

3️. Nivel de acceso

      Desde dónde atacan.

      Interno → Empleado con acceso legítimo

      Externo → Hacker desde internet

4️. Intención / propósito

      Financiera

      Ideológica

      Espionaje

      Venganza

• Diferencia clave para el examen

      Motivación → Por qué ataca

      Atributo → Qué características tiene el atacante

Ejemplo rápido...

Un empleado despedido que roba datos:

      Atributo → Interno, acceso legítimo, baja sofisticación

      Motivación → Venganza

Tipos principales de actores:

      Atacantes inexpertos (script kiddies) → Poca habilidad técnica, usan herramientas ya hechas.

      Hacktivistas → Motivación política o social.

      Crimen organizado → Buscan ganancias económicas (ransomware, fraude).

      Estado-nación → Altamente sofisticados, patrocinados por gobiernos.

      Amenazas internas → Empleados maliciosos o descuidados.

Otros conceptos clave:

      Shadow IT → Uso de sistemas o aplicaciones sin aprobación oficial, generando riesgos.

      Vectores de amenaza → Mensajes, archivos, llamadas, dispositivos removibles, redes inseguras.

Tecnologías de engaño:

      Honeypots (sistemas señuelo)

      Honeynets (redes señuelo)

      Honeyfiles (archivos trampa)

      Honeytokens (datos falsos para detectar accesos indebidos)

Idea central:

Comprender los atributos, tipos y métodos de los actores de amenaza ayuda a diseñar mejores estrategias de defensa y detección en ciberseguridad.
