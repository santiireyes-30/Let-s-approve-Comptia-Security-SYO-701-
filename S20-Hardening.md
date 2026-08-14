# Hardening (Endurecimiento)

El **hardening** es el proceso de **hacer un sistema, aplicación o red más seguros**, reduciendo su superficie de ataque y eliminando vulnerabilidades innecesarias.

## Introducción

## Medidas principales de hardening

### 1. Configuraciones por defecto
- Cambiar **contraseñas predeterminadas**.
- Cerrar **puertos abiertos innecesarios**.
- Modificar configuraciones inseguras de fábrica.

### 2. Restricción de aplicaciones (Application Whitelisting)
- Solo se permite ejecutar **aplicaciones autorizadas**.
- Todo lo demás se bloquea por defecto.

### 3. Servicios innecesarios
- Desactivar procesos o servicios que no se utilizan.
- Reduce vulnerabilidades y libera recursos.

### 4. Sistemas Operativos de Confianza (Trusted OS)
- Sistemas evaluados y certificados para manejar información sensible.
- Incorporan controles de seguridad más estrictos.

### 5. Actualizaciones y Parches
- **Actualización (Update):** añade mejoras, nuevas funciones o corrige errores.
- **Parche (Patch):** corrige una vulnerabilidad o problema de seguridad específico.

### 6. Gestión de Parches (Patch Management)
Proceso de:
1. Identificar parches.
2. Probarlos.
3. Implementar/Despegar.
4. Supervisarlos.

### 7. Políticas de Grupo (Group Policy - Windows)
- Las políticas de grupo son un conjunto de reglas y configuraciones en entornos Windows que permiten a los administradores gestionar y controlar de forma centralizada la configuración de usuarios
y equipos, garantizando el cumplimiento y la seguridad de sus normas operativas.

### 8. SELinux (Security-Enhanced Linux)
- Implementa **Control de Acceso Obligatorio (MAC)**.
- Limita las acciones de procesos y usuarios, incluso si una aplicación es comprometida.

Pero básicamente es un marco de seguridad para sistemas operativos basados en Linux que implementa controles de acceso obligatorios para confinar y limitar las acciones de procesos y usuarios con el fin de mejorar
la seguridad general del sistema.

### 9. Niveles de cifrado de datos
El cifrado de datos es el proceso de convertir datos en un código secreto para impedir el acceso no autorizado.

Protege la información convirtiéndola en un formato ilegible.

Puede aplicarse a:
- Disco completo.
- Partición.
- Volumen.
- Archivo.
- Base de datos.
- Registro (Record).

### 10. Línea Base Segura (Secure Baseline)
- Configuración estándar y segura de un sistema.
- Sirve como punto de partida para desplegar equipos con una configuración consistente y segura, es decir, minimiza riesgos y vulnerabilidades

---

## Resumen de Introducción

- **Hardening = reducir la superficie de ataque.**
- Cambiar configuraciones por defecto.
- Permitir solo aplicaciones autorizadas.
- Desactivar servicios innecesarios.
- Mantener el sistema actualizado y parchado.
- Administrar configuraciones mediante Group Policy o SELinux.
- Cifrar los datos.
- Implementar una Secure Baseline.

# Cambio de Configuraciones por Defecto (Default Configurations)

Cuando se instala un nuevo **hardware o software**, este viene con configuraciones predeterminadas (de fábrica). Estas configuraciones están pensadas para facilitar la instalación, **no para maximizar la seguridad**.

> **Problema:** Los atacantes conocen estas configuraciones por defecto y pueden aprovecharlas para comprometer el sistema.

---

## 1. Cambiar las contraseñas predeterminadas

Las **credenciales predeterminadas** son el usuario y contraseña configurados por el fabricante para el acceso inicial.

### Ejemplos comunes
- `admin / admin`
- `admin / password`
- `admin / (contraseña vacía)`

Como estas credenciales aparecen en los manuales o en Internet, **deben cambiarse inmediatamente**.

### Buenas prácticas
- Cambiar la contraseña al instalar el dispositivo.
- Utilizar una contraseña:
  - Larga.
  - Compleja.
  - Única.
- Habilitar **MFA (Autenticación Multifactor)** si está disponible.
- Rotar la contraseña aproximadamente cada **90 días**.
- Utilizar un **gestor de contraseñas** para almacenarlas de forma segura.

---

## 2. Desactivar puertos y protocolos innecesarios

Muchos dispositivos tienen servicios habilitados que realmente no se utilizan.

Cada **puerto abierto** representa una posible puerta de entrada para un atacante.

### Buenas prácticas
- Identificar qué puertos y protocolos son necesarios.
- Deshabilitar los que no se utilizan.
- Reducir la **superficie de ataque**.

### Siempre que sea posible, utilizar versiones seguras

| Inseguro | Seguro |
|----------|---------|
| HTTP (80) | HTTPS (443) |
| SMTP (25) | SMTPS (465 o 587) |

---

## 3. Cerrar puertos abiertos innecesarios

Muchos fabricantes dejan varios puertos abiertos para ofrecer mayor compatibilidad.

### Ejemplo

| Puerto | Servicio | Acción recomendada |
|---------|----------|--------------------|
| 22 | SSH | Mantener si se utiliza. |
| 23 | Telnet | **Cerrar** (no cifra la información). |
| 80 | HTTP | Cerrar si solo se usa HTTPS. |
| 443 | HTTPS | Mantener para comunicaciones seguras. |

### ¿Por qué cerrar Telnet?

Porque **Telnet transmite usuarios y contraseñas sin cifrar**, mientras que **SSH cifra toda la comunicación**.

---

### Objetivo

Reducir la **superficie de ataque**, eliminando configuraciones inseguras que vienen de fábrica.

---

## Resumen Breve

- Las configuraciones por defecto **priorizan la facilidad de uso, no la seguridad**.
- Cambiar inmediatamente las credenciales predeterminadas.
- Utilizar contraseñas largas, únicas y MFA.
- Desactivar puertos y protocolos innecesarios.
- Preferir protocolos cifrados:
  - HTTP → HTTPS.
  - SMTP → SMTPS.
- Cerrar puertos abiertos que no se utilicen (ej. Telnet - puerto 23).
- **Menos servicios activos = menor superficie de ataque = mayor seguridad.**

# Restricción de Aplicaciones (Application Restriction)

La **restricción de aplicaciones** consiste en controlar qué programas pueden ejecutarse en un sistema para reducir el riesgo de malware, software no autorizado y vulnerabilidades.

Su objetivo es aplicar el principio de **funcionalidad mínima**, donde un equipo solo dispone de las aplicaciones y servicios estrictamente necesarios.

---

## Funcionalidad mínima (Least Functionality)

Es el proceso de configurar una estación de trabajo o un servidor para que sólo proporcione las aplicaciones y servicios esenciales que va a necesitar ese usuario. Consiste en configurar un equipo para que solo tenga:

- Las aplicaciones necesarias.
- Los servicios necesarios.
- Los puertos necesarios.
- Los protocolos necesarios.

**Beneficios**
- Reduce la superficie de ataque.
- Disminuye las vulnerabilidades.
- Facilita la administración y aplicación de parches.

---

## Eliminar aplicaciones innecesarias

Cada programa instalado:

- Consume espacio en disco.
- Debe actualizarse.
- Debe parchearse.
- Puede contener vulnerabilidades.

Por ello, es recomendable:

- Desinstalar software que ya no se utilice.
- Eliminar versiones antiguas después de actualizar un programa.
- Mantener únicamente el software necesario.

---

## Línea Base Segura (Secure Baseline)

En redes empresariales se utiliza una **Secure Baseline**, que es una imagen estándar para todos los equipos.

Generalmente incluye:

- Sistema operativo.
- Aplicaciones necesarias.
- Configuración de seguridad.
- Políticas de la organización.

Esto garantiza que todos los equipos comiencen con la misma configuración segura.

#### Ejemplo

Supongamos que tú y yo queremos ir a una discoteca de moda este viernes por la noche. Nos presentamos en la puerta y nos recibió el portero.
Ahora el portero nos mira y pregunta: "¿Si estamos en la lista? Así que le doy mi nombre y le digo: "Hola, soy Jason Dion", y él mira la lista y se da cuenta de que no estoy en su
lista porque no estoy tan de moda.

Esto significa que no me dejará entrar en ese club. A lo mejor eres más guay que yo y tu nombre estaba en la lista, y si es así, te van a dejar entrar en el club.

Ahora bien, si cada uno de nosotros fuera considerado como una aplicación en un ordenador, este ejemplo de discoteca le muestra de qué estamos hablando
cuando hablamos de un concepto conocido como allowlisting.

---

## Restricción mediante Allowlisting y Blocklisting

Existen dos formas principales de controlar qué aplicaciones pueden ejecutarse.

### Allowlisting (Lista de Permitidos)

Solo pueden ejecutarse las aplicaciones que aparecen en la lista autorizada.

Todo lo demás queda bloqueado.

#### Funcionamiento

```text
¿La aplicación está en la lista?

Sí → Se ejecuta.
No → Se bloquea.
```

#### Ventajas

- Máxima seguridad.
- Bloquea malware desconocido.
- Evita instalaciones no autorizadas.

#### Desventajas

- Mayor administración.
- Debe actualizarse cuando cambian las aplicaciones.

---

## Blocklisting (Lista de Bloqueados)

Solo se bloquean las aplicaciones incluidas en la lista.

Todo lo demás puede ejecutarse.

### Funcionamiento

```text
¿La aplicación está en la lista negra?

Sí → Se bloquea.
No → Se ejecuta.
```

### Ventajas

- Fácil de implementar.
- Menor mantenimiento.

### Desventajas

- Menos seguro.
- El malware nuevo podrá ejecutarse hasta que sea agregado a la lista.

---

## Comparación

| Allowlisting | Blocklisting |
|--------------|--------------|
| Todo bloqueado por defecto. | Todo permitido por defecto. |
| Solo se ejecuta lo autorizado. | Solo se bloquea lo conocido. |
| Más seguro. | Menos seguro. |
| Mayor administración. | Menor administración. |

---

## Administración en empresas

En entornos Windows con **Active Directory**, estas listas pueden administrarse de forma centralizada mediante **Group Policy (GPO)**.

Esto permite aplicar las mismas reglas a miles de equipos sin configurarlos uno por uno.

---

## Resumen breve

- **Restricción de aplicaciones:** controla qué programas pueden ejecutarse.
- **Funcionalidad mínima:** instalar únicamente lo necesario.
- Desinstalar aplicaciones y versiones antiguas para reducir vulnerabilidades.
- Utilizar una **Secure Baseline** para estandarizar la configuración de todos los equipos.
- **Allowlisting:** solo se ejecuta lo autorizado (**más seguro**).
- **Blocklisting:** solo se bloquea lo conocido (**menos seguro**).
- En Windows, estas políticas pueden administrarse mediante **Active Directory + Group Policy**.

# Servicios innecesarios

Los **servicios** son un tipo de aplicacion que se ejecuta en segundo plano en el sistema operativo y realiza diversas funciones, como la cola de impresión. Los servicios que no sean necesarios deben desactivarse en el sistema operativo.

## ¿Por qué deshabilitar servicios?

- Reducen la **superficie de ataque**.
- Consumen recursos innecesarios.
- Pueden introducir vulnerabilidades.
- Algunos malware se ejecutan como servicios.

> **Principio:** mantener únicamente los servicios necesarios (**mínima funcionalidad**).

## En Windows

Los servicios pueden administrarse desde:

- `services.msc`
- Símbolo del sistema (CMD)

Cada servicio muestra:

- Nombre.
- Descripción.
- Estado (ejecutándose o detenido).
- Tipo de inicio:
  - Automático.
  - Manual.
  - Deshabilitado.

### Ejemplo

El servicio **Windows Update (wuauserv)** puede deshabilitarse en organizaciones que utilizan un sistema centralizado de **gestión de parches**, evitando que cada equipo descargue actualizaciones directamente desde Microsoft.

Pasos:

1. Detener el servicio.
2. Cambiar el tipo de inicio a **Deshabilitado**.
3. Aplicar los cambios.

> Esto evita que el servicio vuelva a iniciarse al reiniciar el equipo.

### Comandos útiles

Detener un servicio:

```cmd
sc stop <nombre_del_servicio>
```

Ejemplo:

```cmd
sc stop wuauserv
```

O utilizando:

```cmd
net stop <nombre_del_servicio>
```

Ejemplo:

```cmd
net stop wuauserv
```

## En macOS

Los procesos pueden administrarse mediante:

- **Activity Monitor (Monitor de Actividad)**

Permite:

- Ver procesos en ejecución.
- Ver uso de memoria.
- Consultar archivos y puertos utilizados.
- Finalizar o forzar la salida de un proceso.

## En Linux y macOS (Terminal)

Ver procesos activos:

```bash
top
```

Finalizar un proceso:

```bash
kill <PID>
```

Ejemplo:

```bash
kill 2513 (numero ID del proceso que queremos matar)
```

Donde **PID (Process ID)** es el identificador único del proceso.

## Idea clave

- Mantener **solo los servicios necesarios**.
- Deshabilitar servicios innecesarios para reducir riesgos.
- Si un malware se ejecuta como servicio, primero puede **detenerse** y **deshabilitarse** antes de eliminarlo.
- En Windows se utilizan herramientas como **services.msc**, `sc stop` o `net stop`.
- En Linux/macOS se utilizan comandos como `top` y `kill`.

# Sistemas Operativos de Confianza (Trusted Operating Systems - TOS)

Un **Sistema Operativo de Confianza (TOS)** es un sistema operativo diseñado para ofrecer un **entorno altamente seguro**, aplicando estrictas políticas de seguridad, generalmente mediante **Control de Acceso Obligatorio (MAC)**.

Se utilizan en entornos donde la **confidencialidad, integridad y disponibilidad** de los datos son críticas, como sistemas militares, aeronáuticos, médicos e industriales.

## Características principales

- Implementan **Control de Acceso Obligatorio (MAC)**.
- Aplican políticas de seguridad definidas por el administrador.
- Incluyen auditoría de seguridad.
- Pueden utilizar **Control de Acceso Basado en Roles (RBAC)**.
- Reducen la superficie de ataque mediante una **Base Informática de Confianza (TCB)** mínima.

## Control de Acceso Obligatorio (MAC)

En un sistema **MAC**, el sistema operativo decide quién puede acceder a cada recurso según políticas establecidas por los administradores.

A diferencia del **DAC (Control de Acceso Discrecional)**, el propietario de un archivo **no puede modificar los permisos** para otorgar más acceso.

> **Objetivo:** impedir accesos no autorizados incluso por parte del propietario de los datos.

| **DAC (Discretionary Access Control)** | **MAC (Mandatory Access Control)** |
|----------------------------------------|------------------------------------|
| **El propietario del recurso decide quién accede.** | **El sistema operativo decide quién accede.** |
| El propietario **puede cambiar los permisos**. | El propietario **NO puede cambiar los permisos**. |
| Más flexible. | Más seguro y estricto. |
| Se basa en la decisión del propietario del recurso. | Se basa en políticas definidas por el administrador del sistema. |
| Ejemplo: Windows, Linux y macOS (por defecto). | Ejemplo: SELinux, Trusted Solaris, sistemas militares. |

## Common Criteria y niveles EAL

Los **Common Criteria** se utilizan para evalúar la seguridad y la eficacia de un sistema operativo y de los controles de seguridad mediante los **Evaluation Assurance Levels (EAL)**.

- **EAL1:** nivel más bajo de garantía.
- **EAL4 / EAL4+:** diseño, pruebas y revisión metódica (nivel utilizado por la mayoría de sistemas comerciales).
- **EAL6:** muy alta garantía para sistemas críticos.
- **EAL7:** máximo nivel de garantía.

### Ejemplos

- **Integrity-178B**
  - Utilizado en aeronaves militares y comerciales.
  - Clasificación **EAL6**.
  - Empleado en aviones como F-16, F-22, F-35, B-2 y Airbus A380.

- **SELinux (Security-Enhanced Linux)**

Ahora, SELinux se utiliza como una implementación de MAC en el núcleo de Linux para garantizar que las aplicaciones y los usuarios sólo tengan el acceso mínimo necesario a sus recursos. SELinux utiliza políticas para hacer cumplir las propiedades de seguridad
y puede confinar("Confinar = aislar o limitar algo para que no pueda afectar al resto del sistema"), procesos potencialmente dañinos para limitar el impacto de las vulnerabilidades. Veamos algunas caracteristicas:

  - Implementa **MAC** sobre distribuciones Linux.
  - Clasificación aproximada **EAL4+**.
  - Restringe aplicaciones y usuarios al **mínimo privilegio**.
  - Puede aislar procesos potencialmente peligrosos.

- **Trusted Solaris**

es otro ejemplo de distribución configurada para utilizar MAC. está diseñado para proporcionar operaciones seguras a varios niveles a la vez que implementa MAC. Carcateristicas:

  - Implementa MAC.
  - Incluye auditoría detallada de los eventos de nuestros sistemas y compartimentación para iaslar nuestros procesos y datos.

Ahora, dentro de un sistema operativo de confianza, a menudo usaremos microkernels que van a minimizar la base informática de confianza de ese sistema.

## Microkernel y TCB

Como mencionamos anteriormente muchos sistemas operativos de confianza utilizan una arquitectura de **microkernel**.

Su objetivo es reducir la **Trusted Computing Base (TCB)**, es decir, los componentes críticos para la seguridad.

**Ventajas:**

- Reduce la superficie de ataque.
- Disminuye la probabilidad de vulnerabilidades.
- Facilita la verificación de la seguridad.

## Sistemas móviles

Los dispositivos móviles también incorporan características de sistemas operativos de confianza como **Android de Google** han incorporado elementos del modelo de computación de confianza
a través del uso de diversos mecanismos de seguridad, como el **sandboxing de aplicaciones**, que restringe el acceso a los recursos del sistema y aísla las aplicaciones entre sí, mediante la aplicación
de herramientas de arquitectura de seguridad de confianza, como **AppArmor**, para imponer controles de acceso obligatorios en los dispositivos móviles.

## Ventajas

- Mayor protección de datos.
- Estrictos controles de acceso.
- Menor superficie de ataque.
- Mayor resistencia frente a ataques.

## Desventajas

- Diseño e implementación costosos.
- Mayor complejidad de administración.
- Puede afectar la usabilidad y el rendimiento.
- Normalmente solo se utiliza cuando la seguridad es crítica.

## Idea clave

- Un **Trusted Operating System (TOS)** aplica controles de seguridad estrictos mediante **MAC**.
- Los **Common Criteria** clasifican su nivel de seguridad mediante los **EAL (1-7)**.
- La mayoría de **Windows, macOS y Linux** cuentan con certificaciones **EAL4/EAL4+**  EAL4 significa que el sistema operativo ha sido metódicamente diseñado, probado y revisado, y realmente nos proporciona un nivel de garantía de seguridad realmente bueno y decente, pero no es ni de lejos tan alto como EAL6 o EAL7..
- Los niveles **EAL6 y EAL7** suelen reservarse para sistemas especializados (militares, aeronáuticos, médicos o industriales).

Así que recuerde, los sistemas operativos de confianza desempeñan un papel vital a la hora de proporcionar un entorno informático seguro en un contexto en el que la integridad y la confidencialidad de los datos son cruciales.

Mediante la aplicación de estrictas normas de control de acceso, la realización de rigurosas evaluaciones de seguridad y la reducción al mínimo de la base informática de confianza, estos sistemas pretenden mitigar y minimizar los
posibles riesgos para la seguridad.

Con el tiempo, a medida que la seguridad y la garantía de los datos vayan adquiriendo un papel cada vez más importante en nuestras redes organizativas, es posible que su organización utilice cada vez más sistemas operativos de confianza.

# Actualizaciones y parches

## ¿Qué es un parche?
Un **parche (patch)** es una modificación de software que corrige errores o, especialmente, **vulnerabilidades de seguridad**.

La **gestión de parches** es el proceso de identificar, probar, desplegar y supervisar parches para mantener seguros los sistemas.

## Tipos principales

- **Hotfix:** parche urgente que corrige una vulnerabilidad crítica y debe aplicarse rápidamente después de probarlo.
- **Actualización:** agrega nuevas funciones o mejoras; no necesariamente corrige problemas de seguridad.
- **Service Pack:** conjunto de muchos parches y actualizaciones agrupados en un único instalador.

## Gestión de parches

Un programa eficaz debe tener este método rutinario:

1. Tener una persona/equipo responsable de seguir todos boletines y versiones de parches de seguridad suministrados por los proveedores.
2. Detectar qué sistemas/aplicaciones necesitan parches y Automatizar el parcheado cuando sea posible.
3. Incluir recursos **cloud**, además de sistemas locales.
4. Clasificar los parches como **urgentes, importantes o no críticos**.
5. Probar los parches importantes en un **entorno de laboratorio** antes de producción.
6. Mantener registros de los parches aplicados.
7. Debe disponer de un mecanismo para evaluar, probar y desplegar actualizaciones de **firmware**.
8. Tener un proceso de emergencia para aplicar rápidamente parches críticos si han sido aprobados por un consejo asesor de cambios de emergencia.
9. Agrupar y desplegar periódicamente los parches no críticos.

##  Idea importante

Cuando se publica un parche, los atacantes pueden analizarlo para descubrir **qué vulnerabilidad corrige** y crear un exploit.

Por eso, **retrasar demasiado un parche puede dejar el sistema vulnerable**.

> **Hardening → mantener el software actualizado y parcheado para reducir vulnerabilidades y la superficie de ataque.**

Así pues, recuerde que las actualizaciones y los parches son cruciales para la seguridad de sus dispositivos, y que debe contar con un programa de gestión de parches para asegurarse de que puede minimizar el riesgo de ataques.

Cuando se trata de actualizaciones y parches, recuerde que hay tres tipos principales que debemos tener en cuenta.

Se trata de hotfixes, actualizaciones y service packs.

Un hotfix es un parche de seguridad que resuelve un problema de seguridad y debe aplicarse inmediatamente después de ser probado en su entorno de laboratorio para asegurarse de que la vulnerabilidad no puede ser explotada por los atacantes.

Una actualización, por otro lado, va a proporcionar a su sistema una funcionalidad adicional, pero normalmente no le proporciona ningún parche para los problemas relacionados con la seguridad.

Un paquete de servicio va a ser una colección de cientos o miles de revisiones y actualizaciones en un archivo de instalación para que cuando instales un nuevo sistema operativo, puedas instalar todos los parches de seguridad utilizando un archivo de instalación
en lugar de tener que salir y recoger cien o mil revisiones y actualizaciones de seguridad diferentes para poder implementarlas en tu sistema.

# Gestión de parches

La **gestión de parches** consiste en **planificar, probar, aplicar y auditar** parches de software.

Su objetivo es:
-  Aumentar la **seguridad** corrigiendo vulnerabilidades conocidas (CVE).
-  Aumentar el **tiempo de actividad** y evitar fallos.
-  Ayudar al **cumplimiento** de normativas.
-  Mejorar funciones y rendimiento.

## 4 pasos principales

### 1. Planificación
- Crear políticas y procedimientos.
- Identificar y realizar seguimiento de los parches y actualizaciones disponibles.
- Comprobar su compatibilidad.
- Determinar cómo se probarán y desplegarán antes de instalarlos.
- Utilizar herramientas de gestión de parches que puede decirle realmente si los parches se han desplegado, instalado y verificado funcionalmente en un determinado servidor o cliente.

### 2. Pruebas
Antes de automatizar su despliegue un parche en toda la red/organización que se recibira del fabricante, se debera:
- Probarlo en un **laboratorio** o entorno de prueba.
- Verificar que no genere nuevos problemas.
- Tener en cuenta que cada organización puede tener configuraciones diferentes y eso puede realmente romper algunos de los parches de seguridad cuando se intenta instalarlos.
Así pues, aunque los fabricantes intentan garantizar que los parches no van a causar daños a nuestros sistemas, esto simplemente no se puede garantizar
porque cada red tiene sus propias configuraciones individuales.

**Idea clave:** un parche que funciona correctamente en un sistema puede causar problemas en otro.

### 3. Aplicación
Después de probar el parche:
- Desplegarlo en los sistemas que lo necesiten.
- En redes pequeñas → puede hacerse manualmente.
- En redes grandes → utilizar herramientas de gestión y automatización.

#### Patch Rings (Anillos de Parches)
Los Patch Rings son grupos de dispositivos a los que se les despliega un parche de forma progresiva.
Los parches suelen desplegarse progresivamente:

**Ring 1(pocos equipos) → Ring 2(más equipos) → Ring 3(muchos equipos) → Ring 4(todos los equipos)**

Se empieza con pocos equipos y, si no aparecen problemas, se aumenta progresivamente la cantidad.

Esto limita el impacto antes de actualizar todos los equipos. si el parche provoca algún fallo, sirven para detectar problemas temprano.

### 4. Auditoría
Después del despliegue:
- Comprobar que el parche se instaló correctamente, utilizando una herramienta como Microsoft Endpoint Configuration Manager o una herramienta de gestión de parches de terceros,
podremos llevar a cabo el escaneado y la verificación de sus estaciones de trabajo y servidores por usted, y esto ayudará a garantizar que los parches se han instalado correctamente.
- Detectar errores o problemas inesperados.
- Escanear los sistemas para verificar su estado.
- Registrar los resultados.

Ahora, además de llevar a cabo la gestión de parches en nuestras estaciones de trabajo y servidores, también es importante que realicemos la gestión del firmware de todos nuestros dispositivos de red.

Al fin y al cabo, todos nuestros dispositivos de red, como conmutadores y enrutadores, ejecutan una forma de software conocida como firmware en esos dispositivos para poder proporcionarles el sistema operativo.

Si sus dispositivos de red no contienen las versiones de firmware más recientes y actualizadas, podría tener vulnerabilidades de seguridad y fallos de software que podrían ser aprovechados por un atacante.

## Gestión del firmware

La gestión de parches también incluye el **firmware de dispositivos de red** como:

- Routers
- Switches
- Otros dispositivos de red

El firmware puede contener vulnerabilidades, por lo que también debe mantenerse actualizado.

> **Firmware desactualizado = posibles vulnerabilidades explotables.**

## Herramientas y automatización

En organizaciones grandes se utilizan herramientas para automatizar la gestión de parches, por ejemplo:

- **Microsoft Endpoint Configuration Manager**
- Herramientas de terceros
- **MDM** para dispositivos móviles
- Gestores de paquetes en Linux

La automatización permite gestionar grandes cantidades de dispositivos de forma eficiente.

## Resumen

**Gestión de parches de software = Planificar → Probar → Aplicar → Auditar**

Su finalidad es mantener **servidores, estaciones de trabajo, dispositivos móviles y dispositivos de red** actualizados y protegidos frente a vulnerabilidades conocidas.

Así que recuerde, La gestión de parches es fundamental para proporcionar seguridad, aumentar el tiempo de actividad, garantizar el cumplimiento de la normativa y mejorar las prestaciones
de los dispositivos de red, servidores y clientes.

Sin embargo, para llevar a cabo la gestión de parches a gran escala, es necesario utilizar una herramienta, automatización u orquestación para garantizar que todos los dispositivos de red, servidores,
portátiles y dispositivos móviles estén actualizados y parcheados contra cualquier vulnerabilidad conocida(CVE).

# Políticas de Grupo (Group Policy)

Una **política de grupo (Group Policy)** es un conjunto de reglas que permite administrar y aplicar configuraciones de seguridad a **usuarios y equipos Windows**.

## ¿Para qué sirven?

Permiten aplicar de forma centralizada:

-  Políticas de contraseñas.
-  Bloqueo de cuentas.
-  Restricciones de aplicaciones.
-  Configuraciones de seguridad.
-  Permisos y configuraciones de usuarios.
-  Configuraciones de equipos.

En Windows se puede acceder al editor local mediante:

`gpedit.msc`

En un entorno empresarial con **Active Directory**, las políticas pueden administrarse y distribuirse a muchos equipos mediante **GPO (Group Policy Objects)**.

## GPO (Group Policy Object)

Una **GPO** es un conjunto de configuraciones que se puede aplicar a usuarios o equipos.

Esto permite crear una **línea de base segura (secure baseline)** y aplicarla de forma uniforme a los sistemas de la organización.

---

## Baselining

El **baselining** consiste en establecer qué comportamiento es **normal** en un sistema o red.

Después podemos comparar la actividad actual con esa línea de base para detectar **desviaciones o algo anormal**.

Ejemplo:

- Actividad normal un sábado → baja.
- Un sábado aparece un pico enorme de tráfico → ⚠️ investigar.

Una desviación puede ser:

> - ✅ Esperada/aceptable.
> - 🚨 Anormal y requiere investigación.

→ suponemos que es anormal y podemos investigar o directamente se investiga y se descubre que un atacante está extrayendo datos de la empresa, es un ejemplo para que lo tengamos en cuenta.

El baselining puede ayudar a detectar incidentes como **filtraciones de datos**. Ahora, cada desviación debe analizarse y clasificarse como aceptable y esperada o como un problema
que hay que investigar más a fondo.

Muchas filtraciones de datos se han descubierto al investigar una utilización de la red superior a la esperada, durante periodos que deberían haber sido relativamente bajos.

Al examinarlos, la gente ha descubierto cosas, como que se han producido filtraciones de datos u otros problemas en su red.

---

## Politica de Control de Aplicaciones

### >  AppLocker

**AppLocker** permite controlar qué aplicaciones pueden ejecutarse en Windows.

Permite crear:

- **Allowlisting** → solo se ejecutan las aplicaciones permitidas.
- **Blocklisting** → se bloquean únicamente las aplicaciones incluidas en la lista.

#### Tipos de reglas

Las reglas pueden basarse en:

- **Publisher** → fabricante/editor.
- **Path** → ubicación del archivo.
- **Hash** → identificador/hash específico del archivo.

### Ejemplo

Podemos crear una regla:

`Deny → Todos los usuarios → Path → %WINDIR%\Temp\*`

Esto significa:

> 🚫 Bloquear la ejecución de cualquier archivo ubicado dentro de la carpeta `Temp`.

También podemos crear excepciones para permitir determinados archivos o aplicaciones.

---

## Idea clave

**Group Policy → permite administrar configuraciones de seguridad de forma centralizada.**

**GPO → conjunto de reglas/configuraciones que se aplican a usuarios o equipos.**

**Baselining → establece qué es normal para detectar anomalías.**

**AppLocker → controla qué aplicaciones pueden ejecutarse.**

Todo esto puede utilizarse para crear una **Secure Baseline** y aplicar **hardening** de forma uniforme en los equipos Windows.

# SELinux (Security-Enhanced Linux)

**SELinux** es una capa adicional de seguridad para Linux que implementa **MAC (Mandatory Access Control)** para controlar de forma estricta qué usuarios y procesos pueden acceder a archivos, directorios, puertos y otros recursos

Ahora, una de las mejores maneras de detener una violación de datos es restringir la capacidad de conceder o denegar el acceso de alguien a un objeto de recurso dado dentro de su sistema de archivo.

## DAC vs MAC

- **DAC (Discretionary Access Control/Control de Acceso Discrecional):** el propietario del recurso puede modificar sus permisos mediante comandos como `chmod` y `chown`. Es decir que el propietario del recurso decide sus permisos.

Ejemplo en Linux:

Santiago crea archivo.txt
        ↓
Santiago = propietario
        ↓
Santiago puede decidir:
- quién puede leerlo
- quién puede modificarlo
- quién puede ejecutarlo

- **MAC(Mandatory Access Control/Control de Acceso Obligatorio):** es un mecanismo de control de acceso reforzado por el sistema que se basa en la autorización del sujeto y las etiquetas del objeto. los permisos son definidos por políticas del sistema y
**ni siquiera el propietario puede modificarlos libremente**. El sistema operativo hace cumplir estas políticas.

Santiago crea archivo.txt
        ↓
SELinux establece una política
        ↓
La política determina qué usuario/proceso puede acceder
        ↓
Santiago NO puede cambiar esa política simplemente porque sea propietario

Por eso se llama **Mandatory** (obligatorio): el sistema hace cumplir las reglas.

#### Permisos Basados en Contextos

Ahora, los permisos basados en el contexto se refieren a esquemas de permisos que están definidos por varias propiedades para un archivo o proceso dado, y utiliza esas propiedades juntas,
en lugar de aisladas para determinar si se debe conceder o denegar el acceso a un usuario dado.

Ahora, en Linux, hay dos esquemas principales de permisos basados en el contexto que están disponibles, a saber, SELinux y AppArmor. Y ambos esquemas de permisos basados en el contexto
aprovechan MAC para hacer su trabajo. En pocas palabras se tienen en cuenta varias características para decidir si se permite o deniega el acceso.

## SELinux

SELinux utiliza **etiquetas de seguridad** para controlar el acceso y que se puede hacer cada proceso con cada recurso. Sus 3 contextos principales son:

- **Usuario:** determina qué usuarios pueden acceder(all users, unprivileged user, system administrators y root user).
- **Rol:** determina qué roles pueden acceder(esos roles son típicamente usados para permitir o denegar el acceso al dominio dado o a los recursos y procesos dados. Para controlar esto, hay un rol llamado "object_r", y esto se aplica a tus archivos y directorios.
- **Tipo:** parte de etiqueta de MAC, clasifica los recursos según sus características de seguridad y permite un control más preciso, tambien es una forma de agrupar objetos que tienen requisitos o características de seguridad similares.
- **Nivel (opcional):** indica la sensibilidad de un recurso y permite restricciones adicionales.

### Modos de SELinux

- **Disabled(Desactivado):** SELinux está apagado → no se aplica MAC y se utiliza DAC.
- **Enforcing(Forsozo):** SELinux está activo y **aplica las políticas**, bloqueando acciones no permitidas.
- **Permissive(Permisivo):** SELinux está activo, pero **no bloquea** las acciones; registra las violaciones para analizarlas.

Ahora, SELinux puede implementar dos tipos diferentes de políticas.

### Políticas

- **Targeted(Selectivas/Dirigida):** aplica SELinux principalmente a procesos específicos que necesitan mayor protección. Es la política predeterminada en Red Hat/CentOS.
- **Strict(Estrictas):** aplica MAC a prácticamente **todo el sistema**, proporcionando mayor seguridad pero siendo más difícil de configurar y mantener. Esto sólo se aplica a ciertas cosas en su sistema operativo para las
que realmente desea niveles más altos de protección. Si sigues adelante y usas la política estricta, va a imponer MAC en todo en tu sistema.

### Auditoría

SELinux registra las **violaciones de seguridad** en logs. Esto permite detectar intentos de acceso no autorizado o acciones que contradicen las políticas.

Al principio pueden aparecer **falsos positivos** mientras las políticas se ajustan.

> **Idea clave:** SELinux limita lo que un usuario o proceso puede hacer, incluso si normalmente tendría permisos mediante DAC.

Recuerda, SELinux es tan fuerte como los perfiles restrictivos que estás creando. Así que si creas buenos perfiles restrictivos y endureces tus aplicaciones, esto puede prevenir muchos ataques maliciosos contra las redes de tu empresa.

Esquema Para pensarlo de la manera adecuada:

SELinux
   ↓
Políticas/perfiles de seguridad
   ↓
Definen qué puede hacer cada proceso
   ↓
PERMITIR / DENEGAR

Por ejemplo, una aplicación web puede tener una política que diga:

Servidor web
   ↓
Puede leer → /var/www/
Puede acceder → puerto 80
NO puede acceder → /home/usuarios/
NO puede modificar → archivos críticos

Si un atacante consigue comprometer el servidor web, SELinux puede impedir que ese proceso haga cosas que la política no permite.

# Niveles de cifrado de datos

El **cifrado** convierte los datos en un formato ilegible para impedir el acceso no autorizado y proteger su **confidencialidad**.

El cifrado puede aplicarse a diferentes niveles:

### 1. Cifrado de disco completo (Full Disk Encryption)
Cifra **todo el disco**.

- Windows → **BitLocker**
- macOS → **FileVault**

Protege los datos incluso si alguien extrae el disco y lo conecta a otro equipo.

### 2. Cifrado de partición
Cifra **una partición específica** del disco.

Ejemplo: cifrar únicamente la partición donde se almacenan documentos confidenciales.

Ahora, puede que te preguntes por qué no encriptar toda la unidad en lugar de encriptar sólo una partición. Y la razón es que el cifrado añade una sobrecarga adicional
al proceso de lectura o escritura de datos en un dispositivo de almacenamiento, porque ahora tenemos que descifrar los datos que se leen o cifrar los datos que se escriben.

Así que muchas veces optaremos por encriptar sólo las partes que contienen datos sensibles, porque esto acelerará nuestro sistema en general.

### 3. Cifrado de volumen
Crea un **contenedor cifrado** dentro del almacenamiento que puede contener varios archivos y carpetas.

Ejemplo: **VeraCrypt**.

D:\ 🔐 Volumen cifrado
    ├── documentos
    ├── fotos
    └── archivos

### 4. Cifrado a nivel de archivo
Cifra **archivos individuales**.

Ejemplo: **GPG**.

Es útil para cifrar archivos específicos antes de enviarlos por correo u otro medio.

### 5. Cifrado de base de datos
Cifra **toda una base de datos**.

Ejemplo: **Transparent Data Encryption (TDE)** en SQL Server.

El sistema de base de datos se encarga automáticamente del cifrado y descifrado.

Se refiere a que la propia base de datos puede estar distribuida físicamente en varios lugares y el cifrado protege esos datos en todos esos lugares.

Ejemplo:

             BASE DE DATOS
                  ↓
        ┌─────────┼─────────┐
        ↓         ↓         ↓
     Disco 1   Disco 2   Disco 3
        🔐        🔐        🔐

O incluso:

         Nube
          ↓
   ┌──────┼──────┐
   ↓      ↓      ↓
 Servidor Servidor Servidor
   🔐       🔐       🔐

La idea es que el cifrado de base de datos puede proteger los datos aunque estén almacenados en múltiples dispositivos/servidores o en la nube.

### 6. Cifrado a nivel de registro
Cifra **datos específicos dentro de una base de datos**, como determinadas filas o columnas.

Ejemplo:

```text
Base de datos de clientes
        ↓
Solo cifrar:
- Tarjeta de crédito
- DNI
- Datos sensibles

```

Recuerda cada uno de ellos proporciona un nivel diferente de granularidad de la seguridad, por lo que es importante entender las diferencias
para asegurarse de que puede seleccionar el "equilibrio" adecuado entre **seguridad y rendimiento** del sistema cuando determine qué tipo de cifrado desea utilizar en su organización.

Nuestro objetivo es garantizar que sus datos permanezcan seguros e inaccesibles para entidades no autorizadas, independientemente de dónde vayan a almacenarse.

# Líneas de Base Seguras (Secure Baseline)

Una **línea de base segura (Secure Baseline)** es un conjunto estándar de **configuraciones y controles de seguridad** que se aplican a sistemas, redes o aplicaciones para garantizar un nivel mínimo de seguridad.

## 1. Establecer la línea de base

Primero se analiza el sistema para identificar:

- Qué datos maneja.
- Cómo fluyen esos datos.
- Vulnerabilidades y amenazas.
- Requisitos de seguridad y cumplimiento.
- Mejores prácticas y estándares como **NIST** o **ISO 27001**.

**Ejemplo:** se toma una laptop nueva, se instala el sistema operativo, actualizaciones, firewall, antivirus/EDR, aplicaciones necesarias y políticas de seguridad. Después se comprueba que no tenga vulnerabilidades conocidas.

Así, ahora podemos instalar todas las aplicaciones que necesitan nuestros empleados, incluidas cosas como un paquete ofimático, un agente de respuesta de detección de puntos finales, un navegador web y otras herramientas
por el estilo, en función de sus funciones laborales específicas.

Una vez instaladas y configuradas todas estas herramientas, analizaremos de nuevo el sistema en busca de vulnerabilidades conocidas y también las corregiremos.

Una vez que está correctamente configurada, se crea una **imagen** de esa laptop para utilizarla como plantilla segura en futuras laptops iguales.

## 2. Desplegar la línea de base

La configuración segura se aplica al resto de los dispositivos.

Puede incluir:

- 🔥 Firewall configurado.
- 🔐 Establecimiento de permisos de usuarios.
- 🔒 Aplicación de protocolos de encriptación(Cifrado).
- 🛡️ Garantía de que las soluciones antivirus y antimalware están correctamente instaladas y actualizadas(Antivirus/EDR).
- 📋 Políticas de seguridad.
- 🔄 Actualizaciones y parches.

Se pueden utilizar **scripts y herramientas automatizadas** para aplicarla de forma uniforme.

En Windows empresarial, por ejemplo, se pueden utilizar **GPO (Group Policy Objects)** para aplicar políticas de contraseñas, auditoría, permisos, etc.

En AWS, se puede utilizar **AWS Config** para comprobar y aplicar determinadas configuraciones.

## 3. Mantener la línea de base

esta línea de base se perfeccionará y protegerá continuamente para que se mantenga al día con los últimos parches de seguridad, hotfixes, actualizaciones y service packs, a medida
que el entorno de amenazas siga evolucionando. No basta con crearla una vez. Hay que mantenerla continuamente:

**Baseline → Monitorear → Detectar desviaciones → Corregir → Actualizar**

Por ejemplo, si la baseline establece:

```text
Firewall: ACTIVADO
Antivirus/EDR: ACTIVADO
USB: BLOQUEADO
Windows Update: ACTUALIZADO
```

También debemos mantener nuestras lineas seguras en todos nuestros activos. Ahora bien, esto se hace bloqueando nuestros sistemas para que nuestros usuarios no puedan instalar software adicional
ni modificar nuestras configuraciones existentes.

Ahora, para ayudar a mantener su línea de base segura, también debe llevar a cabo la formación y sensibilización con todos sus empleados para asegurarse de que entienden la importancia de adherirse a las
configuraciones de línea de base segura. Los empleados deben ser conscientes de los riesgos potenciales de desviarse de la línea de base, y se les debe animar a informar de cualquier actividad sospechosa
que puedan notar cuando estén utilizando sus sistemas.

Así que recuerde, el establecimiento, despliegue y mantenimiento de una línea de base segura es una práctica crítica dentro de la industria de la ciberseguridad que protege las redes de su organización.

Las líneas de base seguras ayudan a garantizar que los activos digitales de una organización estén configurados de forma coherente para resistir los ataques y mitigar las vulnerabilidades y los errores de configuración conocidos.
Al supervisar y actualizar continuamente nuestras líneas de base seguras, nuestras organizaciones pueden mejorar su postura de seguridad y proteger sus valiosos datos y recursos de posibles violaciones de datos.
