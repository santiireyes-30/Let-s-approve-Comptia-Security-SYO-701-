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

Ocurre cuando dos WAP tienen áreas de cobertura solapadas y utilizan el **mismo canal**.

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

**Site Survey → Instalación de WAP → Heat Map → Ajustes de cobertura y potencia**
