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
