# Confidencialidad

La confidencialidad garantiza que la información sensible solo sea accesible para personas autorizadas, evitando accesos o divulgaciones no autorizadas.

Es importante por tres razones principales:

Proteger la privacidad personal (datos médicos, financieros, personales).

Mantener ventaja competitiva (información estratégica de la empresa).

Cumplir normativas (protección de datos como PII, PHI, datos financieros).

🔐 Métodos para garantizarla:

Cifrado (encryption) → Convierte datos en código para que no puedan leerse sin clave.

Controles de acceso → Permisos y autenticación para limitar quién accede.

Enmascaramiento de datos → Oculta partes sensibles (ej. tarjeta de crédito).

Seguridad física → Protección de servidores y documentos físicos.

Capacitación y concienciación → Reduce errores humanos.

📌 En Security+, cuando escuches Confidencialidad, piensa principalmente en Cifrado (Encryption).

# Integridad

La integridad garantiza que los datos permanezcan exactos, confiables y sin modificaciones no autorizadas durante todo su ciclo de vida (almacenamiento, procesamiento y transmisión).

Es clave por tres razones:

Exactitud de los datos → Las decisiones se basan en información correcta.

Confianza → Los usuarios deben confiar en que los datos no han sido alterados.

Operatividad del sistema → Datos corruptos pueden causar fallos o caídas.

🔐 Métodos para mantener la integridad:

Hashing → Genera una “huella digital” del archivo; si cambia algo, cambia el hash.

Firmas digitales → Usan hash + cifrado para garantizar integridad y autenticidad.

Checksums → Verifican que los datos no se alteraron durante la transmisión.

Controles de acceso → Solo usuarios autorizados pueden modificar datos.

Auditorías periódicas → Detectan cambios no autorizados.

📌 En Security+, cuando escuches Integridad, piensa principalmente en Hashing.

# Disponibilidad

La disponibilidad garantiza que los sistemas, servicios y datos estén accesibles y operativos cuando los usuarios autorizados los necesiten.

Es clave porque permite:

Continuidad del negocio → Evita pérdidas económicas por caídas.

Confianza del cliente → Los usuarios esperan acceso constante.

Reputación empresarial → Fallos frecuentes dañan la imagen.

📊 Niveles de disponibilidad

Se mide por el “número de nueves”:

99.9% (tres nueves) → hasta ~8 horas de caída al año.

99.999% (cinco nueves) → solo ~5 minutos de caída al año.

Cuantos más “nueves”, menor tiempo de inactividad.

🔄 Cómo se garantiza

La clave es la redundancia (tener respaldos o sistemas duplicados):

Redundancia de servidores (failover / balanceo de carga)

Redundancia de datos (copias en múltiples ubicaciones)

Redundancia de red (múltiples conexiones)

Redundancia de energía (UPS, generadores)

📌 En Security+, cuando escuches Disponibilidad, piensa en Redundancia y resiliencia.

🔁 Redundancia

Es la duplicación de componentes críticos (servidores, enlaces de red, energía, datos) para que, si uno falla, otro tome su lugar automáticamente.
👉 Objetivo: evitar interrupciones.

Ejemplo: tener dos conexiones a Internet o servidores en failover.

🛡️ Resiliencia

Es la capacidad de un sistema para resistir, adaptarse y recuperarse rápidamente ante fallos o ataques.
👉 Objetivo: mantener operaciones y volver a la normalidad lo antes posible.

Ejemplo: un plan de recuperación ante desastres (DRP).

# No Repudio

El no repudio garantiza que una persona o entidad no pueda negar haber realizado una acción o enviado una comunicación digital.

Es decir, proporciona prueba irrefutable de participación y autenticidad en una transacción.

🔐 ¿Cómo se logra?

Principalmente mediante firmas digitales:

Se genera un hash del mensaje.

Ese hash se cifra con la clave privada del emisor.

Esto crea una firma única que prueba:

Quién lo envió (autenticidad).

Que no fue alterado (integridad).

Si alguien intenta negar la acción, la firma digital actúa como evidencia.

🎯 ¿Por qué es importante?

Confirma la autenticidad de transacciones digitales.

Garantiza la integridad de la información.

Proporciona responsabilidad y trazabilidad.

# Autententicación

La autenticación es el proceso de verificar que una persona o entidad es quien dice ser antes de permitirle acceso a un sistema o recurso.

Su objetivo es evitar accesos no autorizados y proteger datos, privacidad y recursos digitales.

🔐 5 Factores de autenticación

Algo que sabes → contraseña, PIN (factor de conocimiento).

Algo que tienes → tarjeta, token, código SMS (factor de posesión).

Algo que eres → huella, rostro (biometría / inherencia).

Algo que haces → firma, patrón de comportamiento (factor de acción).

Algún lugar donde estás → ubicación geográfica (factor de localización).

🔑 MFA (Multi-Factor Authentication)

Combina dos o más factores (ej. contraseña + código SMS).
Aunque uno sea comprometido, el atacante no podrá acceder sin el segundo factor.

🎯 ¿Por qué es clave?

Previene accesos no autorizados.

Protege datos sensibles.

Garantiza que solo usuarios válidos consuman recursos.

📌 En Security+, cuando escuches Autenticación, piensa en verificación de identidad + factores (especialmente MFA).

# Autorización

Mientras que la autenticación consiste en verificar la identidad, la autorización consiste en determinar qué se le permite hacer a esa identidad 
dentro de un sistema determinado.

La autorización determina qué puede hacer un usuario después de haberse autenticado.

Si la autenticación responde a “¿Quién eres?”,
la autorización responde a “¿Qué tienes permitido hacer?”.

🔐 ¿Cómo funciona?

Se basa en reglas y políticas como:

- Control basado en roles (RBAC)

- Reglas o atributos específicos

No todos los usuarios tienen los mismos permisos, aunque accedan al mismo sistema.

🎯 ¿Por qué es importante?

Protege datos sensibles → Solo usuarios autorizados pueden ver o modificar información crítica.

Mantiene la integridad del sistema → Evita cambios accidentales o maliciosos.

Mejora la experiencia del usuario → Cada usuario ve solo lo necesario para su función.

📌 En Security+, cuando escuches Autorización, piensa en permisos y privilegios después de la autenticación.

# Disponibilidad/Accounting

La contabilidad es el proceso de registrar y monitorear todas las acciones que realizan los usuarios dentro de un sistema.

No se trata de dinero, sino de crear un registro detallado (logs) de actividades como:

- Inicios de sesión

- Acceso a archivos

- Cambios de configuración

- Intentos de acceso no autorizado

🎯 ¿Por qué es importante?

Pista de auditoría → Permite rastrear qué ocurrió y cuándo.

Cumplimiento normativo → Demuestra que la organización sigue regulaciones.

Análisis forense → Ayuda a investigar incidentes de seguridad, expertos de cyber intentan comprender exactamente qué ocurrió, cómo ocurrió y cómo evitar que se repitan incidentes.

Optimización de recursos → Permite ver cómo se usan sistemas y redes.

Responsabilidad → Los usuarios saben que sus acciones quedan registradas.

🛠 Herramientas comunes

- Servidores Syslog: Los servidores Syslog se van a utilizar para agregar registros de varios dispositivos y sistemas de red, de modo que los administradores de sistemas puedan analizarlos
para detectar patrones o anomalías en los sistemas de la organización. Se pueden utilizar analizadores de red como Wireshark para capturar y analizar el tráfico de red, de modo que los administradores de
red puedan obtener información detallada sobre todos los datos que se mueven por su red.

- Sistemas SIEM: un sistema de gestión de eventos e información de seguridad conocido como SIEM nos proporcionará un análisis en tiempo real de nuestras alertas de seguridad generadas
por diversas piezas de infraestructura de hardware y software dentro de nuestra organización.

# Categorias de Controles de Seguridad

La seguridad no se basa solo en tecnología. Para proteger una organización se utilizan 4 categorías de controles de seguridad, que trabajan en conjunto para reducir riesgos.

🔹 1. Controles Técnicos

Son herramientas tecnológicas que protegen automáticamente los sistemas.
Ejemplos:

- Firewalls

- Antivirus

- Cifrado

- IDS/IPS

👉 Funcionan a nivel de hardware y software.

🔹 2. Controles de Gestión (Administrativos)

Se enfocan en la estrategia y gobernanza de la seguridad.
Incluyen:

- Políticas de seguridad

- Evaluaciones de riesgo

- Planes de respuesta a incidentes

- Programas de capacitación

👉 Definen cómo la organización maneja el riesgo.

🔹 3. Controles Operativos

Son procedimientos del día a día ejecutados por personas.
Ejemplos:

- Cambios periódicos de contraseña

- Copias de seguridad

- Revisión de cuentas

👉 Mantienen la seguridad activa continuamente.

🔹 4. Controles Físicos

Protegen los activos en el mundo real (para inpedir el acceso fisico).
Ejemplos:

- Cámaras

- Guardias

- Cerraduras

- Acceso biométrico

👉 Evitan accesos físicos no autorizados.

📌 En Security+:
La clave es entender que la seguridad es multicapa: técnica, estratégica, operativa y física.

# Tipos de Controles de Seguridad

Para proteger una organización existen 6 tipos de controles de seguridad, cada uno con una función específica:

Preventivos → Evitan que ocurra el incidente.
Ej: firewall que bloquea tráfico malicioso.

Disuasorios → Desaniman al atacante mostrando que hay vigilancia.
Ej: carteles de monitoreo o banners de advertencia.

Detectivos → Detectan y alertan cuando ocurre algo sospechoso.
Ej: IDS o cámaras de seguridad.

Correctivos → Actúan después de detectar un problema para mitigarlo y restaurar el sistema.
Ej: antivirus que elimina malware.

Compensatorios → Alternativas cuando el control ideal no puede aplicarse.
Ej: usar VPN junto con WPA2 si no se puede implementar WPA3.

Directivos → Guían el comportamiento/proceso mediante políticas y normas.
Ej: Política de Uso Aceptable (PUA).

📌 Idea clave:
Cada tipo cumple un rol distinto, pero juntos crean una estrategia de seguridad sólida y equilibrada.

# Análisis de Carencias (Gap Analysis)

Un análisis de carencias es un proceso que compara:

📍 Estado actual de la organización
🎯 Estado deseado

Su objetivo es identificar qué falta para cerrar esa brecha y mejorar el rendimiento o la seguridad.

🧩 Pasos principales:

- Definir el alcance y objetivos.

- Recopilar datos del estado actual.

- Identificar las diferencias.

- Crear un plan con metas y plazos para cerrar la brecha.

☁️ Ejemplo práctico

Si una empresa migra a la nube (ej: AWS o Azure), puede descubrir que:

Su cifrado es obsoleto. Sus controles de acceso no encajan con el modelo IAM de la nube, y su infraestructura no soporta nuevas exigencias de seguridad, entonces se crea
un plan para actualizar sistemas y procesos.

🔍 Tipos de análisis de carencias:

Técnico → Evalúa infraestructura, red, cifrado, seguridad.

Empresarial → Evalúa procesos, gestión, presupuesto y operaciones.

Se usa mucho en:

Gestión de vulnerabilidades

Planes de acción (POA&M)

Migraciones a la nube

Mejora continua de seguridad

Un análisis de carencias permite planificar cómo pasar del estado actual al deseado de forma estructurada, priorizando riesgos y mejoras.
