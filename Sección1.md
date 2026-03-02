# Sección 1: Fundamentos de Seguridad

Vamos a centrarnos en los fundamentos de la seguridad.

Ahora, antes de que podamos profundizar en cualquier discusión técnica sobre Inyecciones SQL o Cracking de
contraseñas o la seguridad de los sistemas de su empresa mediante la configuración
de sus firewalls, tenemos que cubrir primero algunos conceptos básicos que usted simplemente debe entender.

# 2 Términos a tener en cuenta y su diferencia:
Seguridad en la Información: 

Es el acto de proteger los datos y la información del acceso no autorizado, la modificación
e interrupción ilícitas, la divulgación o corrupción y la destrucción.

En pocas palabras, cuando hablamos de seguridad de la información, nos referimos a los datos que guardan los sistemas,
no a los sistemas en sí.

Seguridad en Sistemas de Información: 

Es el acto de proteger los sistemas que contienen y procesan nuestros datos críticos. Puede ser un ordenador, un servidor, 
un dispositivo de red o incluso tu smartphone.

- Recuerde que si alguien habla de proteger los datos en sí, está hablando de seguridad de la información, pero si se refiere
a los dispositivos que contienen los datos, entonces hablamos de seguridad del sistema de información.

# Conceptos Generales de Seguridad

El Objetivo nº 1.1 establece que debes ser capaz de comparar y contrastar varios tipos de controles de seguridad.
El Objetivo 1.2 establece que debes ser capaz de resumir conceptos fundamentales de seguridad.

Así que para empezar esta sección, vamos a empezar con el objetivo 1. 2 y empezaremos
cubriendo la C.I.A Una tríada, que significa confidencialidad, integridad y disponibilidad,
y son los tres pilares de la seguridad.

- La confidencialidad garantiza que sólo puedan acceder a la información, quienes dispongan de la debida autorización.
  EJ: Si encriptas archivos sensibles para que sólo las personas autorizadas puedan leerlos y desencriptarlos.
- La integridad va a garantizar que los datos sigan siendo exactos e inalterados a menos que sea necesario modificarlos.
  EJ: las sumas de comprobación pueden utilizarse para verificar que un archivo no ha sido modificado o corrompido mientras se desplaza por nuestra
  red durante una transferencia de datos.
- La disponibilidad garantiza que los recursos de información sean accesibles y funcionales cuando los necesiten los usuarios autorizados.
  EJ: Sería su sitio web cuando aplica medidas de redundancia para garantizar que permanece en línea y activo en cualquier momento, independientemente
  del tráfico que reciba.

  IMPORTANTE!!: MÁS ALLA DE LA TRIADA C.I.A HOY ES C.I.A.N.A (Confidencialidad, Integridad, Disponibilidad, No-Repudio y Autenticación...
  
# Concepto de no-repudio

No repudio significa garantizar que una acción o acontecimiento específico ha tenido lugar y no puede ser negado por las partes implicadas.
Por ejemplo, si te envío un correo electrónico y lo firmo digitalmente, eso va a garantizar que no puedo negar que te envié ese
mensaje en concreto porque mi firma digital está adjunta a él.

Ahora pasamos a este ámbito de las A.A.A de la seguridad, que llamamos autenticación, autorización y contabilidad.

# Concepto de Autenticación

- La autenticación es el proceso de verificación de la identidad de un usuario o sistema. Por ejemplo, cuando intenta acceder a su correo electrónico,
su nombre de usuario y contraseña se cotejan con una versión almacenada para confirmar su identidad.

- La autorización determina qué acciones o recursos un usuario autenticado tiene permisos para realizar.

- La contabilidad es el acto de rastrear las actividades de los usuarios y la utilización de los recursos y, por lo general, lo hacemos con fines
de auditoría o facturación. Así que cuando inicias sesión en tu ordenador, en realidad estamos registrando lo que haces.

# Controles de Seguridad

los controles de seguridad son medidas o mecanismos que se establecen para mitigar los riesgos y proteger la confidencialidad, integridad y disponibilidad
de los sistemas de información y sus datos. Estos controles de seguridad pueden agruparse en categorías, como controles técnicos, de gestión, operativos
y físicos, pero también podemos hablar de los distintos tipos de controles de seguridad que tenemos, como controles preventivos, disuasorios, detectivos, 
correctivos, compensatorios y directivos.

# Zero Trust (Confianza cero)

a confianza cero es un modelo de seguridad más reciente que se basa en el principio de que no se debe confiar por defecto en nadie, ya sea
dentro o fuera de la organización, y se va a exigir verificación a todo aquel que intente acceder a los recursos del sistema.

Para lograr la confianza cero, tenemos que utilizar un plano de control y un plano de datos. El plano de control está formado por la identidad adaptativa,
la reducción del alcance de las amenazas, los controles de acceso basados en políticas y las zonas seguras. Por otro lado, el plan de datos se va
a centrar en el sujeto y el sistema, el motor de políticas, el administrador de políticas y el establecimiento de puntos de aplicación de políticas.

''No confíes en nada, verifica todo.''

Implica:

- Verificación continua

- Autenticación fuerte

- No confiar solo por estar dentro de la red, Incluso si estás en la red corporativa, debes validar identidad constantemente.

# Amenazas, Vulnerabilidades y Gestión del Riesgo

Como profesionales de ciberseguridad, nuestro trabajo es impedir que las amenazas exploten las vulnerabilidades de los sistemas.

🔹  Amenaza

Es cualquier cosa que pueda causar daño, pérdida o perjuicio a los sistemas.
Provienen de fuentes externas como:

- Ciberataques
- Violaciones de datos
- Divulgación de información confidencial

No podemos controlar totalmente las amenazas, pero sí podemos minimizar su impacto.

🔹  Vulnerabilidad

Es una debilidad en el diseño o implementación de un sistema.
Proviene de factores internos como:

- Errores de software
- Mala configuración
- Falta de parches
- Falta de seguridad física

Las vulnerabilidades sí están bajo nuestro control y pueden gestionarse mediante:

- Mitigación
- Transferencia
- Evitación
- Aceptación del riesgo

🔹 Riesgo

El riesgo existe cuando una amenaza puede explotar una vulnerabilidad.

Amenaza sin vulnerabilidad → no hay riesgo.

Vulnerabilidad sin amenaza → no hay riesgo.

El trabajo del profesional de ciberseguridad es gestionar ese riesgo constantemente.

# En Resúmen: 
La ciberseguridad consiste en gestionar el riesgo reduciendo vulnerabilidades y mitigando el impacto de las amenazas.
