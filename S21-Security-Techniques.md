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
- **Análisis estático (SAST):** analizar el código fuente sin ejecutarlo.
- **Análisis dinámico (DAST):** analizar una aplicación mientras está ejecutándose.
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
