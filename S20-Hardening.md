# Hardening (Endurecimiento)

El **hardening** es el proceso de **hacer un sistema, aplicación o red más seguros**, reduciendo su superficie de ataque y eliminando vulnerabilidades innecesarias.

# INTRODUCCIÓN

## Medidas principales de hardening

### Configuraciones por defecto
- Cambiar **contraseñas predeterminadas**.
- Cerrar **puertos abiertos innecesarios**.
- Modificar configuraciones inseguras de fábrica.

### Restricción de aplicaciones (Application Whitelisting)
- Solo se permite ejecutar **aplicaciones autorizadas**.
- Todo lo demás se bloquea por defecto.

### Servicios innecesarios
- Desactivar procesos o servicios que no se utilizan.
- Reduce vulnerabilidades y libera recursos.

### Sistemas Operativos de Confianza (Trusted OS)
- Sistemas evaluados y certificados para manejar información sensible.
- Incorporan controles de seguridad más estrictos.

### Actualizaciones y Parches
- **Actualización (Update):** añade mejoras, nuevas funciones o corrige errores.
- **Parche (Patch):** corrige una vulnerabilidad o problema de seguridad específico.

### Gestión de Parches (Patch Management)
Proceso de:
1. Identificar parches.
2. Probarlos.
3. Implementar/Despegar.
4. Supervisarlos.

### Políticas de Grupo (Group Policy - Windows)
- Las políticas de grupo son un conjunto de reglas y configuraciones en entornos Windows que permiten a los administradores gestionar y controlar de forma centralizada la configuración de usuarios
y equipos, garantizando el cumplimiento y la seguridad de sus normas operativas.

### SELinux (Security-Enhanced Linux)
- Implementa **Control de Acceso Obligatorio (MAC)**.
- Limita las acciones de procesos y usuarios, incluso si una aplicación es comprometida.

Pero básicamente es un marco de seguridad para sistemas operativos basados en Linux que implementa controles de acceso obligatorios para confinar y limitar las acciones de procesos y usuarios con el fin de mejorar
la seguridad general del sistema.

### Niveles de cifrado de datos
El cifrado de datos es el proceso de convertir datos en un código secreto para impedir el acceso no autorizado.

Protege la información convirtiéndola en un formato ilegible.

Puede aplicarse a:
- Disco completo.
- Partición.
- Volumen.
- Archivo.
- Base de datos.
- Registro (Record).

### Línea Base Segura (Secure Baseline)
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
