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

## Resumen para el examen

- Las configuraciones por defecto **priorizan la facilidad de uso, no la seguridad**.
- Cambiar inmediatamente las credenciales predeterminadas.
- Utilizar contraseñas largas, únicas y MFA.
- Desactivar puertos y protocolos innecesarios.
- Preferir protocolos cifrados:
  - HTTP → HTTPS.
  - SMTP → SMTPS.
- Cerrar puertos abiertos que no se utilicen (ej. Telnet - puerto 23).
- **Menos servicios activos = menor superficie de ataque = mayor seguridad.**
