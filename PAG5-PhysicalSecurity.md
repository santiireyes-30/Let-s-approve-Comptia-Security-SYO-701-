# Seguridad Física

En esta sección se estudia la seguridad física, que consiste en las medidas utilizadas para proteger activos tangibles como edificios, equipos y personal frente a daños o accesos no autorizados.
La seguridad física busca prevenir accesos no autorizados a las instalaciones mediante controles, mientras que los profesionales de seguridad deben identificar y analizar los ataques que intentan evadir estos controles.

# Introducción

     - Bolardos y Vallas

     - Vestíbulo de control de acceso (mantrap)

     - Cercado

     - Videovigilancia

     - Guardia de seguridad

     - Tarjeta de acceso

     - Iluminación

     - Sensores

           - Infrarrojo

           - Presión

           - Microondas

           - Ultrasonido

También se estudian ataques contra la seguridad física, como:

        - Entrada forzada
        
        - Manipulación de dispositivos de seguridad
        
        - Embestida con vehículos
        
        - Piggybacking (acceso con ayuda de alguien autorizado)
        
        - Tailgating (seguir a alguien autorizado sin que lo note)

Además, se analiza cómo algunos dispositivos como el Flipper Zero pueden utilizarse en pruebas de seguridad para demostrar vulnerabilidades, por ejemplo clonando tarjetas de acceso RFID.

# Controles de Seguridad Física

Definición breve de Vallas y Bolados:

Vallas: Control para impedir acceso a personas.

Bolardos: objeto para impedir accesos a vehiculos ante un posible ataque.

Fuerza bruta: es un tipo de ataque donde el atacante intenta superar un sistema probando todas las posibilidades o usando métodos directos y violentos para obtener acceso.
En seguridad física, los ataques de fuerza bruta incluyen principalmente:

     - Entrada forzada
     - Acceso no autorizado rompiendo o superando barreras físicas como ventanas, puertas o vallas.
                                                                  
+Info: Los ataques de fuerza bruta en seguridad física son directos y violentos, pero pueden ser muy efectivos si las instalaciones no tienen múltiples capas de protección.

# Sistema de vigilancia 

Los sitemas de vigilancia son un conjunto de herramientas y métodos utilizados para observar, detectar y responder a actividades sospechosas en un área,
con el objetivo de proteger instalaciones, personas y activos.
Un sistema de vigilancia efectivo combina cámaras, guardias, iluminación y sensores para detectar amenazas y responder rápidamente ante intrusiones. A continuación veremos
algunos conceptos, Hay que tener en cuenta que la vigilancia se divide en cuatro componentes principales:

Videovigilancia (CCTV):
     - Uso de cámaras para monitorear áreas en tiempo real y revisar grabaciones.
     - Puede incluir detección de movimiento, visión nocturna, reconocimiento facial y acceso remoto.
     - Las cámaras pueden ser con cable o inalámbricas, y algunas tienen PTZ (Pan-Tilt-Zoom) para mover y ajustar el ángulo.

Guardias de seguridad:
     - Personal entrenado para detectar comportamientos sospechosos, responder a incidentes y disuadir atacantes.

Iluminación:
     - Mejora la visibilidad para cámaras y guardias, reduce escondites y actúa como disuasión.
     - Algunas luces pueden activarse por movimiento.

Sensores:
     - Detectan cambios en el entorno y envían alertas.
     Tipos principales:

          - Infrarrojos: detecta radiación infrarroja, invisible al ojo humano, para medir distancias, detectar objetos o movimiento, o identificar cambios de calor.
          - Presión: se activan cuando alguien pisa una superficie.
          - Microondas: detectan movimiento en áreas amplias.
          - Ultrasónicos: usan ondas sonoras para detectar movimientos.

Otra cosa que debemos tener en cuenta que los sistemas de vigilancia no son infalibles, un intruso decidido podría intentar diversas técnicas para eludir o desactivar su sistema de vigilancia
con el fin de evitar ser detectado. Analicemos algunos de los diferentes métodos utilizados por los atacantes para eludir los sistemas de vigilancia de su organización...

1. Obstrucción visual
Bloquear la cámara con objetos, cinta, pegatinas o pintura para impedir su visión.

2. Cegamiento de cámaras o sensores
Usar luces intensas, láseres o cambios de temperatura para inutilizar temporalmente sensores o cámaras.

3. Interferencia acústica
Utilizar ruido fuerte o dispositivos de ruido blanco para impedir que los sensores de audio detecten sonidos.

4. Interferencia electromagnética (EMI)
Interrumpir las señales inalámbricas o radiofrecuencias utilizadas por los sistemas de vigilancia.

5. Ataques al entorno físico
Manipular el entorno como cortar energía, dañar cables, cambiar temperatura para dañar sensor infrarojo o sabotear equipos.

# Vestículo de Control

Un vestíbulo de control de acceso es un sistema de seguridad física formado por dos puertas controladas electrónicamente, donde solo una puede abrirse a la vez.
Su objetivo es verificar la identidad de una persona antes de permitirle entrar a una zona segura de un edificio.

Cuando alguien entra por la puerta exterior, queda en un espacio intermedio. Allí se verifican sus credenciales (por ejemplo con una tarjeta de acceso).
Si la verificación es correcta, se abre la puerta interior; si no, se le niega el acceso.

Este sistema suele complementarse con tarjetas de acceso (RFID, NFC o banda magnética) y guardias de seguridad, creando una seguridad física por capas.

Además, ayuda a prevenir dos ataques comunes:

Piggybacking: cuando alguien autorizado deja entrar a otra persona sin permiso.

Tailgating: cuando un intruso sigue a una persona autorizada sin que esta lo note.

Las tarjetas de acceso también registran cada entrada, creando un registro de auditoría para investigar incidentes de seguridad.

# Cerraduras de puertas

Las cerraduras de puertas son controles de seguridad física internos que restringen y regulan el acceso a áreas sensibles dentro de una organización y
protegen áreas críticas como salas de servidores o armarios de red. No todas las cerraduras ofrecen el mismo nivel de seguridad, los candados y cerraduras
simples pueden ser forzados rápidamente por atacantes.

- Cerraduras modernas usan tecnologías más seguras como PIN, señales inalámbricas (NFC, Bluetooth, RFID) o biometría.
- Una de ellas es Cipher Lock(Bloqueo Cifrado): Es una cerradura mecánica o electrónica que se abre introduciendo una combinación numérica en un teclado.

La biometría identifica a una persona mediante características físicas como huella dactilar, rostro, lo que corresponde al factor de autenticación “ALGO QUE ERES”.
Para evaluar sistemas biométricos se usan tres métricas:

- FAR (False Acceptance Rate/Tasa de Falsa Aceptación): cuando el sistema acepta a alguien que no debería tener acceso, lo ideal es reducir a cero la tasa
                                                        de falsas aceptaciones aumentando la sensibilidad de nuestros escáneres.

- FRR (False Rejection Rate): cuando el sistema rechaza a un usuario autorizado, Ej: aumento la tasa de sensibilidad y el dispositivo me rechaza y soy el dueño

Intentamos conseguir un buen equilibrio entre estos dos factores para que la tasa de falsos aceptados y la tasa de falsos rechazados sean iguales. Este punto de igualdad
se conoce como Tasa de Igualdad de Errores (EER, por sus siglas en inglés), pero en el sector de la ciberseguridad se suele denominar Tasa de Cruce de Errores (CER).
Esto se debe a que su Tasa de Falsa Aceptación y su Tasa de Falso Rechazo se cruzan en ese punto específico donde son iguales, que es la Tasa de Error de Cruce.

Esta Tasa de Error de Cruce es realmente importante porque se utiliza como medida de la eficacia de un sistema biométrico determinado.

- CER o EER (Cross / Equal Error Rate): punto donde FAR y FRR son iguales; cuanto más bajo, mejor es el sistema.

Autenticación multifactor en cerraduras

Las cerraduras modernas suelen usar más de un factor de autenticación. Ejemplo:

- PIN + huella
- Tarjeta + PIN

Esto es MFA (Multi-Factor Authentication).

Tipos de factores:

Factor:                  |   Ejemplo:
 Algo que sabes          |   PIN
 Algo que tienes	     |   Tarjeta
 Algo que eres	          |   Huella

 # Clonación de Credenciales de Acceso

La clonación de credenciales de acceso es un ataque en el que un atacante copia los datos de una tarjeta RFID o NFC y los transfiere a otra tarjeta
o dispositivo para suplantar la identidad de un usuario autorizado y acceder a edificios, sistemas o realizar pagos. Se trata de una vulnerabilidad
común en sistemas de control de acceso, por lo que se deben aplicar múltiples medidas de seguridad para evitarla.

El proceso suele tener cuatro pasos:

1. Escaneo: el atacante lee la tarjeta RFID/NFC con un lector cercano.

2. Extracción de datos: obtiene el identificador o datos de autenticación.

3. Clonación: copia esa información en otra tarjeta o dispositivo (por ejemplo con herramientas como Flipper Zero).

4. Uso: utiliza la tarjeta clonada para obtener acceso no autorizado.

Este ataque es peligroso porque es fácil, barato y difícil de detectar, y puede permitir a los atacantes entrar a instalaciones o cometer fraudes.
Para prevenirlo, las organizaciones pueden:

- Usar cifrado fuerte en las tarjetas.

- Implementar autenticación multifactor (MFA) como tarjeta + PIN.

- Actualizar regularmente claves y sistemas.

- Capacitar a los usuarios sobre riesgos.

- Usar fundas o carteras con protección RFID.

- Monitorear los registros de acceso para detectar comportamientos sospechosos.
