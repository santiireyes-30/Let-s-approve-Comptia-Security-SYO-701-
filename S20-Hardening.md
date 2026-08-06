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

## Common Criteria y niveles EAL

Los **Common Criteria** evalúan la seguridad de un sistema operativo mediante los **Evaluation Assurance Levels (EAL)**.

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
  - Implementa **MAC** sobre distribuciones Linux.
  - Clasificación aproximada **EAL4+**.
  - Restringe aplicaciones y usuarios al **mínimo privilegio**.
  - Puede aislar procesos potencialmente peligrosos.

- **Trusted Solaris**
  - Implementa MAC.
  - Incluye auditoría detallada y compartimentación de procesos y datos.

## Microkernel y TCB

Muchos sistemas operativos de confianza utilizan una arquitectura de **microkernel**.

Su objetivo es reducir la **Trusted Computing Base (TCB)**, es decir, los componentes críticos para la seguridad.

**Ventajas:**

- Reduce la superficie de ataque.
- Disminuye la probabilidad de vulnerabilidades.
- Facilita la verificación de la seguridad.

## Sistemas móviles

Los dispositivos móviles también incorporan características de sistemas operativos de confianza.

Ejemplo:

- **Android**
  - Sandboxing de aplicaciones.
  - Uso de **AppArmor**.
  - Aplicación de políticas **MAC** para aislar aplicaciones.

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
- La mayoría de **Windows, macOS y Linux** cuentan con certificaciones **EAL4/EAL4+**.
- Los niveles **EAL6 y EAL7** suelen reservarse para sistemas especializados (militares, aeronáuticos, médicos o industriales).
