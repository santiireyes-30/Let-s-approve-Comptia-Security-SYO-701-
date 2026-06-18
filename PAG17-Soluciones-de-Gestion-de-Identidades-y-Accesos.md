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
Token o llave USB de seguridad
3. Algo que eres (Inherencia)
Huella dactilar
Reconocimiento facial
Reconocimiento de voz
Escáner de iris
4. Algún lugar donde estás (Ubicación)
Dirección IP
GPS
Red específica autorizada
Algo que haces (Comportamiento)
Forma de escribir en el teclado
Movimiento del ratón
Forma de usar el dispositivo

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

#### Tokens

Token de hardware

  - Dispositivo físico que genera códigos temporales.
  - Ejemplo: llavero de seguridad o llave USB.

Token de software

Aplicación instalada en un móvil o computadora.
Ejemplo: Google Authenticator.
También puede ser un código enviado por SMS o correo electrónico.

#### Passkeys (Claves de acceso)

Las Passkeys son una alternativa moderna a las contraseñas.

Características:

No requieren recordar contraseñas.
Utilizan biometría o PIN del dispositivo.
Se basan en criptografía de clave pública.
Son más resistentes al phishing y a las filtraciones de datos.
Mejoran la comodidad y la seguridad.

Ejemplo:

Desbloqueas tu teléfono con tu huella o rostro y automáticamente inicias sesión en una aplicación o sitio web.
