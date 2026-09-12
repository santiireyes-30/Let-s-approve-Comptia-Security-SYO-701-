# Técnicas de Seguridad

Esta sección de **CompTIA Security+** trata sobre la aplicación de técnicas de seguridad para proteger recursos informáticos.

#### Cubriremos los siguientes objetivos

- **Objetivo 4.1:** Aplicar técnicas de seguridad comunes a los recursos informáticos según un escenario.
- **Objetivo 4.5:** Modificar las capacidades de una empresa para mejorar su seguridad.

---

## 1. Seguridad inalámbrica

Se estudia cómo proteger las redes inalámbricas mediante:

- **WPA3**
- **AAA** (Authentication, Authorization and Accounting)
- **RADIUS**
- Protocolos criptográficos
- Protocolos de autenticación

---

## 2. Seguridad de aplicaciones

Técnicas utilizadas para proteger las aplicaciones:

- **Validación de entradas:** comprobar que los datos recibidos sean válidos y seguros.
- **Cookies seguras:** proteger las cookies mediante mecanismos como `Secure` y `HttpOnly`.
- **Análisis estático de codigo (SAST):** analizar el código fuente sin ejecutarlo.
- **Análisis dinámico de codigo (DAST):** analizar una aplicación mientras está ejecutándose.
- **Firma de código:** verificar la autenticidad e integridad del software.
- **Sandboxing:** ejecutar aplicaciones o código en un entorno aislado para limitar sus acciones.

---

## 3. NAC — Network Access Control

**NAC (Network Access Control)** controla qué **usuarios y dispositivos** pueden acceder a los recursos de una red.

Su objetivo es aplicar políticas de seguridad y restringir el acceso a dispositivos o usuarios que no cumplan determinados requisitos.

---

## 4. Filtrado Web y DNS

Se utilizan diferentes técnicas para controlar y bloquear contenido o sitios potencialmente peligrosos:

- Filtros basados en agentes
- Proxies centralizados
- Escaneo de URLs
- Categorización de contenido
- Reglas de bloqueo
- Reputación de dominios y URLs

---

## 5. Seguridad del correo electrónico

Principales mecanismos:

- **SPF:** verifica qué servidores están autorizados para enviar correos de un dominio.
- **DKIM:** utiliza una firma criptográfica para verificar la autenticidad e integridad del correo.
- **DMARC:** establece políticas para los correos que no superan las comprobaciones de SPF o DKIM.
- **Filtros antispam:** identifican y bloquean correos no deseados o potencialmente maliciosos.

---

## 6. EDR — Endpoint Detection and Response

**EDR** es una tecnología de ciberseguridad que supervisa continuamente los dispositivos **endpoint**, como:

- Computadoras
- Smartphones
- Tablets

Recopila información para:

- Detectar amenazas
- Investigar incidentes
- Responder ante amenazas
- Prevenir ataques

---

## 7. UBA — User Behavior Analytics

**UBA (User Behavior Analytics)** analiza el comportamiento de los usuarios para detectar actividades anómalas o potencialmente maliciosas.

El sistema:

1. Establece una **línea base** del comportamiento normal.
2. Analiza las actividades de los usuarios.
3. Detecta desviaciones respecto al comportamiento habitual.
4. Puede generar alertas ante comportamientos sospechosos.

Puede utilizar **análisis de datos y Machine Learning** para identificar anomalías.

---

## 8. Selección de protocolos seguros

Se estudia cómo seleccionar protocolos y métodos de transporte que proporcionen una comunicación segura.

La elección del protocolo debe tener en cuenta factores como:

- Seguridad
- Cifrado
- Autenticación
- Integridad de los datos
- Método de transporte

---

## Idea principal

El objetivo de esta sección es aprender a **seleccionar y aplicar técnicas de seguridad según un escenario**.

Las principales técnicas estudiadas son:

**Seguridad inalámbrica → Seguridad de aplicaciones → NAC → Filtrado Web/DNS → Seguridad del correo → EDR → UBA → Protocolos seguros**

# Seguridad de la Infraestructura Inalámbrica

La seguridad de una red inalámbrica depende tanto de su **configuración** como de la **ubicación física de los puntos de acceso (WAP)**.

## 1. Ubicación de los WAP

Un **WAP (Wireless Access Point)** permite conectar dispositivos inalámbricos a una red cableada mediante Wi-Fi 802.11.

La ubicación del WAP afecta:

- Alcance de la señal.
- Cobertura.
- Intensidad de la señal.
- Rendimiento.
- Seguridad.

### Recomendaciones

- Colocar los WAP cerca del **centro del edificio**.
- Evitar colocarlos cerca de **ventanas y paredes exteriores**.
- Instalar los WAP en lugares elevados, como techos o estanterías.
- Evitar que la señal se extienda innecesariamente fuera del edificio.

### Riesgo de una mala ubicación

Hay que tener en cuenta estas 3 cosas a la hora de colocar: el alcance, la cobertura y la intensidad de la señal de la red inalámbrica

Si un WAP está cerca de una pared exterior o ventana, la señal puede llegar al exterior.

**Ejemplo:** un atacante podría estacionar un vehículo en el aparcamiento y conectarse a la red desde fuera del edificio si la señal inalámbrica llega hasta allí.

### Antenas

- **Omnidireccional:** transmite la señal en todas las direcciones, aproximadamente 360°.
- **Unidireccional:** concentra la señal en una dirección específica.

Si un WAP debe colocarse cerca de una pared exterior, una **antena unidireccional** puede utilizarse para dirigir la señal hacia el interior del edificio.

---

## 2. ESS — Extended Service Set

En edificios grandes, un único WAP puede no proporcionar suficiente cobertura.

Un **ESS (Extended Service Set)** utiliza varios WAP que trabajan juntos para proporcionar una zona de cobertura más amplia.

Esto permite que un usuario se desplace por el edificio y cambie automáticamente de un WAP a otro manteniéndose conectado a la misma red.

---

## 3. Interferencias inalámbricas

Cuando se utilizan varios WAP, es necesario planificar correctamente los canales para evitar interferencias.

### Interferencia cocanal

Ocurre cuando dos WAP tienen áreas de cobertura solapadas y utilizan el **mismo canal y misma zona o bandas de frecuencias para crear sus áreas de coberturas**.

Esto puede provocar:

- Colisiones/interferencias.
- Retransmisión de datos.
- Mayor tráfico.
- Menor rendimiento de la red.

### Interferencia de canal adyacente

Ocurre cuando WAP cercanos utilizan **canales demasiado próximos**, provocando que sus frecuencias se superpongan.

Esto puede causar:

- Errores de transmisión.
- Pérdida de ancho de banda.
- Menor rendimiento.

En términos sencillos, significa que el Wi-Fi de tus vecinos está chocando con el tuyo porque están usando canales de transmisión que se "pisan" entre sí.
Para entenderlo mejor, imagina que las frecuencias de Wi-Fi son como carriles en una autopista:
Un WAP (punto de acceso inalámbrico o router) transmite su señal por un carril específico. Si dos routers cercanos eligen carriles que están demasiado pegados, los autos (los datos) se rozan y chocan entre sí.

### Canales 1, 6 y 11

En la banda de **2,4 GHz**, los canales se superponen debido a que tienen un ancho de banda considerable respecto al espectro disponible.

Por eso, normalmente se utilizan los canales:

**1 → 6 → 11**

Estos canales están suficientemente separados para evitar la superposición entre ellos.

> **Regla importante:** En redes Wi-Fi de 2,4 GHz, utilizar los canales **1, 6 y 11** ayuda a minimizar las interferencias.

---

## 4. Site Survey — Estudio del emplazamiento

Un **Site Survey** es un estudio realizado para planificar y diseñar correctamente una red inalámbrica.

Permite analizar:

- Cobertura.
- Capacidad de la red.
- Capacidad de roaming.
- Calidad del servicio (QoS).
- Interferencias de radiofrecuencia (RF).
- Ubicación óptima de los WAP.
- Redes inalámbricas existentes.

Durante el estudio se escanean las ondas de radio para detectar otros dispositivos o redes que puedan causar interferencias.

---

## 5. Heat Map — Mapa de calor

Un **Heat Map** es una representación gráfica de la cobertura inalámbrica.

Utiliza diferentes colores para mostrar información como:

- Intensidad de la señal.
- Cobertura.
- Utilización de frecuencias.
- Zonas con señal débil o inexistente.
- Zonas con señal excesivamente fuerte.
- Señal que se filtra fuera del edificio.

### ¿Para qué sirve?

Permite identificar:

- **Zonas muertas:** áreas sin suficiente cobertura.
- **Señal demasiado fuerte:** puede indicar una cobertura innecesariamente amplia.
- **Interferencias:** zonas donde existen problemas de señal.
- **Signal leakage:** señal que se extiende fuera de las instalaciones.

---

## 6. Ejemplo de implementación

Una empresa quiere instalar una nueva red Wi-Fi.

### Paso 1 — Site Survey

Se analiza el edificio para determinar:

- Dónde colocar los WAP.
- Qué redes inalámbricas existen cerca.
- Qué interferencias existen.
- Qué canales pueden utilizarse.

### Paso 2 — Instalación

Se colocan los WAP en ubicaciones adecuadas, preferentemente:

- En zonas centrales.
- En lugares elevados.
- Alejados de ventanas y paredes exteriores.

### Paso 3 — Heat Map

Después de instalar los WAP, se crea un mapa de calor para comprobar la cobertura real.

Si la señal es demasiado débil en los bordes:

→ Se pueden agregar WAP adicionales.

Si la señal se filtra fuera del edificio:

→ Se pueden reposicionar los WAP.  
→ Reducir la potencia de transmisión.  
→ Utilizar antenas unidireccionales.

---

## Conceptos clave

| Concepto | Función |
|---|---|
| **WAP** | Permite conectar dispositivos Wi-Fi a una red cableada |
| **Omnidireccional** | Transmite en todas las direcciones |
| **Unidireccional** | Concentra la señal en una dirección |
| **ESS** | Combina varios WAP para ampliar la cobertura |
| **Interferencia cocanal** | WAP cercanos utilizan el mismo canal |
| **Interferencia de canal adyacente** | WAP utilizan canales demasiado próximos |
| **Canales 1, 6 y 11** | Canales normalmente utilizados en 2,4 GHz para reducir solapamiento |
| **Site Survey** | Estudia el entorno antes de diseñar/instalar la red |
| **Heat Map** | Representa visualmente la cobertura e intensidad de la señal |
| **Signal leakage** | Señal inalámbrica que se extiende fuera de las instalaciones |

## Idea principal

**Una red inalámbrica segura no depende únicamente del cifrado o la autenticación. También es importante controlar físicamente dónde llega la señal.**

# Configuración de Seguridad Inalámbrica

La seguridad inalámbrica busca proteger los **datos transmitidos**, controlar quién puede acceder a la red y evitar accesos no autorizados.

## 1. Protocolos de cifrado inalámbrico

El cifrado proporciona **confidencialidad**, haciendo que los datos interceptados sean ilegibles. Así que tenemos que ver la importancia de utilizar la configuración de seguridad
inalámbrica correcta, incluyendo el uso de WPA3 u otras formas de cifrado inalámbrico, AAA y RADIUS para crear capas adicionales de autenticación en una red, y el uso del Protocolo
de Autenticación Extensible conocido como EAP.

### WEP

**WEP (Wired Equivalent Privacy)** es un protocolo antiguo y **obsoleto**.

- Utiliza claves estáticas.
- Utiliza **RC4**.
- Tiene un vector de inicialización (IV) débil de **24 bits**.
- Puede ser vulnerado fácilmente mediante ataques criptográficos.

> ❌ **WEP no debe utilizarse.**

### WPA

**WPA (Wi-Fi Protected Access)** fue creado como reemplazo de WEP.

- Introdujo **TKIP**.
- Generaba claves dinámicas para los paquetes.
- Mejoró la seguridad respecto a WEP.
- Sin embargo, heredó vulnerabilidades y TKIP también resultó inseguro.

> ❌ **WPA tampoco se considera seguro actualmente.**

### WPA2

**WPA2** reemplazó WPA y proporcionó una seguridad mucho mayor.

- Sustituyó TKIP por **AES**.
- Utiliza **CCMP** para proteger los datos.
- Incluye mecanismos de integridad como **MIC/Código de integridad de mensajes**.
- Aun así, presentó vulnerabilidades como **KRACK**.

> ⚠️ WPA2 es mucho más seguro que WEP/WPA, pero **WPA3 es la opción moderna preferida** cuando está disponible.

### WPA3

**WPA3 (Wi-Fi Protected Access 3)** es la versión más moderna y segura de WPA.

Principales mejoras:

- **SAE (Simultaneous Authentication of Equals)**: inmunes a los ataques de fuerza bruta y de diccionario, incluso si usas una contraseña débil.
- **Enhanced Open / OWE**: Enhanced Open mejora la privacidad y la seguridad del usuario, ya que lo protege de los ataques pasivos de escucha que son habituales
en los escenarios Wi-Fi públicos. Aunque no ofrece una seguridad completa como WPA3, Enhanced Open ayuda a garantizar que la conexión entre clientes y puntos de acceso esté cifrada.
Enhanced Open también proporciona una conexión más segura que las redes abiertas tradicionales, por lo que es una función valiosa para los proveedores de redes que ofrecen servicios Wi-Fi públicos a
sus usuarios finales.
- Protocolos criptográficos actualizados(AES): GCMP o protocolo Galois Counter Mode. Este protocolo no sólo admite el algoritmo AES de 128 bits para sus redes personales, sino que
también admite un AES de 192 bits para el uso de redes empresariales o personales con el protocolo WPA3.
- **Protected Management Frames (PMF/Protección de tramas de gestión)**: Es necesario utilizar estos marcos de protección de gestión para salvaguardar su red contra ataques de recuperación de claves. Garantiza la integridad
del tráfico de tutoría de la red al impedir las escuchas, la falsificación o el templado con este tipo de tramas, que son fundamentales para la gestión y el mantenimiento general de las comunicaciones inalámbricas.

---

## 2. Características de WPA3

### SAE

**SAE (Simultaneous Authentication of Equals)** reemplaza el antiguo método de clave precompartida utilizado en WPA2.

Utiliza un mecanismo basado en **Diffie-Hellman**.

Su principal ventaja es proporcionar mayor protección contra **ataques de diccionario offline**.

> Si un atacante captura el intercambio de autenticación, no puede utilizarlo de la misma forma que en WPA2 para probar contraseñas offline.

### Enhanced Open / OWE

**OWE (Opportunistic Wireless Encryption)** permite cifrar las comunicaciones incluso en redes Wi-Fi abiertas.

En una red Wi-Fi abierta tradicional:

**Dispositivo → datos sin cifrar → WAP**

Con OWE:

**Dispositivo → datos cifrados → WAP**

Esto mejora la privacidad frente a ataques de **escucha pasiva (sniffing)**.

> ⚠️ OWE cifra la comunicación, pero **no proporciona autenticación mediante contraseña**.

### AES-GCMP

WPA3 utiliza protocolos criptográficos modernos basados en **AES-GCMP**.

Puede utilizar:

- **AES-128** para determinados escenarios.
- **AES-192** en escenarios empresariales.

### Protected Management Frames

Los **Protected Management Frames (PMF)** protegen las tramas de gestión inalámbrica.

Ayudan a evitar que un atacante:

- Intercepte.
- Falsifique.
- Manipule.
- Utilice tramas de gestión para interrumpir las conexiones.

Esto ayuda a proteger contra determinados ataques de **denegación de servicio (DoS)** y otros ataques sobre la gestión de la red inalámbrica.

---

# 3. AAA

**AAA** significa:

- **Authentication:** ¿Quién eres?
- **Authorization:** ¿Qué puedes hacer?
- **Accounting:** ¿Qué hiciste?

Permite gestionar de forma centralizada el acceso de los usuarios a los recursos de la red.

---

## 4. RADIUS

**RADIUS (Remote Authentication Dial-In User Service)** proporciona servicios **AAA** mediante un modelo cliente-servidor.

Permite:

- Centralizar la autenticación.
- Verificar la identidad de los usuarios.
- Aplicar políticas de acceso.
- Registrar la actividad de los usuarios.

Es muy utilizado en **redes empresariales** y puede integrarse con infraestructuras Wi-Fi.

---

## 5. TACACS+

**TACACS+** también proporciona servicios AAA.

Una diferencia importante respecto a RADIUS es que separa:

**Authentication → Authorization → Accounting**

Esto permite un control más granular.

Además:

- Utiliza **TCP**.
- Protege mediante cifrado el proceso de autenticación.
- Es especialmente utilizado para **controlar el acceso administrativo a dispositivos de red**.

---

# 6. EAP

**EAP (Extensible Authentication Protocol/Protocolo de Autenticación Extensible)** es un **framework de autenticación**, no un método de autenticación único.

Permite utilizar diferentes métodos de autenticación, como:

- Certificados.
- Smart cards.
- Tokens.
- Credenciales.

Se utiliza especialmente en:

- Redes inalámbricas.
- Conexiones punto a punto.

---

## 7. PEAP

**PEAP (Protected Extensible Authentication Protocol)** encapsula EAP dentro de un **túnel TLS**.

Es un método para transportar datos de autenticación de forma segura a través de 802. 11 redes Wi-Fi(802.11 = estándar que permite la comunicación inalámbrica (Wi-Fi)). Esto permite proteger las credenciales durante la autenticación. 

**Idea clave:**

> PEAP = EAP protegido mediante un túnel TLS.

---

## 8. EAP-TTLS

**EAP-TTLS (EAP Tunneled Transport Layer Security)** también utiliza un túnel TLS para proteger la autenticación.

Una característica importante es que normalmente requiere un **certificado en el lado del servidor**, mientras que el cliente puede autenticarse mediante otro método dentro del túnel.

Cliente ───── 🔒 Túnel TLS 🔒 ───── Servidor
                                  📜 Certificado
---

#### Diferencia entre EAP-TTLS & PEAP 

La principal diferencia entre PEAP y EAP-TTLS es que EAP-TTLS requiere un certificado sólo en el lado del servicio, mientras que PEAP requiere una autenticación de certificado de doble cara tanto en el lado del servidor como
en el lado del cliente de la conexión.

Con EAP-TTLS, el protocolo encapsulará un segundo protocolo para la autenticación que se transporta dentro del túnel de cifrado TLS.

## 9. EAP-FAST

**EAP-FAST (Flexible Authentication via Secure Tunneling)** fue desarrollado por Cisco.

Permite:

- Crear un túnel TLS seguro.
- Proteger las credenciales.
- Facilitar la reautenticación de usuarios.
- Mejorar la movilidad dentro de la red.

Fue desarrollado como alternativa a **LEAP**, que presentaba vulnerabilidades.

---

### Resúmen Breve: 

Así que recuerde, a medida que las redes inalámbricas continúan expandiendo su popularidad, es importante que aprendamos las mejores formas de asegurar esas redes, incluyendo el uso de WPA3 u otras formas de encriptación
inalámbrica, **AAA y RADIUS para crear capas adicionales de autenticación en la red**, y el uso del Protocolo de Autenticación Extensible conocido como EAP.

WPA3 es la versión más reciente y segura del protocolo Wi-Fi Protected Access o WPA, y se utiliza para ofrecernos las protecciones más sólidas, incluso cuando los usuarios eligen contraseñas que no alcanzan las recomendaciones típicas
de complejidad.

RADIUS es un **protocolo de red** que proporciona una gestión centralizada de autenticación, autorización y contabilidad para los usuarios que se conectan y utilizan un servicio de red.
Mientras que TACACS+ es un protocolo independiente que permite un control más granular(control más específico y detallado), de la autenticación, autorización y contabilidad que ofrece cierta seguridad avanzada al cifrar todo el proceso de autenticación.

EAP o Protocolo de Autenticación Extensible es un marco de autenticación universal utilizado para admitir diversos métodos de autenticación, como tarjetas token, tarjetas inteligentes, certificados y otros, y redes inalámbricas y conexiones punto a punto.

Al adoptar estos protocolos y metodologías avanzados, podemos dotar a nuestras redes inalámbricas de una infraestructura más segura, diseñada para resistir a los modernos actores de amenazas, garantizando la protección tanto de la autenticidad del usuario como de la integridad
de los datos en nuestras redes inalámbricas.

## Comparación rápida

| Tecnología | Característica principal | Estado |
|---|---|---|
| **WEP** | RC4 + clave estática | ❌ Obsoleto |
| **WPA** | TKIP | ❌ Inseguro |
| **WPA2** | AES + CCMP | ⚠️ Mejor, pero reemplazado por WPA3 cuando es posible |
| **WPA3** | SAE + AES-GCMP + PMF | ✅ Recomendado |
| **RADIUS** | AAA centralizado | ✅ Muy utilizado |
| **TACACS+** | AAA separado y control granular | ✅ Muy utilizado |
| **EAP** | Framework de autenticación | ✅ |
| **PEAP** | EAP dentro de túnel TLS | ✅ |
| **EAP-TTLS** | Autenticación mediante túnel TLS | ✅ |
| **EAP-FAST** | Túnel TLS + credenciales protegidas | ✅ |

## 🧠 Para recordar

**WEP → WPA → WPA2 → WPA3**

La evolución fue aumentando la seguridad:

**WEP ❌ → WPA ❌ → WPA2 ⚠️ → WPA3 ✅**

Y para autenticación empresarial:

**AAA → RADIUS / TACACS+ → EAP**

**Site Survey → Instalación de WAP → Heat Map → Ajustes de cobertura y potencia**

# Seguridad de Aplicaciones

La **seguridad de aplicaciones** busca desarrollar software seguro desde su diseño, aplicando medidas para **prevenir, detectar y corregir vulnerabilidades**.

Las 6 áreas principales son:

---

## 1. Validación de entradas

Consiste en comprobar que los datos introducidos por un usuario o sistema sean **válidos, seguros y tengan el formato esperado** antes de procesarlos.

Ayuda a prevenir ataques como:

- **SQL Injection**
- **Cross-Site Scripting (XSS)**
- **Buffer Overflow**
- Otros ataques de inyección

No se trata sólo de prevenir ataques maliciosos, sino también de garantizar que nuestros sistemas se comporten de forma predecible y puedan gestionar los errores con elegancia.

Por ejemplo, si una función espera un valor numérico pero en su lugar recibe una cadena, podría provocar errores o un comportamiento impredecible. Una validación de entrada adecuada detecta 
estos problemas antes de que la aplicación intente realizar una operación con un tipo de datos incorrecto.

 ### Front-end vs Back-end

Sin embargo, la validación de entradas no sólo consiste en establecer límites, sino que también es una importante medida de seguridad para garantizar que los datos se validan en una fase temprana del proceso.
A esto lo llamamos validación front-end, en la que cualquier formulario web creado en una aplicación se asegurará de que los datos coinciden con el formato correcto antes de aceptarlos.

A la inversa, también aplicaremos la validación back-end para garantizar que nuestros servidores comprueban los datos antes de permitir que una aplicación los utilice.

- **Front-end:** valida los datos antes de enviarlos al servidor.
- **Back-end:** vuelve a validar los datos en el servidor.

> ⚠️ La validación del front-end puede ser evadida por un atacante, por lo que la validación del **back-end es fundamental**.

---

## 2. Cookies seguras

Las **cookies** son pequeños fragmentos de datos que el navegador web almacena en el ordenador del usuario mientras navega por un sitio web. 
Almacenan información entre el navegador y el servidor, por ejemplo información relacionada con una sesión.

Si no están protegidas pueden utilizarse para realizar **Session Hijacking** o robar información.

### Atributos importantes

- **Secure:** la cookie sólo se transmite mediante **HTTPS**.
- **HttpOnly:** impide que scripts del lado del cliente accedan directamente a la cookie.
- **SameSite:** controla cuándo se envía la cookie en solicitudes entre sitios y ayuda a reducir ataques como **CSRF**.

> 🔑 Una buena práctica es generar una nueva cookie de sesión después de una autenticación.

---

## 3. Análisis estático de código — SAST

**SAST (Static Application Security Testing)** analiza el **código fuente sin ejecutar la aplicación**.

Busca vulnerabilidades como:

- SQL Injection
- XSS
- Buffer Overflow
- Problemas de validación de entradas

### Revisión manual

También se puede revisar el código manualmente.

Es recomendable que lo revise **otro programador diferente al autor**, ya que puede detectar errores o suposiciones incorrectas que el desarrollador original no identificó.

> **SAST = analizar el código antes de ejecutarlo.**

---

## 4. Análisis dinámico de código — DAST

**DAST (Dynamic Application Security Testing)** analiza una aplicación **mientras está ejecutándose**.

Puede detectar problemas que no siempre son visibles mediante SAST, como:

- Errores en tiempo de ejecución.
- Fugas de memoria(reserva memoria y luego no la libera correctamente, haciendo que la memoria disponible se vaya agotando.
Ejemplo: una aplicación abre archivos continuamente pero nunca libera la memoria que utilizó → con el tiempo puede volverse lenta o bloquearse).
- Vulnerabilidades que aparecen al interactuar con la aplicación.

### Fuzzing

Consiste en introducir grandes cantidades de datos **aleatorios, inesperados o malformados** para intentar provocar:

- Fallos.
- Crashes.
- Excepciones.
- Fugas de memoria.

### Stress Testing

Somete al sistema a **cargas extremas** para comprobar:

- Estabilidad.
- Rendimiento.
- Puntos débiles.
- Capacidad de recuperación ante fallos.

> **DAST = analizar la aplicación mientras está funcionando.**

---

## 5. Firma de código

La **firma de código** permite verificar:

- **Autenticidad:** quién publicó el software.
- **Integridad:** si el código fue modificado después de ser firmado.

### Funcionamiento simplificado

1. El desarrollador genera un **hash** del archivo.
2. Firma ese hash con su **clave privada**.
3. El usuario recibe el software y su firma/certificado.
4. Se utiliza la **clave pública** para verificar la firma.

> ⚠️ Una firma válida **NO significa que el software sea completamente seguro o que no tenga vulnerabilidades**. Significa que podemos verificar su autenticidad e integridad desde que fue firmado.

---

## 6. Sandboxing

El **sandboxing** ejecuta programas o código en un **entorno aislado**.

Limita:

- Recursos a los que puede acceder.
- Cambios que puede realizar.
- Interacción con el sistema principal.

Esto permite ejecutar código potencialmente peligroso reduciendo el riesgo de que afecte al sistema anfitrión.

**Ejemplo:**

Un navegador puede ejecutar el código de una página web dentro de un entorno aislado para limitar el impacto de código malicioso.

---

## Resúmen breve

Así que recuerde, en el mundo de la seguridad de las aplicaciones, tenemos que considerar seis áreas clave, validación de entrada, cookies seguras, análisis de código estático, análisis de código dinámico,
firma de código y sandboxing.

La validación de entradas está diseñada para actuar como un guardián vigilante que garantiza que nuestras aplicaciones sólo procesan datos bien definidos y no contaminados para contrarrestar diversas formas de ataques.

Las cookies seguras ayudan a evitar vulnerabilidades como el secuestro de sesiones mediante la transmisión segura y el uso de la configuración de atributos adecuada en las cookies.

El análisis estático del código implica la detección proactiva de vulnerabilidades mediante la revisión del código fuente.

El análisis dinámico del código se utiliza para descubrir cualquier problema en tiempo de ejecución.

La firma de código proporciona un medio para verificar la autenticidad del software, y el sandboxing se utiliza para aislar cualquier código no fiable con el fin de mitigar su capacidad de causar daños potenciales.

Estas medidas de seguridad polifacéticas, cuando se integran en las prácticas de desarrollo de software, ayudan a crear una sólida estrategia de defensa contra el mundo en constante evolución de las amenazas a la ciberseguridad.

## Comparación rápida

| Técnica | ¿Qué hace? |
|---|---|
| **Validación de entradas** | Comprueba que los datos sean válidos y seguros |
| **Cookies seguras** | Protege información de sesión |
| **SAST** | Analiza el código sin ejecutarlo |
| **DAST** | Analiza la aplicación mientras se ejecuta |
| **Fuzzing** | Introduce datos aleatorios/malformados |
| **Stress Testing** | Prueba el sistema bajo cargas extremas |
| **Firma de código** | Verifica autenticidad e integridad |
| **Sandboxing** | Aísla código o aplicaciones potencialmente peligrosas |

##  Para recordar

**SAST = Static → código sin ejecutar**

**DAST = Dynamic → aplicación ejecutándose**

**Firma de código = ¿Quién lo firmó y fue modificado?**

**Sandbox = Aislar para limitar el daño**

**Validación de entrada = No confiar en los datos recibidos**

# Control de Acceso a la Red (NAC)

**NAC (Network Access Control)** controla qué dispositivos (ya sea conocidos o desconocidos, es decir dentro de la red interna o de otro lugar utilizando VPN), pueden acceder a una red según su **estado de seguridad** y determinadas reglas.

---

## ¿Cómo funciona el escaneo?

1. Un dispositivo intenta conectarse a la red.
2. NAC lo coloca temporalmente en una **zona de espera**.
3. Comprueba/Verifica su seguridad, por ejemplo:
   - Autenticación utilizando EAP.
   - Antivirus actualizado.
   - Parches de seguridad.
   - Configuraciones de seguridad.
4. Si cumple los requisitos → **accede a la red**.
5. Si no cumple → **cuarentena**, donde puede recibir actualizaciones y parches, pero no comunicarse libremente con la red.

---

**Las soluciones NAC pueden funcionar con Agentes persistentes o no persistentes.**

## Agentes NAC

### Agente persistente
- Software instalado permanentemente en el dispositivo.
- Adecuado para **equipos corporativos** controlados por la organización.

### Agente no persistente
- El agente se descarga temporalmente para realizar la inspección.
- Luego se elimina.
- Útil para **BYOD** (dispositivos personales), como en universidades.

---

## 802.1X

**IEEE 802.1X** es un estándar utilizado para implementar **control de acceso a la red basado en puertos**.

Es muy utilizado junto con soluciones NAC modernas.

---

## Factores para permitir o denegar acceso

NAC no sólo comprueba el estado de seguridad. También puede utilizar:

- **Tiempo:** permitir acceso sólo en determinados horarios.
- **Ubicación:** comprobar desde dónde se conecta el dispositivo.
- **Rol:** determinar si el dispositivo/usuario tiene permiso para realizar determinada acción.
- **Reglas:** combinar múltiples condiciones mediante lógica (`AND`, `OR`, etc.).

### NAC adaptativo
Reevalúa los permisos de un dispositivo según **lo que intenta hacer y su rol**.

---

## Resúmen breve

Así que recuerde, el control de acceso a la red o NAC se utiliza para proteger su red de dispositivos conocidos y desconocidos mediante el escaneo de cualquier dispositivo para determinar
su estado actual de seguridad antes de que se les permita el acceso a su red. Como puede ver, NAC es muy útil como parte de nuestra estrategia de defensa en profundidad y ayuda a imponer
una arquitectura de confianza cero dentro de nuestras redes.

## Para recordar

**NAC = inspeccionar → permitir o poner en cuarentena.**

Su objetivo es evitar que un dispositivo **inseguro o no autorizado** entre libremente en la red.

También ayuda a implementar una estrategia de **defensa en profundidad** y una arquitectura de **Zero Trust**.

# Filtrado Web y DNS

El **filtrado web y DNS** permite controlar el acceso de los usuarios a Internet para **bloquear sitios maliciosos, inapropiados o que distraigan**, aplicando las políticas de la organización.

---

## 1. Filtrado Web

Controla directamente el **contenido o los sitios web** a los que puede acceder un usuario.

### Principales métodos

- **Basado en agentes:** instala un software en cada dispositivo que aplica las políticas, incluso fuera de la red corporativa.
- **Proxy centralizado/Servidor proxy:** el usuario solicita acceder a una web → el **proxy analiza la solicitud** → permite o bloquea el acceso.
- **Escaneo de URL:** comprueba la URL contra bases de datos de sitios maliciosos conocidos.
- **Categorización de contenido:** clasifica sitios (redes sociales, apuestas, adultos, etc.) y permite bloquear categorías completas.
- **Reglas de bloqueo:** bloquea específicamente dominios, IPs o sitios determinados. Por ejemplo, un administrador de sistemas podría haber notado que había una cantidad significativa
de transferencia de datos desde su base web a un servidor de archivos desconocido en Internet. Esto podría ser un indicador de que alguien está exfiltrando tus datos sensibles y
enviándolos a un servidor remoto. Así que en este caso, el administrador del sistema podría querer añadir la dirección IP de su servidor de archivos remoto, para evitar cualquier
otra comunicación entre su red y la del posible atacante
- **Reputación:** bloquea sitios según una **puntuación de reputación** proporcionada por servicios externos. Si la base de datos revela que el sitio web tiene una puntuación de reputación baja,
debido a incidentes anteriores de intentos de suplantación de identidad y alojamiento de programas maliciosos, la solución de filtrado web bloqueará el acceso.

---

## 2. Filtrado DNS

Es una técnica utilizada para bloquear el acceso a determinados sitios web impidiendo la traducción de nombres de dominio específicos en sus correspondientes direcciones IP. Es decir,
Bloquea sitios **durante la resolución DNS**.

### Funcionamiento

1. El usuario solicita acceder a `ejemplo.com`.
2. El dispositivo consulta al **servidor DNS** para obtener su IP.
3. El DNS comprueba si el dominio está bloqueado.
4. Si está bloqueado → **no proporciona la dirección IP**.
5. Si está permitido → devuelve la IP y el usuario puede acceder al sitio.

> 🔑 **Filtrado Web:** controla el acceso/contenido web.  
> **Filtrado DNS:** bloquea la resolución de determinados dominios.

---

## Resúmen breve

Así que recuerda, el filtrado web y el filtrado DNS son dos herramientas importantes para garantizar un uso seguro y productivo de Internet. Al utilizar el filtrado web
y el filtrado DNS, su organización puede evitar que sus empleados accedan a sitios web maliciosos o que distraigan su atención, al tiempo que aplica las políticas de uso de
Internet de su organización.

El filtrado web puede estar basado en agentes o no, y puede implicar el escaneado de URL, la categorización de contenidos, reglas de bloqueo y filtrado basado en la reputación.
En lo que respecta al filtrado DNS, éste ayuda a evitar la traducción de nombres de dominio específicos a sus correspondientes direcciones IP, ya que DNS nos traduce la IP y a el atacante le va a resultar más
complejo el ataque, si se trata de un ataque DNS.

## Para recordar

**Web Filtering → "¿A qué sitios/contenidos puede acceder?"**

**DNS Filtering → "¿Este dominio puede resolverse a una IP?"**

# Seguridad del Correo Electrónico

La **seguridad del correo electrónico** utiliza diferentes mecanismos para proteger los mensajes, las cuentas y la infraestructura contra **phishing, spoofing, spam, malware y otros ataques**.

Concepto de Spoofing: técnica en la que un atacante suplanta la identidad de una entidad legítima

---

## 1. DKIM

**DKIM (DomainKeys Identified Mail)** agrega una **firma digital** a las cabeceras del correo.

Permite al receptor comprobar:
- Que el correo fue enviado por el **dominio que dice ser**.
- Que el mensaje **no fue modificado durante el tránsito**.

La clave pública puede validarse con una clave criptográfica(la firma), y se encuentra/publica en los **registros DNS** del dominio.

Por ejemplo, si alguien en diontraining.com envía un correo electrónico, el servidor receptor puede comprobar la firma DKIM con diontraining. com.

Si la firma digital coincide, esto confirma que el correo electrónico procede realmente de diontraining. com y que no ha sido modificado
durante el tránsito desde nuestro servicio a su servidor de correo electrónico. DKIM puede proporcionarnos numerosas ventajas, como la autenticación 
del correo electrónico, la protección contra la suplantación de identidad, la mejora de la capacidad de entrega y la mejora de la reputación.

> **DKIM = firma digital → autenticidad + integridad.**

---

## 2. SPF (Marco de Políticas de Remitente)

**SPF (Sender Policy Framework)**, es un método de autenticación de correo electrónico diseñado para evitar la falsificación de direcciones de remitente durante la entrega de correo electrónico. 
Verifica si el **servidor/IP que envía el correo está autorizado** para enviar mensajes en nombre de ese dominio.

La lista de IP autorizadas se publica en los **registros DNS**.

Si la IP no está autorizada, el correo puede ser marcado como spam o rechazado.

> **SPF = ¿Esta IP está autorizada para enviar correos de este dominio?**

Ventajes de aplicar SPF: 
- La prevención de la suplantación de identidad.
- La mejora de la entregabilidad del correo electrónico.
- La mejora de la reputación del dominio.

Por ejemplo, si alguien en diontraining. com envía un correo electrónico, el servidor de correo electrónico receptor comprobará primero si la dirección IP del remitente figura en el registro
SPF de diontraining. com antes de aceptarla.

Si la dirección IP no figura como autorizada en el marco de políticas del remitente, el correo electrónico se marcará como spam o será rechazado por el servidor de correo electrónico.

Si querés consultar públicamente los registros DNS de cualquier dominio, podés usar:

MXToolbox → busca registros A, MX, TXT, CNAME, SPF, etc.
Google Admin Toolbox Dig → muestra directamente las respuestas DNS.
Cloudflare DNS Lookup → consulta distintos tipos de registros DNS.

Por ejemplo, para ver el SPF de un dominio, buscás sus registros TXT.

---

## 3. DMARC

**DMARC**, sistema de validación que utiliza **SPF, DKIM o ambos** para ayudar a prevenir la suplantación de dominios.

El propietario del dominio establece qué hacer cuando un correo **falla las comprobaciones**, por ejemplo:
- Permitir.
- Marcar como spam.
- Rechazar.

El propósito principal de implementar DMARC es proteger un dominio de ser utilizado en ataques comprometidos de correo electrónico de negocios, correos electrónicos
de phishing, estafas de correo electrónico y otras actividades de amenazas de ciberseguridad.

> **DMARC = política sobre qué hacer cuando SPF/DKIM fallan.**

---

## 4. Pasarela de correo electrónico (Email Gateway)

Una **pasarela de correo** es el punto de **entrada y salida** entre Internet y la red de una organización. Las pasarelas de correo electrónico suelen
basarse en el protocolo simple de transferencia de correo o SMTP para enviar y recibir correos electrónicos. 

**Proceso**: Cuando se envía un correo electrónico, primeropasa por la pasarela de correo electrónico del remitente antes de enviarse por Internet. Una vez que el correo electrónico 
llega al dominio del destinatario, pasa por la pasarela de correo electrónico del destinatario antes de llegar a la bandeja de entrada del destinatario. Las pasarelas de correo electrónico se implantan 
para facilitar el enrutamiento, la seguridad, la aplicación de políticas y el cifrado y descifrado de los mensajes.

La pasarela puede analizar el correo antes de dejarlo pasar, tambien puede encargarse de:
- Enrutar correos.
- Detectar **spam, phishing y malware**.
- Aplicar políticas.
- Cifrar/descifrar mensajes.

Puede ser entre internet y red local:
- **Local (On-Primese Email Gateway):** infraestructura/Servidor fisico propio, el servidor es mío → tengo más control → yo lo mantengo..
- **Cloud:** proporcionada por un proveedor externo. Nos ofrecernos la mayor escalabilidad y facilidad de mantenimiento, pero su funcionamiento puede resultar más caro que el de una solución
in situ y, a la hora de determinar sus configuraciones exactas, estará limitado a las medidas de seguridad del proveedor de servicios en la nube.
- **Híbrida:** combinación de ambas.

---

## 5. Filtrado de Spam

Detecta y bloquea **correos no deseados o sospechosos**.

Puede analizar:
- Análisis del Contenido.
- Filtrado bayesiano: analiza las palabras y patrones del correo y calcula qué tan probable es que sea spam según experiencias anteriores.
- Lista de sumideros basada en DNS (DNS Sinkhole): hace que un dominio malicioso apunte a una dirección controlada en lugar de llevar al usuario al servidor malicioso. Así se puede bloquear o analizar la conexión.
- Reglas generales de filtrado: reglas definidas para permitir, bloquear o marcar correos según criterios como remitente, dominio, palabras, archivos adjuntos, etc.

Ejemplo para las 4 definiciones: Si un correo electrónico contiene palabras comúnmente asociadas con mensajes de spam como lotería, gratis, premio, u otros lenguajes de spam comúnmente utilizados, entonces
el filtro de spam de su red de empresa podría marcarlo como potencialmente spam y moverlo a la carpeta de spam.

---

## Resúmen breve: 

Así pues, recuerde que la seguridad del correo electrónico puede mejorarse utilizando diversas técnicas, como las configuraciones de DKIM, SPF, DMARC, protocolos de pasarela de correo electrónico y mecanismos de filtrado de spam.

DKIM se utiliza para añadir una firma digital a la cabecera del correo electrónico que puede utilizarse para validar al destinatario y garantizar que el correo electrónico no se ha modificado durante el tránsito.

SPF evita la falsificación de la dirección del remitente comprobando si la dirección IP del remitente está autorizada en los registros DNS del dominio.

DMARC es un protocolo que utiliza SPF y DKIM para determinar la autenticidad del mensaje de correo electrónico, permitiendo que el propietario de un dominio especifique cómo gestionar los correos electrónicos que no superen esa comprobación de
seguridad concreta.

Las pasarelas de correo electrónico sirven de punto de entrada y salida para todos los correos electrónicos de la empresa. Estas pasarelas de correo electrónico se implementan para ayudar con el enrutamiento del correo electrónico,
la seguridad del correo electrónico, la aplicación de políticas y el cifrado y descifrado de correos electrónicos. Y por último, también tenemos el filtrado de spam, que es una técnica para detectar y bloquear correos electrónicos no deseados
en función de varios criterios, como el contenido, la reputación del remitente y las preferencias del usuario.

## Comparación rápida

| Técnica | ¿Qué comprueba/hace? |
|---|---|
| **DKIM** | Firma digital → autenticidad e integridad |
| **SPF** | IP del remitente → ¿está autorizada? |
| **DMARC** | Define qué hacer si SPF/DKIM fallan |
| **Gateway** | Punto de entrada/salida y seguridad del correo |
| **Spam Filter** | Detecta y bloquea correos no deseados |

### 🔑 Para recordar

**DKIM → Firma**

**SPF → IP autorizada**

**DMARC → Política**

**Gateway → Entrada/salida**

**Spam Filter → Detectar/bloquear spam**

# Detección y Respuesta de Endpoints

## EDR

**EDR (Endpoint Detection and Response)** supervisa continuamente los **endpoints** (PC, notebooks, móviles, etc.) para detectar amenazas y responder ante ellas. Se basa
en gran medida en la supervisión de la integridad de los archivos.

### Proceso de EDR

1. **Recopilación de datos:** procesos del sistema, uso de la memoria, cambios de registro, patrones de tráfico de red, etc.

2. **Consolidación:** Definición breve: los datos se centralizan para analizarlos. Definición más completa: Una vez recopilados los datos, se envían a una solución de seguridad centralizada o a una base de datos para su análisis.
Esta base de datos podría estar ubicada en las instalaciones o en la nube, dependiendo de la solución específica de detección y respuesta de endpoints que utilice su organización.

3. **Detección de Amenzas:** busca amenazas mediante firmas, comportamiento anómalo o patrones conocidos.

4. **Alerta y respuesta a Amenazas:** genera alertas o realiza acciones automáticas, como **aislar un equipo de la red** para evitar que la amenaza se propague aún más por la red de la organización.

5. **Investigación de Amenzas:** proporciona información, eventos y datos forenses para determinar qué ocurrió, también proporcionan a sus equipos de seguridad las herramientas necesarias para investigar las amenazas.
Estas herramientas pueden incluir líneas temporales detalladas de la actividad

6. **Remediación/Corrección:** elimina archivos maliciosos, revierte cambios realizados y restaura los sistemas efectivos a su estado normal utilizando una línea de base segura.

> **EDR = monitorear → detectar → investigar → responder.**

Ya que mencionamos en el paso 4 aislar un equipo vamos a ver como es y su diferencia con poner en cuarentena un equipo...

- **Aislar un equipo:** cortar o limitar su comunicación con la red para evitar que la amenaza se propague. El equipo sigue encendido y funcionando.
- **Poner un equipo en cuarentena:** colocarlo en una red/zona restringida, donde tiene acceso muy limitado y normalmente sólo puede comunicarse con servicios necesarios para su reparación, actualización o análisis.

Ejemplo. Un EDR detecta malware en una PC:

Sin protección:
  - PC infectada → Red corporativa → otros equipos

Aislada:
  - PC infectada ✖── Red corporativa
  → Se corta su comunicación con otros equipos.

En cuarentena:
  - PC infectada → [RED DE CUARENTENA] → sólo servicios autorizados.

El objetivo principal de la solución de detección y respuesta de puntos finales es proporcionar datos de incidentes a nuestros analistas de ciberseguridad para ayudar a mejorar la supervisión de la seguridad, la
respuesta a incidentes y las investigaciones forenses que llevan a cabo en la red de su empresa.

Por ejemplo, una solución de detección y respuesta para puntos finales podría supervisar una red en busca de indicios de malware u otras ciberamenazas.

Si se detecta una amenaza, la solución de detección y respuesta de endpoints puede alertar al equipo de seguridad o emprender acciones predefinidas a partir de un libro
de jugadas utilizando la automatización y la orquestación para mitigar la amenaza identificada.

---

## FIM/Supervisión de la Integridad de los Archivos

**FIM (File Integrity Monitoring)** controla si los **archivos críticos fueron modificados**. 

Se utiliza para validar la integridad de los archivos de los sistemas operativos y del software de aplicación mediante un método de verificación
entre el estado actual del archivo y una línea de base buena y conocida. Esta comparación puede ayudar a identificar cambios en archivos críticos, incluidos archivos binarios, archivos de aplicaciones del sistema, así como archivos de configuración y parámetros.
Normalmente, un monitor de integridad de archivos utiliza una pequeña pieza de software conocida como agente para supervisar continuamente los archivos críticos del sistema en busca de cambios.

Funcionamiento:
- Se calcula el **hash** de un archivo conocido como seguro.
- Se guarda como referencia (**baseline**).
- Si el archivo cambia, su hash cambia.
- FIM genera una alerta para investigar el cambio.

> **FIM = detectar modificaciones no autorizadas en archivos.**

---

## XDR

**XDR (Extended Detection and Response)** amplía EDR y **correlaciona información de múltiples capas de seguridad**. Es decir, La detección y respuesta ampliadas o XDR es una estrategia
de seguridad que integra múltiples tecnologías de protección en una única plataforma para mejorar la precisión de la detección y simplificar el proceso de respuesta ante incidentes.

Como mencionamos antes se utilizan para recopilar y correlacionar automáticamente datos a través de múltiples capas de seguridad, incluyendo su correo electrónico, punto final, servidor, cargas de trabajo en la nube y redes,
de modo que cualquier amenaza pueda detectarse más rápidamente, y los analistas de seguridad puedan minimizar el tiempo necesario para responder a cualquier problema.

Al utilizar una solución de detección y respuesta ampliada, ya no necesita tener soluciones separadas para la seguridad de su red, la seguridad de su correo electrónico y la seguridad de sus puntos finales.

Puede integrar datos de:
- Endpoints.
- Red.
- Correo electrónico.
- Servidores.
- Cloud.

Esto permite detectar amenazas que afectan a **varios componentes al mismo tiempo** y responder más rápidamente.

> **XDR = EDR + red + correo + cloud + otras fuentes.**

---

**¿Cuál es la diferencia entre una solución de detección y respuesta de endpoints y una solución de detección y respuesta ampliada?** Bueno, la detección y respuesta de puntos finales se centra realmente en sus puntos finales, cosas como ordenadores, portátiles y dispositivos móviles.

Las soluciones de detección y respuesta para puntos finales pueden recopilar datos de estos puntos finales, analizarlos en busca de indicios de amenazas y responder a las amenazas detectadas. 

Por otro lado, la detección y respuesta ampliadas son una solución más completa que va mucho más allá de los puntos finales. La detección y respuesta ampliadas recopilan y correlacionan automáticamente los datos en varias capas de seguridad, incluidos los puntos finales, la red, la nube 
y el correo electrónico, para detectar y responder a cualquier amenaza identificada.

## Resúmen breve

Así pues, recuerde que la detección y respuesta de puntos finales es una herramienta de seguridad que supervisa los eventos de los puntos finales y de la red en busca de señales de amenazas que puedan enviar una alerta a un equipo de seguridad o tomar
medidas predefinidas para mitigar la amenaza en cuestión.

La detección y respuesta ampliadas, por su parte, es una estrategia de seguridad que integra múltiples tecnologías de protección en una única plataforma.

La supervisión de la integridad de los archivos(ya que un atacante puede introducir algún tipo de codigo malicioso en tu archivo), suele incluirse como parte de la solución EDR o XDR, ya que la supervisión de la integridad de los archivos se utiliza para validar la integridad de los archivos 
del sistema operativo y del software de aplicación.

Al comprender y aplicar estas herramientas, las organizaciones pueden mejorar significativamente su postura de seguridad y su resistencia frente a diversas ciberamenazas y tecnologías.

## EDR vs XDR vs FIM

| Tecnología | Enfoque principal |
|---|---|
| **EDR** | Detectar y responder a amenazas en endpoints |
| **FIM** | Detectar cambios en archivos |
| **XDR** | Correlacionar amenazas entre múltiples capas |

### Para recordar

**EDR → Endpoint**

**FIM → Archivos**

**XDR → Varias capas de seguridad**

# Análisis del Comportamiento del Usuario (UBA / UEBA)

El **UBA (User Behavior Analytics)** estan diseñado para analizar el comportamiento de los usuarios y para detectar **anomalías** que puedan indicar una amenaza de seguridad, como el tráfico
de red, los dispositivos de los usuarios y los registros de aplicaciones.

Utiliza:
- Técnicas Análiticas Avanzadas (ej: aprendizaje automático)
- **Big Data**
- **Machine Learning**
- Análisis estadístico (para crear una base de referencia del comportamiento normal de los usuarios.
- Datos de múltiples fuentes

---

## ¿Cómo funciona UBA?

1. **Recopila datos** de diferentes fuentes:
   - Tráfico de red.
   - Dispositivos de los usuarios.
   - Registros de aplicaciones.
   - Actividad de las cuentas.

2. **Aprende el comportamiento normal** de cada usuario.

3. Crea una **línea base (baseline)** del comportamiento habitual.

4. **Supervisa continuamente** la actividad.

5. Si detecta una desviación importante respecto al comportamiento normal → **genera una alerta** para que el equipo de seguridad investigue.

> 🔑 UBA no necesariamente significa que una actividad sea maliciosa. Detecta que es **anómala** y la marca para investigación.

---

## Ejemplos de anomalías

### Horario inusual

Un usuario normalmente inicia sesión durante el horario laboral.

De repente:
- Inicia sesión a las 3:00 AM.
- El sistema lo detecta como comportamiento anómalo.
- Se genera una alerta.

Esto podría ser:
- Una actividad legítima.
- Una cuenta comprometida.

---

### Acceso a información inusual

Un empleado normalmente accede a archivos relacionados con su trabajo.

De repente comienza a acceder a:
- Información financiera.
- Información de RR. HH.
- Archivos confidenciales.

→ UBA puede detectar la desviación y generar una alerta.

---

### Descarga masiva de información

Un usuario normalmente descarga pocos archivos.

De repente descarga **una gran cantidad de datos**.

→ Puede indicar un intento de **exfiltración de datos**.

---

### Cambio de comportamiento

Una cuenta normalmente sólo **lee datos**.

De repente comienza a:
- Modificar archivos.
- Eliminar información.
- Realizar acciones que normalmente no realiza.

→ Podría indicar que las **credenciales fueron comprometidas**.

---

## UBA vs UEBA

### UBA

**User Behavior Analytics**

Analiza principalmente el comportamiento de los **usuarios**.

### UEBA

**User and Entity Behavior Analytics**

Amplía UBA para analizar también **entidades**.

Ejemplos de entidades:
- Usuarios.
- Routers.
- Servidores.
- Endpoints.
- Otros dispositivos de la red.

> **UEBA = UBA + comportamiento de entidades.**

---

## Ventajas

### Detección temprana de amenazas
Detecta comportamientos anómalos antes de que una amenaza pueda causar un daño importante.

### Detección de amenazas internas
Ayuda a detectar empleados o cuentas que acceden a información que normalmente no deberían utilizar.

### Detección de cuentas comprometidas
Permite identificar cambios repentinos en el comportamiento de una cuenta.

### Mejora de la respuesta
Puede proporcionar información al equipo de seguridad y, en algunos casos, realizar acciones automáticas como **cerrar una sesión o bloquear una cuenta**, que quizo comprometer una credencial del usuario de la empresa.

---

## Resúmen breve

Así que recuerde, el análisis del comportamiento del usuario es una herramienta poderosa para detectar posibles amenazas a la seguridad mediante la identificación de comportamientos anómalos
que puedan indicar una amenaza. Es posible que oiga hablar de esta tecnología como UBA o UEBA.

El análisis del comportamiento del usuario, o UBA, es una estrategia avanzada de ciberseguridad que aprovecha el poder de los big data y el aprendizaje automático para analizar los comportamientos 
de los usuarios y detectar anomalías que puedan indicar posibles amenazas a la seguridad.

Cuando lo llamamos UEBA, nos referimos al análisis del comportamiento de usuarios y **entidades**, y añadimos la supervisión de entidades a nuestro análisis del comportamiento de usuarios.

Por tanto, no sólo incluimos nuestras cuentas de usuario, sino también dispositivos o entidades como routers, servidores y puntos finales de la red.

## Para recordar

**UBA → analiza el comportamiento de los usuarios.**

**UEBA → usuarios + entidades.**

**Baseline → comportamiento normal.**

**Anomalía → desviación respecto al comportamiento normal.**

**UBA no dice necesariamente "esto es un ataque" → dice "esto es inusual, investigarlo".**

**Ejemplo clave:**  
Usuario normalmente trabaja de día y accede a archivos comunes → de repente entra de madrugada y descarga miles de archivos → **UBA genera una alerta**.

# Selección de Protocolos Seguros

Para mejorar la seguridad de una red debemos seleccionar correctamente:

1. **Protocolos**
2. **Puertos**
3. **Método de transporte (TCP o UDP)**

---

## 1. Protocolos seguros

Un **protocolo** es un conjunto de reglas que permite transmitir datos entre dispositivos.

Siempre que sea posible, debemos utilizar protocolos que proporcionen **cifrado**, especialmente al transmitir información sensible o mediante redes no confiables como Internet.

### Protocolos inseguros vs seguros

| Inseguro | Seguro | Uso |
|---|---|---|
| **HTTP** | **HTTPS** | Navegación web |
| **FTP** | **SFTP** | Transferencia de archivos |
| **Telnet** | **SSH** | Administración remota |
| **SMTP** | **SMTPS** | Envío de correo |
| **POP3** | **POP3S** | Recepción de correo. POP3: permite recuperar mensajes de correo electrónico de un servidor de correo a través del puerto 110, pero si utilizas la versión encriptada de POP3S, en su lugar utilizarás el puerto 995 para recibir tus correos electrónicos. |
| **IMAP** | **IMAPS** | Acceso a correo, y IMAPS cifrará todos sus correos electrónicos antes de que los reciba a través del puerto 993. |
| **SNMP** | **SNMPS** | Administración de dispositivos |

### Ejemplo: HTTP vs HTTPS

**HTTP:** transmite datos sin cifrado → un atacante podría interceptarlos y leerlos.

**HTTPS:** cifra los datos → aunque sean interceptados, no pueden leerse fácilmente sin las claves adecuadas, es decir exepto el receptor del mensaje que es el que tiene la clave de desifrado adecuada.

### Ejemplo: Telnet vs SSH

**Telnet:** Es el protocolo de capa de aplicación que permite a un usuario de un ordenador conectarse a otro que forme parte de la misma red.

- No cifra la comunicación.
- Usuario y contraseña viajan en texto plano.
- Vulnerable a sniffing y ataques Man-in-the-Middle.

**SSH(Secure Shell):**
- Cifra la comunicación.
- Permite autenticación segura.
- Se utiliza para administración remota.

> 🔑 **Regla básica: elegir protocolos cifrados en lugar de versiones heredadas/inseguras. La mayoría de las veces, el protocolo simplemente añadirá una S al final del protocolo sin cifrar para indicar que se trata
de una versión más segura de ese protocolo..**

---

## 2. Selección de puertos

Un **puerto** identifica un servicio o proceso específico dentro de un sistema.

### Rangos de puertos

| Rango | Tipo | Uso habitual |
|---|---|---|
| **0–1023** | Conocidos | Servicios estándar |
| **1024–49151** | Registrados | Aplicaciones |
| **49152–65535** | Dinámicos/privados | Conexiones del cliente |

### Puertos importantes

| Servicio | Puerto |
|---|---:|
| HTTP | **80** |
| HTTPS | **443** |
| SMTP | **25** |
| SMTPS | **587** |
| POP3 | **110** |
| POP3S | **995** |
| IMAP | **143** |
| IMAPS | **993** |

> ⚠️ **Los números de puerto por sí solos no proporcionan seguridad.** La seguridad depende principalmente del protocolo y su configuración.

---

## Principio de mínimo privilegio

Se deben abrir **únicamente los puertos necesarios** para que un servicio funcione y bloquear los demás.

Esto permite:
- Reducir la **superficie de ataque**.
- Disminuir accesos no autorizados.
- Reducir posibles vectores de ataque.

---

## Puertos no estándar

Un administrador puede cambiar el puerto predeterminado de un servicio.

Ejemplo:

**HTTP → puerto 80**

Podría configurarse en:

**HTTP → puerto 8888**

Esto puede hacer que el servicio sea **menos predecible**, pero sólo proporciona una pequeña capa de **oscuridad**.

> ❌ Cambiar el puerto **NO reemplaza** el cifrado, una autenticación fuerte, actualizaciones ni otras medidas de seguridad.

---

## 3. Métodos de transporte: TCP vs UDP

### TCP

**TCP (Transmission Control Protocol)** es orientado a conexión.

Características:
- Establece una conexión antes de transmitir.
- Confirma la recepción de datos.
- Retransmite paquetes perdidos.
- Mantiene el orden de los datos.
- Prioriza la **integridad y confiabilidad**.

**Ejemplo:** navegación web y correo electrónico.

> **TCP = confiabilidad e integridad.**

---

### UDP

**UDP (User Datagram Protocol)** es sin conexión.

Características:
- No establece una conexión antes de enviar.
- No garantiza la entrega.
- No retransmite automáticamente paquetes perdidos.
- Tiene menor sobrecarga.
- Prioriza **velocidad y eficiencia**.

**Ejemplos:** streaming, videojuegos y comunicaciones en tiempo real.

> **UDP = velocidad, aceptando cierta pérdida de datos.**

---

## TCP vs UDP

| Característica | TCP | UDP |
|---|---|---|
| Conexión | Sí | No |
| Entrega garantizada | Sí | No |
| Retransmisión | Sí | No |
| Orden de paquetes | Sí | No garantiza |
| Velocidad | Menor | Mayor |
| Uso típico | Web, correo, archivos | Streaming, juegos, tiempo real |

---

##  Para recordar

**Protocolo → ¿Cómo se comunican los dispositivos?**

**Puerto → ¿Qué servicio/proceso estoy utilizando?**

**TCP → confiabilidad e integridad.**

**UDP → velocidad y eficiencia.**

**HTTPS > HTTP**

**SFTP > FTP**

**SSH > Telnet**

**Mínimo privilegio → abrir sólo los puertos necesarios.**

**Cambiar el puerto ≠ seguridad real.**
