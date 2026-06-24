## Gestión de Identidad y Acceso (IAM)

La Gestión de Identidad y Acceso (IAM) es un conjunto de tecnologías y procesos que garantizan que las personas correctas tengan acceso a los recursos correctos en el momento adecuado.

IAM se encarga de:

- Gestionar usuarios e identidades digitales.
- Controlar quién puede acceder a qué recursos.
- Administrar contraseñas y permisos.
- Registrar las actividades de los usuarios.

Los 4 procesos principales de IAM

1. Identificación
El usuario dice quién es.
Ejemplo: ingresar un nombre de usuario o correo electrónico.

2. Autenticación
El sistema verifica su identidad.
Ejemplo: introducir una contraseña o usar una huella digital.

3. Autorización
Determina qué puede hacer el usuario.
Ejemplo: leer archivos, modificarlos o administrar sistemas.

4. Contabilidad (Auditoría)
Registra las acciones realizadas por los usuarios.
Ejemplo: guardar quién inició sesión, cuándo y qué hizo.

Temas relacionados que cubre IAM
- Aprovisionamiento y desaprovisionamiento: crear y eliminar cuentas de usuario.
- MFA (Autenticación Multifactor): usar varios factores para verificar identidad.
  - Algo que sabes (contraseña).
  - Algo que tienes (token o celular).
  - Algo que eres (huella, rostro).
  - Algo que haces (firma o comportamiento).
  - Algún lugar donde estás (ubicación).
- Seguridad de contraseñas
  - Políticas de contraseñas.
  - Gestores de contraseñas.
  - Autenticación sin contraseña.
- Ataques a contraseñas
  - Fuerza bruta.
  - Diccionario.
  - Password spraying.
  - Ataques híbridos.
- SSO (Single Sign-On)
  - Un solo inicio de sesión para acceder a varias aplicaciones.
- Federación
  - Permite usar las mismas credenciales en distintos sistemas u organizaciones.
- PAM (Privileged Access Management)
  - Gestión de cuentas con privilegios administrativos.
- Modelos de control de acceso
  - MAC (Mandatory Access Control).
  - DAC (Discretionary Access Control).
  - RBAC (Role-Based Access Control).
  - Rule-Based Access Control.
  - ABAC (Attribute-Based Access Control).
  - Principio de mínimo privilegio.

## Gestión de Identidad y Acceso (IAM)

IAM (Identity and Access Management) Como mencionamos antes es el conjunto de sistemas y procesos que garantiza que las personas correctas tengan acceso a los recursos correctos en el momento adecuado.

Los 4 procesos principales de IAM + Ejemplos

1. Identificación
El usuario indica quién es.
Ejemplo: introducir un nombre de usuario o correo electrónico.

2. Autenticación
El sistema verifica que realmente es esa persona.
Ejemplo: contraseña, huella digital o MFA.

3. Autorización
Determina a qué recursos puede acceder el usuario.
Ejemplo: RR. HH. accede a expedientes de empleados, Finanzas a datos financieros.

4. Contabilidad (Auditoría)
Registra las acciones realizadas por los usuarios.
Ejemplo: cuándo inició sesión, qué hizo y qué cambios realizó.

Otros conceptos de IAM

1. Aprovisionamiento (Provisioning) Y Desaprovisionamiento (Deprovisioning)

- Proceso de crear cuentas y asignar permisos a nuevos usuarios.

Ejemplo: contratar un empleado y darle correo corporativo, acceso a la red y aplicaciones necesarias.

Desaprovisionamiento (Deprovisioning)

- Proceso de eliminar accesos y permisos cuando ya no son necesarios.

Ejemplo: cuando un empleado abandona la empresa.

2. Comprobación de identidad (Identity Proofing)

Verificación de la identidad de una persona antes de crear su cuenta.

Ejemplo: solicitar DNI, pasaporte o licencia de conducir.

3. Interoperabilidad

Capacidad de distintos sistemas para trabajar juntos y compartir información de identidad y para permitir una autenticación y autorización
seguras y sin fisuras entre distintos sistemas.

Ejemplo: usar estándares como SAML u OpenID Connect para iniciar sesión en varios sistemas.

4. Atestación/Certificacion (Attestation)

Revisión periódica de cuentas y permisos para confirmar que siguen siendo correctos.

Ejemplo: comprobar que un empleado conserva únicamente los accesos necesarios para su puesto.

Es decir es un proceso de validación de que las cuentas de usuario y los derechos de acceso son correctos y están actualizados.

Esto suele implicar revisiones y auditorías periódicas de las cuentas de usuario y sus derechos de acceso para garantizar que los usuarios tienen el acceso mínimo necesario para desempeñar su función o sus funciones laborales.

## Autenticación Multifactor (MFA)

La autenticación multifactor (MFA) es un sistema de seguridad que exige dos o más factores de autenticación diferentes para verificar la identidad de un usuario. Su objetivo es dificultar el acceso de personas no autorizadas incluso si una credencial es robada.

#### Factores de autenticación

1. Algo que sabes (Conocimiento)
  - Contraseña
  - PIN
  - Preguntas de seguridad

2. Algo que tienes (Posesión)
Smartphone con código SMS
Aplicación autenticadora (Google Authenticator, Microsoft Authenticator)
Tarjeta inteligente
Token o llave USB de seguridad (hardware)

3. Algo que eres (Inherencia)
Huella dactilar
Reconocimiento facial
Reconocimiento de voz
Escáner de iris

4. Algún lugar donde estás (Ubicación)
Dirección IP
GPS
Red específica autorizada

5. Algo que haces (Comportamiento)
Forma de escribir en el teclado
Movimiento del ratón
Forma de usar el dispositivo

Algo que haces se considera una de las categorías más nuevas que se utilizan en los sistemas de autenticación multifactor, se suele utilizar como factor secundario en los sistemas de autenticación y rara vez
se utiliza en un sistema de autenticación de factor único.

#### Tokens

Token de hardware

  - Dispositivo físico que genera códigos temporales.
  - Ejemplo: llavero de seguridad o llave USB.

Token de software

Aplicación instalada en un móvil o computadora.
Ejemplo: Google Authenticator.
También puede ser un código enviado por SMS o correo electrónico.

#### Tipos de autenticación

- Autenticación de un solo factor (SFA)
  - Utiliza un único tipo de factor.
  - Ejemplo: usuario + contraseña.
  - Aunque sean dos datos, ambos pertenecen al mismo factor ("algo que sabes").

Autenticación de dos factores (2FA)
  - Utiliza dos factores distintos.
  -  Ejemplo:
      - Contraseña (algo que sabes)
      - Código recibido en el móvil (algo que tienes)

Autenticación multifactor (MFA)

  - Utiliza dos o más factores distintos.
  - 2FA es un tipo de MFA.

Para aumentar nuestra seguridad, podemos optar por utilizar la autenticación multifactor, pero esto introducirá pasos adicionales que el usuario debe dar al iniciar sesión en el sistema,
y aumenta nuestro coste global para implementar una solución de autenticación. Afortunadamente, ahora existe una alternativa válida al uso de contraseñas para la autenticación,
y esto nos lleva al mundo de las passkeys.

#### Passkeys (Claves de acceso)

Las Passkeys son una alternativa moderna a las contraseñas.

Características:

- No requieren recordar contraseñas.
- Utilizan biometría o PIN del dispositivo.
- También utiliza criptografía de clave pública. con la clave privada almacenada de forma segura en el dispositivo del usuario y creada utilizando la funcionalidad de bloqueo de pantalla
y la huella dactilar, el reconocimiento facial, el PIN o el patrón de desbloqueo del usuario.

Suposición:

Tu PC → tiene la clave privada.
Servidor → tiene la clave pública.

Cuando intentas conectarte, el servidor verifica que realmente posees la clave privada asociada a esa clave pública.

Entonces, si un atacante compromete el servidor y roba las claves públicas:

- No puede iniciar sesión como tú.
- No puede generar tu clave privada.
- No puede descifrar tus comunicaciones.
- Son más resistentes al phishing y a las filtraciones de datos.
- Mejoran la comodidad y la seguridad.

Ejemplo:

Desbloqueas tu teléfono con tu huella o rostro y automáticamente inicias sesión en una aplicación o sitio web.

Es decir, robar una clave pública no suele representar un riesgo importante, porque el verdadero secreto es la clave privada, que permanece en el equipo del usuario.

Ejemplo sencillo

Imagina que:

La clave pública es como un candado abierto que cualquiera puede ver.
La clave privada es la llave que abre ese candado.

Aunque un atacante robe el candado (clave pública), sigue sin tener la llave (clave privada).

Por eso, en SSH se considera mucho más seguro guardar claves públicas en el servidor que guardar contraseñas o secretos.

#### Gestor de contraseña

Los gestores de contraseñas son herramientas que almacenan y administran contraseñas de forma segura. Sus principales funciones son:

1. Generación de contraseñas
- Crean contraseñas fuertes, aleatorias y únicas para cada cuenta.
- Ayudan a evitar la reutilización de contraseñas.
- Permiten definir longitud, complejidad y uso de caracteres especiales.

2. Autorrelleno (Autofill)
- Completan automáticamente el usuario y la contraseña al iniciar sesión.
- Ahorran tiempo y reducen errores al escribir credenciales.

3. Compartición segura (Secure Sharing)
- Permiten compartir accesos con otras personas sin revelar la contraseña real.
- El usuario autorizado puede acceder a la cuenta, pero sin conocer la contraseña.

4. Acceso multiplataforma
- Funcionan en distintos dispositivos (PC, navegador, móvil, tablet).
- Permiten acceder a las contraseñas desde cualquier lugar.

#### Resúmen Breve

Así que recuerde, los métodos de autenticación multifactor proporcionan un mayor nivel de seguridad que los métodos de autenticación de un solo factor.

Los factores de autenticación son cruciales para validar la identidad de un usuario, y varios métodos nos ofrecen diferentes capas de seguridad.

Algo que sabes se refiere a un dato que sólo el usuario debe conocer, como una contraseña o un PIN.

Algo que tiene que ver con el dispositivo físico que posee un usuario, como un smartphone que recibe un código de verificación o un token de hardware como un llavero.

Algo que abarca la biometría, que son características físicas únicas de un usuario que se utilizan para verificar la identidad, incluidas las huellas dactilares o los escáneres de retina.

Algo que capta el comportamiento único de un usuario, como la dinámica de firmas o los patrones de pulsación de teclas.

Por último, En algún lugar estás aprovecha la ubicación del usuario como mecanismo de autenticación para restringir el acceso a servicios específicos a menos que la ubicación geográfica del usuario,
a menudo determinada mediante GPS o dirección IP, coincida con la zona esperada. Cada factor contribuye a un enfoque holístico de la seguridad y garantiza que sus sistemas de autenticación sean sólidos y multidimensionales.

La implantación de sistemas de autenticación multifactor dificulta que usuarios no autorizados ataquen o accedan a los sistemas de información o a los datos de su organización.

## Seguridad de Contraseñas

La seguridad de las contraseñas mide qué tan difícil es para un atacante adivinar o descifrar una contraseña mediante ataques de fuerza bruta.

5 aspectos clave de una política de contraseñas

1. Longitud de la contraseña
Es el factor más importante.
Cuanto más larga sea la contraseña, más difícil será romperla.
Se recomienda entre 12 y 16 caracteres o más.
Cada carácter adicional aumenta exponencialmente la cantidad de combinaciones posibles.

Ejemplo:

PIN de 4 dígitos = 10.000 combinaciones.
PIN de 8 dígitos = 100 millones de combinaciones.

2. Complejidad de la contraseña

Consiste en combinar:

Letras mayúsculas
Letras minúsculas
Números
Caracteres especiales

Ejemplo:

Débil: password
Fuerte: P3nc1l5Ar3F0rWr1t1ng!

Mientras más tipos de caracteres se utilicen, más difícil será un ataque de fuerza bruta.

3. Reutilización de contraseñas

No se debe:

- Usar la misma contraseña en diferentes servicios.
- Reutilizar contraseñas antiguas.

Si una contraseña se filtra en un sitio, el atacante podría acceder a otras cuentas donde uses la misma ("En caso de una web o app de un factor").

Por eso existe el historial de contraseñas, que impide volver a utilizar contraseñas anteriores.

4. Caducidad de la contraseña

Consiste en obligar al usuario a cambiarla cada cierto tiempo (ej. cada 90 días).

Sin embargo, actualmente el NIST ya no recomienda forzar cambios periódicos porque muchos usuarios terminan creando contraseñas predecibles:

Contraseña1
Contraseña2
Contraseña3

Es mejor usar contraseñas fuertes y únicas.

5. Edad mínima de la contraseña

Define cuánto tiempo debe pasar antes de poder volver a cambiarla.

Sirve para evitar que un usuario cambie rápidamente la contraseña varias veces para regresar a una contraseña antigua.

Ejemplo:

Edad mínima = 3 días.
Edad máxima = 90 días.

Entonces:

No puedes cambiarla durante los primeros 3 días.
Debes cambiarla cuando llegues a los 90 días.

En entrevistas de SOC o ciberseguridad, si te preguntan por la edad mínima, recuerda: evita que los usuarios cambien repetidamente la contraseña para reutiliza

#### Autenticación sin contraseña (Passwordless)

Métodos modernos que reemplazan las contraseñas tradicionales:
- Biometría
  - Huella digital.
  - Reconocimiento facial.
  - Escaneo de iris.

- Token de hardware
  - Llaves físicas de seguridad (ej. YubiKey).

- OTP (One-Time Password)
  - Código temporal enviado por SMS, email o app.

- Magic Link
  - Enlace enviado al correo.
  - Al hacer clic inicia sesión automáticamente.

Passkeys (Clave de acceso)

Sirve como herramienta de autenticación que se integra con el navegador o el sistema operativo. Cuando se configura, se pide a los usuarios que establezcan una clave de acceso.
Al iniciar sesión en un sitio o en aplicaciones, se pide a los usuarios que desbloqueen el dispositivo utilizando el método elegido.
Cuando se configura, se pide a los usuarios que establezcan una clave de acceso. En lugar de recordar y teclear contraseñas, los usuarios utilizan las funciones de seguridad 
integradas en sus dispositivos, como el sensor de huellas dactilares.
Una vez desbloqueado, el dispositivo recupera su clave de acceso almacenada de forma segura y la presenta al sitio o aplicación, verificando la identidad del usuario y concediéndole acceso.

- Utilizan las funciones de seguridad del dispositivo (huella, PIN o rostro).
- Son más seguras que las contraseñas tradicionales.
- Cada vez son más utilizadas por empresas como Google, Apple y Microsoft.

#### Resúmen Breve

Así que, recuerde, cuando se trata de contraseñas, cuanto más larga sea tu contraseña, más tiempo tardarán en descifrarla. La complejidad de las contraseñas evoluciona con el uso de una
mezcla de letras, números y caracteres especiales. Tampoco debes reutilizar nunca las contraseñas y cada una de tus cuentas debe tener su propia contraseña única.

Además, su organización debería considerar la posibilidad de utilizar un gestor de contraseñas que le ayude a gestionar sus contraseñas de forma eficaz y explorar también las opciones sin contraseña 
si están disponibles, ya que proporcionan una mayor seguridad y una mejor experiencia general para el usuario.

## Ataques a Contraseñas

Los ataques a contraseñas son técnicas utilizadas por los atacantes para descubrir o recuperar contraseñas. Los principales tipos son:

1. Ataque de fuerza bruta

Consiste en probar todas las combinaciones posibles hasta encontrar la contraseña correcta.

Ejemplo:

0000, 0001, 0002... hasta 9999.

Ventaja: Siempre funciona si se tiene suficiente tiempo.
Desventaja: Puede ser muy lento con contraseñas largas y complejas.

Protección y Mitigación:

Contraseñas largas y complejas(longitud).
Limitar intentos de inicio de sesión.
MFA (autenticación multifactor).
CAPTCHA para impedir los intentos de descifrado de contraseñas en línea (detectan actividad automatizada y obligan al usuario a demostrar que es humano, dificultando que un programa pruebe miles de contraseñas)

Concepto a tener en cuenta: 

Ataque en línea: probar contraseñas directamente en una página de inicio de sesión.
Ataque offline: descifrar contraseñas robadas localmente, sin conectarse al sistema objetivo. Es decir, ocurre cuando el atacante ya robó una base de datos de contraseñas cifradas (hashes) y las intenta descifrar en su propia computadora, sin conectarse al servidor. En ese caso, un CAPTCHA no sirve porque el atacante no está interactuando con ningún sitio web.

2. Ataque de diccionario

Utiliza una lista de contraseñas comunes y sus variaciones para intentar adivinar la contraseña.

Ejemplos:

password
Password
P@ssw0rd

Ventaja: Más rápido que la fuerza bruta.
Desventaja: No funciona bien contra contraseñas únicas y complejas.

Protección:

Contraseñas únicas y largas.
MFA.
Limitar intentos.

3. Ataque de pulverización de contraseñas (Password Spraying)

Prueba unas pocas contraseñas comunes contra muchas cuentas diferentes(prueba contraseñas a muchas cuentas de la empresas).

Ejemplo:

Probar "Password123" en todas las cuentas de una empresa.

Ventaja: Evita bloqueos de cuenta por demasiados intentos en un solo usuario.

Protección:

Contraseñas fuertes y únicas.
MFA.

4. Ataque híbrido

Combina diccionario + fuerza bruta.

Ejemplo:

Parte de una palabra común ("Fabuloso")
Prueba números al final ("Fabuloso123456")

Ventaja: Más eficiente que la fuerza bruta pura.

Protección:

Contraseñas largas, aleatorias y complejas.
MFA.

Así que si mi palabra del diccionario era fabuloso, y mi número asignado al azar era 617238 entonces mi nueva contraseña se establecería como fabuloso61238.

Así que si sabes que la contraseña de todo el mundo sigue este formato, puedes usar un ataque basado en diccionario para encontrar la primera palabra como
fabuloso y luego usar un ataque de fuerza bruta para probar cada combinación desde fabuloso000001 a fabuloso999999 hasta encontrar la contraseña correcta
como fabuloso617238.

John the Ripper (Decifrador de contraseñas/Herramienta de Hackers)

Es una herramienta de descifrado de contraseñas utilizada para encontrar contraseñas débiles a partir de hashes. Recuerde que el uso de MD5 para hash no se recomienda para ningún propósito de seguridad real debido a sus vulnerabilidades.

Una contraseña común como "password" puede descubrirse en segundos porque ya aparece en listas de contraseñas conocidas. Ahora bien, si vas a almacenar contraseñas, utiliza siempre un algoritmo de hash criptográfico fuerte como SHA-256 combinado con una sal.

Ahora, el salting y los hashes implican añadir una cadena aleatoria de caracteres, también conocida como sal para proteger la contraseña antes de hacer el hash. Esto mejora la seguridad previniendo cualquier texto de diccionario o búsquedas de tabla hashing.

## Resúmen Breve

Así que recuerda, los ataques de fuerza bruta se utilizan para probar todas las combinaciones posibles de una contraseña con el fin de descifrarla, pero
pueden llevar mucho tiempo y ser muy caros de realizar desde el punto de vista computacional.

Un ataque de diccionario utilizará una lista de contraseñas de uso común de un archivo de texto conocido como diccionario para intentar adivinar la contraseña.

Un ataque de rociado de contraseñas intenta probar las mismas contraseñas contra muchas cuentas diferentes para intentar evitar el bloqueo de cualquier cuenta de usuario individual durante el intento de descifrar la contraseña en línea.

Un ataque híbrido se utiliza para combinar las ventajas de un ataque de diccionario y de fuerza bruta para encontrar contraseñas más largas, más fuertes y más complejas en menos tiempo del que podría hacerlo un ataque de fuerza bruta, etc.

Para protegerse contra estos ataques, su organización debe exigir el uso de una contraseña única, larga y compleja, por ejemplo, utilizando gestores de contraseñas para ayudar a gestionar las contraseñas de sus usuarios en la red.

Además, para evitar realmente que los ataques con contraseña tengan éxito, deberías activar la autenticación multifactor siempre que sea posible, ya que añade una capa adicional de seguridad al requerir que se utilice un segundo factor de autenticación además de una simple contraseña.

## Inicio de Sesión Único (SSO)

SSO (Single Sign-On) permite que un usuario inicie sesión una sola vez y acceda a varias aplicaciones o servicios sin volver a ingresar sus credenciales.
Lo más habitual es que el SSO se utilice dentro de una red empresarial y se base en la relación de confianza entre el controlador del directorio activo y las
distintas aplicaciones y sitios web que forman parte de la red de la organización.

¿Cómo funciona?

El usuario se autentica en un Proveedor de Identidad (IdP).
Cuando accede a otra aplicación confiable, esta consulta al IdP si el usuario ya fue autenticado.
Si la respuesta es afirmativa, se le concede acceso sin pedir nuevamente usuario y contraseña.

Ventajas del SSO
- Mejor experiencia de usuario: solo se recuerda una contraseña.
- Mayor productividad: menos tiempo iniciando sesión.
- Menos trabajo para soporte técnico: menos solicitudes de restablecimiento de contraseñas.
- Mayor seguridad: reduce la reutilización de contraseñas y favorece el uso de contraseñas más fuertes.

Ejemplo que se utiliza en el mundo corporativo donde una empresa podría establecer un SSO para sus aplicaciones internas.

Un empleado inicia sesión una vez con sus credenciales de empresa y, a continuación, tiene acceso a su correo electrónico, a la herramienta de medición de proyectos y al sistema de recursos humanos sin necesidad de iniciar sesión en cada uno de ellos por separado.

Para habilitar y admitir el inicio de sesión único, existen tres protocolos de uso común(Protocolos principales de SSO):

1. LDAP (Lightweight Directory Access Protocol/Ligero de acceso a directorios)

Protocolo para acceder y administrar directorios de usuarios y recursos en una red.
Centraliza información de usuarios, grupos, impresoras, archivos, etc.
Puede utilizarse para autenticación y autorización. También para buscar certificados de encriptación, impresoras conectadas y otros servicios de la red.
Esto permite a los sistemas tomar decisiones sobre a qué recursos o servicios debe tener acceso un usuario.
Su versión segura es LDAPS.

Por ejemplo, una organización puede utilizar LDAP para formar un directorio de sus empleados que permita almacenar información sobre esos usuarios en un único lugar y acceder a ella desde distintas aplicaciones, como su lista de contactos, libretas de direcciones y clientes de correo electrónico.

2. OAuth (Open Authorización)

Es un estándar abierto de autenticación y autorización basado en tokens que permite a los usuarios iniciar sesión en aplicaciones o sitios web utilizando cuentas de terceros (como Google) sin compartir su contraseña. Funciona mediante un proveedor de identidad que autentica al usuario y emite un token de acceso. Este token permite que la aplicación acceda únicamente a los datos autorizados por el usuario, como nombre, correo electrónico o foto de perfil. OAuth se utiliza ampliamente en aplicaciones web y API, empleando tokens JWT(Jeson Web Token para intercambiar información de forma segura.

3. SAML (Security Assertion Markup Language)

Estándar que permite a una aplicación confiar en la autenticación realizada por un proveedor de identidad.
La aplicación no autentica directamente al usuario; recibe una confirmación del IdP.

Ahora bien, SAML puede ser un poco complejo, pero lo que realmente hay que recordar es que permite desacoplar los servicios de los proveedores de identidad y elimina la necesidad de que los servicios autentiquen directamente a los usuarios.

Breve: 

SSO: un inicio de sesión para múltiples aplicaciones.
LDAP: directorio centralizado de usuarios y recursos.
OAuth: autorización mediante tokens (ej.: "Iniciar sesión con Google").
SAML: intercambio de información de autenticación entre un proveedor de identidad y una aplicación.

Resúmen:

Así que recuerde, el inicio de sesión único, también conocido como SSO, permite a un usuario acceder a varias aplicaciones o sitios web iniciando sesión una sola vez con un único conjunto de credenciales.

LDAP es un protocolo utilizado para acceder y mantener servicios de información de directorio distribuidos a través de una red IP.

OAuth es un estándar abierto para la autenticación y autorización basadas en tokens.

SAML es un estándar para registrar usuarios en aplicaciones basándose en sus sesiones en otro contexto.
El inicio de sesión único es una gran tecnología que aumenta la facilidad de uso e incrementa la seguridad de sus sistemas de autenticación al basarse en una red de socios de identidad de confianza para ayudar a garantizar que cada uso se valida y autentica correctamente.
