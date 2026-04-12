# COURSE PROJECT

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/f/fc/UPC_logo_transparente.png"></img><br>
    <strong>Universidad Peruana de Ciencias Aplicadas</strong><br>
    <br>
    <strong>Facultad de Ingeniería</strong><br>
    <strong>Carrera de Ingeniería de Software</strong><br>
    <strong>Ciclo 2026-10</strong>
</p>

<p align="center">
  <strong>Código del curso: </strong>1ASI0572<br>
  <strong>Curso: </strong>Desarrollo de Soluciones IOT
</p>

<p align="center">
  <strong>NRC: 6772</strong>
</p>

<p align="center">
    <strong>Profesor: </strong>Marco Antonio Leon Baca
</p>

<p align="center">
    <strong>Informe de Trabajo Final</strong>
</p>

<p align="center">
    <strong>Nombre del startup: </strong> [Startup]
</p>

<p align="center">
    <strong>Nombre del producto:</strong> [Producto]
</p>

<p align="center">
    <strong>Marzo, 2026</strong>
</p>

---

# Project Report Collaboration Insights
**URL del repositorio para el Project Report:** [https://github.com/IoTMedicineProject/report.git](https://github.com/IoTMedicineProject/report.git)

---

# Contenido

---

# Student Outcome

---

# Capítulo I: Introducción

## 1.1. Startup Profile
### 1.1.1. Descripción de la Startup
**ParkSense** es una startup conformada por estudiantes de la carrera de Ingeniería de Software de la Universidad Peruana de Ciencias Aplicadas (UPC), enfocada en desarrollar soluciones tecnológicas basadas en **Internet de las Cosas (IoT)** para optimizar la gestión de estacionamientos en centros comerciales.

A través de su producto **SpotFinder**, ParkSense busca resolver la problemática del tiempo desperdiciado y la congestión vehicular que se genera dentro de los estacionamientos cerrados. El sistema proporciona una solución integral que combina:
* Sensores ultrasónicos.
* Reconocimiento automático de placas vehiculares (ANPR) para la automatización de entrada y salida de vehículos.
* Guiado visual por luces.
* Aplicación móvil para conductores.
* Panel de control para administradores de estacionamientos.

La propuesta consiste en el desarrollo de un sistema inteligente que permita monitorear en tiempo real los espacios disponibles y ocupados, brindando información útil tanto a usuarios como a administradores mediante plataformas digitales.

**Misión**
Transformar la experiencia de estacionamiento en centros comerciales del Perú mediante soluciones IoT innovadoras que reduzcan el tiempo de búsqueda de espacios, mejoren la seguridad vehicular y optimicen la operación administrativa de los estacionamientos.

**Visión**
Posicionarnos como una solución innovadora dentro del ámbito de ciudades inteligentes, integrando IoT y plataformas digitales para transformar la gestión de estacionamientos.
### 1.1.2. Perfiles de integrantes del equipo
| Foto | Nombres y Apellidos | Código | Carrera | Resumen de Conocimientos y Habilidades |
| :---: | :--- | :---: | :---: | :--- |
| ![Henry Kalet Esteban Román](./assets/images/photos/esteban-henry.png) | Henry Kalet Esteban Román | U202310210 | Ingeniería de Software | Estudiante de 7° ciclo. Posee experiencia en desarrollo fullstack (Angular, Vue.js, Spring Boot, .NET) y aplicaciones móviles. Domina arquitecturas DDD y Clean Architecture, además de metodologías ágiles como Scrum y Lean UX. Cuenta con sólidos conocimientos en Java, TypeScript y bases de datos relacionales
| ![[Foto Compañero 2]](./assets/images/photos/perfil-vacio.png) | [Nombres y Apellidos] | [Código] | [Carrera] | [Resumen de Conocimientos y Habilidades] |
| ![[Foto Compañero 3]](./assets/images/photos/perfil-vacio.png) | [Nombres y Apellidos] | [Código] | [Carrera] | [Resumen de Conocimientos y Habilidades] |
| ![[Foto Compañero 4]](./assets/images/photos/perfil-vacio.png) | [Nombres y Apellidos] | [Código] | [Carrera] | [Resumen de Conocimientos y Habilidades] |
| ![[Foto Compañero 5]](./assets/images/photos/perfil-vacio.png) | [Nombres y Apellidos] | [Código] | [Carrera] | [Resumen de Conocimientos y Habilidades] |
## 1.2. Solution Profile

El proyecto consiste en el desarrollo de un sistema **IoT** para la gestión inteligente de estacionamientos, basado en el monitoreo en tiempo real de los espacios disponibles. El sistema utiliza sensores instalados en cada espacio para detectar si un lugar está ocupado o libre, permitiendo generar un mapa actualizado del estacionamiento que puede ser consultado por los usuarios a través de una aplicación móvil.

Adicionalmente, se incorpora el **reconocimiento de placas vehiculares (ALPR)** como un mecanismo de identificación, el cual permite asociar un vehículo a su ubicación dentro del estacionamiento. Esto facilita un acceso más fluido mediante la automatización de ingreso por barreras anti-intrusión, mientras que los conductores son guiados hacia su lugar de destino a través de indicadores LED.

La solución incluye dos plataformas principales:
* **Aplicación móvil (Usuarios):** Permite visualizar espacios disponibles, recibir notificaciones relacionadas al vehículo y realizar pagos digitales por el tiempo de uso.
* **Plataforma web (Administradores):** Panel para gestionar la información del estacionamiento, visualizar estadísticas de uso (como espacios con mayor demanda) y tomar decisiones basadas en datos.

### 1.2.1. Antecedentes y problemática

**¿Cuál es el problema? (What)**
El problema central es la ausencia de sistemas inteligentes de gestión en los estacionamientos de centros comerciales en Lima. Esto genera tiempos excesivos de búsqueda de espacios, congestión vehicular interna, cuellos de botella en los accesos e inseguridad por falta de trazabilidad. Actualmente, la mayoría opera con sistemas semi-automatizados limitados a tickets físicos, sin ofrecer información en tiempo real.

Según estudios de la Universidad de Piura (2019), los conductores en Lima pierden en promedio **cinco horas a la semana** buscando estacionamiento. Además, el Banco Central de Reserva del Perú (BCR) estima que la congestión genera pérdidas económicas de aproximadamente **S/ 23,300 millones anuales** (2.4% del PBI).

**¿Cuándo ocurre? (When)**
Se presenta de manera continua, intensificándose en horas punta, fines de semana y temporadas de alta afluencia como Navidad, Fiestas Patrias, Black Friday o Cyber Days.

**¿Dónde ocurre? (Where)**
Surge en los estacionamientos cerrados de centros comerciales en Lima Metropolitana, particularmente en aquellos con múltiples niveles subterráneos o estructuras elevadas.

**¿A quién afecta? (Who)**
* **Conductores:** Experimentan frustración, inseguridad y pérdida de tiempo.
* **Administradores y operadores:** Enfrentan altos costos operativos, dificultades para generar reportes de ocupación y limitaciones para responder ante emergencias.

**¿Por qué sucede? (Why)**
La raíz radica en la falta de infraestructura tecnológica IoT. La mayoría de los estacionamientos carece de detección de disponibilidad por espacio individual y de sistemas de guiado visual en tiempo real.

**¿Cómo se utilizará el producto? (How)**
* **Para conductores:** Mediante una aplicación móvil para ver disponibilidad en tiempo real, reserva de espacios, localización del auto y pago digital.
* **Para administradores:** A través de un dashboard web con métricas clave (tasa de ocupación, rotación, ingresos) y control remoto de barreras.
* **Componente IoT:** Nodos **ESP32** con sensores ultrasónicos **HC-SR04**, LEDs **WS2812B**, módulos **ESP32-CAM** para placas y sensores **MQ-2** para detección de gases, comunicados vía protocolo **MQTT**.

**¿Cuán grande es el impacto? (How much)**
* El 30% del tráfico en zonas comerciales proviene de vehículos buscando estacionamiento.
* Se generan **1.3 kg de CO₂** por cada 10 minutos de búsqueda.
* El 51% de los limeños reporta pérdida de calidad de vida debido a la congestión.

## 1.2.2. Lean UX Process

El Lean UX Process es un enfoque ágil centrado en diseñar soluciones que respondan a necesidades reales de los usuarios mediante ciclos cortos de validación, retroalimentación y mejora continua. Para este proyecto, utilizamos este enfoque para analizar los desafíos de la gestión de estacionamientos en centros comerciales de Lima y construir una solución IoT integral que mejore la experiencia del conductor y la eficiencia operativa del estacionamiento.

### 1.2.2.1. Lean UX Problem Statements

En estacionamientos de gran escala, los usuarios tienen dificultades para encontrar espacios disponibles de manera rápida, mientras que los administradores no cuentan con información estructurada sobre el uso del estacionamiento.

Actualmente, no existen soluciones accesibles que integren monitoreo en tiempo real con visualización clara y herramientas de análisis.

¿Cómo podríamos diseñar un sistema que permita conocer en tiempo real la disponibilidad de espacios, mejorar la experiencia del usuario y proporcionar datos útiles para la gestión del estacionamiento?

#### ¿Quién es el usuario?

El sistema está dirigido principalmente a dos tipos de usuarios. Por un lado, los conductores que utilizan estacionamientos de gran tamaño, como centros comerciales, quienes buscan estacionar de manera rápida, sencilla y sin perder tiempo. Por otro lado, los administradores del estacionamiento, quienes requieren herramientas que les permitan monitorear, analizar y gestionar el uso de los espacios de forma eficiente.

#### ¿Dónde encaja nuestro producto en su vida?

Para los conductores, el producto se integra en el momento en que necesita estacionar su vehículo, ayudándolos a identificar espacios disponibles antes o durante su recorrido dentro del estacionamiento. También forma parte de su experiencia al permitirles recibir notificaciones relevantes y realizar el pago de manera digital sin necesidad de desplazarse a puntos físicos.

Para los administradores, el sistema se integra en su flujo de trabajo diario, proporcionando información en tiempo real y datos históricos que facilitan la toma de decisiones, la optimización de recursos y la mejora del servicio.

#### ¿Qué problemas tiene nuestro producto y cómo se pueden resolver?

- Dificultad para encontrar espacios disponibles.  
  Solución: Implementación de un sistema de sensores que detecta la ocupación en tiempo real y lo refleja en un mapa digital accesible desde la aplicación móvil.

- Falta de información estructurada para la gestión.  
  Solución: Desarrollo de una plataforma web con paneles de control que muestran estadísticas como ocupación por zonas, horarios de mayor demanda y uso de espacios.

- Problemas relacionados con el vehículo (mal estacionamiento u otros incidentes).  
  Solución: Uso de reconocimiento de placas para asociar vehículos con espacios y enviar notificaciones al usuario en caso de incidencias.

- Dificultad en el proceso de pago.  
  Solución: Integración de pagos digitales dentro de la aplicación móvil, permitiendo al usuario pagar desde cualquier lugar sin necesidad de acudir a máquinas físicas.

#### ¿Cómo y cuándo es usado nuestro producto?

El sistema se utiliza en diferentes momentos de la experiencia del usuario. Antes o al ingresar al estacionamiento, el conductor puede consultar la disponibilidad de espacios. Durante su permanencia, el sistema puede enviar notificaciones relacionadas con su vehículo. Al finalizar, el usuario puede realizar el pago del tiempo de estacionamiento directamente desde la aplicación.

Por su parte, los administradores utilizan la plataforma de manera continua para supervisar el estado del estacionamiento, revisar reportes, analizar patrones de uso y gestionar la operación.

#### ¿Qué características son importantes?

- Detección de ocupación mediante sensores.
- Mapa en tiempo real de espacios disponibles.
- Reconocimiento de placas.
- Notificaciones al usuario.
- Plataforma web con estadísticas.
- Pago digital desde app móvil.

#### ¿Cómo debe verse nuestro producto y cómo comportarse?

SpotFinder tiene como objetivo proporcionar a los centros comerciales un sistema IoT integral que permita automatizar la gestión de sus estacionamientos, incluyendo la detección de disponibilidad de espacios en tiempo real, el control de acceso vehicular mediante reconocimiento de placas, el guiado visual hacia espacios libres, el procesamiento de pagos digitales y el monitoreo de seguridad.

El problema se manifiesta en la forma ineficiente con la que actualmente se gestionan los estacionamientos en centros comerciales de Lima. La mayoría de estos establecimientos depende de sistemas basados en tickets físicos, personal de orientación manual y barreras mecánicas sin integración digital. Esto genera una cadena de ineficiencias: los conductores pierden tiempo excesivo buscando espacios libres, se forman cuellos de botella en rampas y accesos, no existe trazabilidad del vehículo dentro del estacionamiento, los procesos de cobro son lentos y propensos a errores, y la capacidad de respuesta ante emergencias es limitada.

Hemos identificado que esta deficiencia operativa tiene un impacto directo en tres dimensiones: la experiencia del conductor (frustración, pérdida de tiempo, inseguridad), la rentabilidad del centro comercial (menor rotación de espacios, menor tiempo de permanencia en tiendas, satisfacción del visitante) y el impacto ambiental (emisiones de CO₂ por vehículos circulando innecesariamente). La ausencia de datos en tiempo real también impide a los administradores tomar decisiones informadas sobre tarificación dinámica, asignación de personal y planificación de capacidad.

¿Cómo podríamos optimizar la gestión de estacionamientos en centros comerciales mediante tecnología IoT, proporcionando a los conductores información en tiempo real sobre disponibilidad de espacios y a los administradores herramientas de monitoreo y control?

**Domain:** La gestión de estacionamientos en centros comerciales de Lima sigue siendo un proceso predominantemente manual y desconectado, que genera congestión vehicular, pérdida de tiempo para los conductores y costos operativos elevados para los administradores.

**Customer Segments:**
- Conductores: Personas que visitan centros comerciales y necesitan encontrar estacionamiento de forma rápida, segura y conveniente, con opciones de pago digital.
- Administradores de estacionamiento: Personal operativo y gerencial de centros comerciales u operadores tercerizados que requieren herramientas para monitorear la ocupación, controlar accesos, generar reportes analíticos y responder eficientemente ante emergencias.

**Pain Points:**
- Tiempo excesivo buscando espacios libres dentro del estacionamiento (15-30 minutos en horas punta).
- Congestión en rampas y accesos internos por falta de guiado inteligente hacia zonas con disponibilidad.
- Procesos de cobro manuales que generan colas en las salidas y retardan la evacuación.
- Falta de trazabilidad del vehículo: el conductor olvida dónde estacionó su auto en estructuras de múltiples niveles.
- Incapacidad de los administradores para acceder a métricas de ocupación, rotación e ingresos en tiempo real.
- Respuesta lenta ante emergencias (incendio, fuga de gas) por falta de protocolos automatizados.

**Gap:** Actualmente no existe en el mercado peruano una solución IoT integral y accesible que combine detección de disponibilidad por espacio individual, reconocimiento de placas para control de acceso, guiado visual con LEDs, aplicación móvil para conductores y dashboard analítico para administradores, diseñada específicamente para las condiciones y necesidades de los centros comerciales de Lima.

**Vision/Strategy:** Desarrollar un sistema IoT de gestión inteligente de estacionamientos basado en ESP32, sensores ultrasónicos y reconocimiento de placas vehiculares, que se integre con una aplicación móvil para conductores y un dashboard web para administradores. El sistema será modular, escalable y de bajo costo, diseñado para implementarse de forma progresiva en centros comerciales de Lima.

**Initial Segment:** El lanzamiento se enfocará en centros comerciales medianos y grandes de Lima Metropolitana (500-5,000 espacios de estacionamiento), particularmente aquellos ubicados en distritos con alta congestión vehicular como Santiago de Surco, San Isidro, Miraflores e Independencia.

### 1.2.2.2. Lean UX Assumptions

#### Business Assumptions

- Creemos que nuestros clientes necesitan un sistema IoT que les brinde visibilidad en tiempo real sobre la disponibilidad de espacios y control automatizado del acceso vehicular en sus estacionamientos.
- Estas necesidades se pueden resolver con una plataforma que integre sensores ultrasónicos para detección de espacios, reconocimiento de placas para control de acceso, guiado visual con LEDs, una app móvil para conductores y un dashboard web para administradores.
- Nuestros clientes iniciales serán los centros comerciales medianos y grandes de Lima que actualmente operan con sistemas manuales o semi-automatizados y buscan modernizar su infraestructura de estacionamiento.
- El valor más importante que el cliente (centro comercial) quiere de nuestro servicio es aumentar la rotación de vehículos, reducir la congestión interna y mejorar la satisfacción de sus visitantes, lo que se traduce en mayor tiempo de permanencia en tiendas y mayor consumo.
- El cliente también puede obtener beneficios adicionales como reducción de costos operativos por personal de orientación, datos analíticos para tarificación dinámica, cumplimiento de protocolos de seguridad automatizados y diferenciación competitiva frente a otros centros comerciales.
- Vamos a adquirir la mayoría de nuestros clientes mediante demostraciones piloto en estacionamientos seleccionados, participación en ferias de tecnología y retail, y marketing B2B dirigido a gerentes de operaciones de centros comerciales.
- Generamos ingresos a través de un modelo de suscripción mensual basado en la cantidad de espacios monitoreados, con tres planes: Starter (hasta 200 espacios, sensores + app), Business (hasta 1,000 espacios, sensores + ALPR + analytics), Enterprise (más de 1,000 espacios, solución completa con integraciones personalizadas).
- Nuestra competencia principal en el mercado peruano son los operadores tradicionales como Apparka (con ALPR básico), soluciones internacionales de alto costo como ParkHelp, y los sistemas manuales existentes basados en tickets y personal de orientación.
- Los venceremos debido a que ofrecemos una solución IoT integral de bajo costo, diseñada específicamente para el mercado peruano, con reconocimiento de placas peruanas, integración con pasarelas de pago locales (Culqi, Yape) y soporte técnico local.
- El mayor riesgo del producto es la resistencia al cambio por parte de los operadores de estacionamiento y el costo percibido de la inversión inicial en infraestructura IoT.
- Resolveremos esto a través de un modelo de implementación progresiva (comenzando con una zona piloto), demostración de ROI con métricas de impacto desde el primer mes, y un modelo de suscripción que elimine la necesidad de inversión inicial elevada.

#### User Assumptions

- ¿Quién es el usuario? Conductores que visitan centros comerciales en Lima y buscan una experiencia de estacionamiento rápida, segura y sin fricciones; y administradores de estacionamiento que necesitan herramientas de monitoreo, control y análisis para optimizar la operación diaria.
- ¿Qué problemas tiene nuestro producto que debe resolver? Para los conductores: eliminar el tiempo perdido buscando espacios, ofrecer pago digital sin colas, brindar seguridad mediante trazabilidad del vehículo y facilitar la localización del auto al regresar. Para los administradores: proporcionar visibilidad en tiempo real de la ocupación, automatizar el control de acceso, generar reportes analíticos y habilitar protocolos de emergencia automatizados.
- ¿Qué características son importantes? Mapa interactivo de disponibilidad en tiempo real, reserva anticipada de espacios, guiado visual con LEDs, reconocimiento automático de placas, pago digital integrado (Yape, Culqi), notificaciones push, localización del vehículo, dashboard con métricas de ocupación y rotación, alertas de emergencia y control remoto de barreras.
- ¿Dónde encaja nuestro producto en su trabajo o vida? Los conductores lo usarán cada vez que visiten un centro comercial, desde la planificación del viaje hasta la salida. Los administradores lo usarán durante toda la jornada operativa para monitorear la ocupación, gestionar incidencias y tomar decisiones basadas en datos.
- ¿Cuándo y cómo es nuestro producto usado? Los conductores accederán desde su smartphone (iOS/Android) antes y durante la visita al centro comercial. Los administradores accederán desde el dashboard web en computadoras o tablets en la oficina de operaciones del estacionamiento, con acceso 24/7 a métricas y alertas.
- ¿Cómo debe verse nuestro producto y cómo debe comportarse? Debe ser moderno, intuitivo y responsivo, con respuestas en tiempo real (latencia menor a 2 segundos en la actualización de estados de espacios). La app móvil debe priorizar la simplicidad y la rapidez de uso en contextos de conducción (pantallas grandes, acciones mínimas). El dashboard debe ser profesional, con visualizaciones claras de datos y capacidad de drill-down en métricas.

### 1.2.2.3. Lean UX Hypothesis Statements

- **Hypothesis 01:** Creemos que los conductores que visitan centros comerciales adoptarán la aplicación móvil SpotFinder para consultar la disponibilidad de espacios en tiempo real y recibir guiado hacia espacios libres, reduciendo significativamente su tiempo de búsqueda.  
  Sabremos que hemos tenido éxito cuando al menos el 60% de los conductores que descarguen la app la utilicen activamente durante sus visitas al centro comercial en el primer mes, y el tiempo promedio de búsqueda de estacionamiento se reduzca en al menos un 50%.

- **Hypothesis 02:** Creemos que la implementación del sistema de reconocimiento automático de placas (ALPR) en las barreras de acceso eliminará la necesidad de tickets físicos y agilizará el proceso de ingreso y salida del estacionamiento.  
  Sabremos que hemos tenido éxito cuando el tiempo promedio de procesamiento en barrera se reduzca de 30-45 segundos (sistema de tickets) a menos de 5 segundos (ALPR), y al menos el 90% de las placas peruanas sean reconocidas correctamente en el primer intento.

- **Hypothesis 03:** Creemos que el sistema de guiado visual con LEDs (verde/rojo) instalado sobre cada espacio de estacionamiento reducirá la congestión interna y mejorará la experiencia del conductor al eliminar la incertidumbre sobre la disponibilidad de espacios en cada nivel.  
  Sabremos que hemos tenido éxito cuando la congestión en rampas internas se reduzca en al menos un 40% y el índice de satisfacción de los conductores con la experiencia de estacionamiento aumente en al menos un 30% respecto a la línea base, medido mediante encuestas post-visita.

- **Hypothesis 04:** Creemos que los administradores de estacionamiento adoptarán el dashboard analítico para tomar decisiones basadas en datos sobre tarificación, asignación de personal y planificación de capacidad.  
  Sabremos que hemos tenido éxito cuando al menos el 80% de los administradores consulten el dashboard diariamente y reporten una mejora de al menos 20% en la eficiencia operativa.

- **Hypothesis 05:** Creemos que la integración del pago digital (Yape, Culqi) eliminará las colas en las cabinas de cobro y mejorará la experiencia de salida del estacionamiento.  
  Sabremos que hemos tenido éxito cuando al menos el 50% de los pagos se realicen de forma digital en los primeros tres meses de operación, y el tiempo promedio de salida del estacionamiento se reduzca en al menos un 60%.
#### 1.2.2.4. Lean UX Canvas.

![Lean UX Canvas](./assets/lean-ux/LeanUX_canvas_v4.png)

## 1.3. Segmentos objetivo.
[Contenido]

---

# Capítulo II: Requirements Elicitation & Analysis

## 2.1. Competidores.
### 2.1.1. Análisis competitivo.
[Contenido]

### 2.1.2. Estrategias y tácticas frente a competidores.
[Contenido]

## 2.2. Entrevistas.
### 2.2.1. Diseño de entrevistas.
[Contenido]

### 2.2.2. Registro de entrevistas

## Segmento Objetivo 1

---

## Segmento Objetivo 2

**Segmento Administradores de estacionamientos: Entrevistado 1**

| Atributo                | Detalle |
|-------------------------|--------|
| **Nombre**              | Fabian Oliva |
| **Edad**                | 26 |
| **Sexo**                | Masculino |
| **Distrito**            | Surquillo |
| **Ocupación**           | Administrador de estacionamiento (Mall Plaza Angamos) |
| **Fecha de entrevista** | 11/04/2026 |
| **Timing**              | 00:00 - 04:59 |
| **Video**               | [Ver entrevista](#) |
| **Captura**             | ![Captura entrevista 1](./assets/images/screenshots/seg2entrevista1.png) |
| **Resumen**             | Fabian gestiona un estacionamiento de aproximadamente 850 espacios distribuidos en 5 niveles. Actualmente, la operación depende en gran medida de procesos manuales y herramientas básicas como Excel y sistemas de tickets, lo que limita la precisión y visibilidad en tiempo real. Enfrenta problemas de congestión en horas pico, dificultad de los usuarios para encontrar espacios y dependencia del personal para orientar el tráfico. No cuenta con analítica avanzada ni reportes automatizados. El sistema de cobro es parcialmente eficiente, pero presenta demoras. Considera valioso implementar soluciones como dashboards en tiempo real, guiado con LEDs, reconocimiento de placas (ALPR) y sistemas de seguridad automatizados. Está dispuesto a invertir si se demuestra un retorno claro. |

---

**Segmento Administradores de estacionamientos: Entrevistado 2**

| Atributo                | Detalle |
|-------------------------|--------|
| **Nombre**              | Nicole Requena Saiwa |
| **Edad**                | 28 |
| **Sexo**                | Femenino |
| **Distrito**            | Yanahuara, Arequipa |
| **Ocupación**           | Administradora de Operaciones de Estacionamiento |
| **Fecha de entrevista** | 9/04/2026 |
| **Timing**              | 00:00 - 05:00 |
| **Video**               | [Ver entrevista](#) |
| **Captura**             | ![Captura entrevista 2](./assets/images/screenshots/seg2entrevista2.png) |
| **Resumen**             | Administradora con aproximadamente 7 a 8 años de experiencia en la gestión de estacionamientos. Supervisa operaciones en espacios que superan los mil estacionamientos distribuidos en varios niveles. Actualmente, la gestión es mixta: cuenta con sistemas de conteo en entradas y salidas, pero el control interno sigue siendo mayormente manual, lo que limita la visibilidad en tiempo real por zonas específicas.\n\nEnfrenta problemas frecuentes como congestión en horas pico, dificultad de los conductores para encontrar espacios, desorden en momentos de alta demanda y reclamos constantes de los usuarios. No cuenta con estadísticas detalladas ni herramientas avanzadas de análisis, lo que dificulta la toma de decisiones.\n\nEl proceso de cobro se realiza mediante tickets físicos, generando colas y demoras en horas de alta afluencia. En situaciones de emergencia, la evacuación depende principalmente del personal, ya que no existe un sistema automatizado de guía.\n\nConsidera muy valiosas soluciones tecnológicas como dashboards en tiempo real, reportes automáticos, guiado visual con LEDs y reconocimiento de placas (ALPR), destacando especialmente su impacto en la eficiencia operativa y experiencia del cliente. Está dispuesta a implementar una solución IoT siempre que se demuestre un retorno claro, con un presupuesto estimado entre 20,000 y 50,000 dólares. |

---

**Segmento Administradores de estacionamientos: Entrevistado 3**

| Atributo                | Detalle |
|-------------------------|--------|
| **Nombre**              | [Nombre del entrevistado] |
| **Edad**                |  |
| **Sexo**                |  |
| **Distrito**            |  |
| **Ocupación**           |  |
| **Fecha de entrevista** |  |
| **Timing**              |  |
| **Video**               | [Ver entrevista](#) |
| **Captura**             | ![Captura entrevista 3](./assets/images/screenshots/interview-admin3.png) |
| **Resumen**             | [Completar resumen de la entrevista] |


El video completo de las entrevistas puede ser visualizado en el siguiente link:

### 2.2.3. Análisis de entrevistas



## 2.3. Needfinding

En la siguiente sección, analizaremos a nuestros segmentos objetivos para identificar sus necesidades y de acuerdo a ello ofrecer una solución óptima a sus problemas.

### 2.3.1. User Personas
**Segmento 1: Conductores que visitan centros comerciales**

<img src="/assets/requirements/personas/UserPersona1.png" alt="User persona - segmento 1" width="700"/>
<br><br>

**Segmento 2: Administradores de estacionamientos de centros comerciales**

<img src="/assets/requirements/personas/UserPersona2.png" alt="User persona - segmento 2" width="700"/>


### 2.3.2. User Task Matrix

Esta sección presenta las tareas que realizan los segmentos objetivo para cumplir sus objetivos dentro del contexto de los estacionamientos en centros comerciales. Las tareas identificadas se basan en el análisis de los User Personas y reflejan la situación actual del mercado. Cada tarea se evalúa según su Frecuencia e Importancia, utilizando las categorías Alta, Media y Baja.

**Segmento 1: Conductores que visitan centros comerciales**

| **Task Matrix**                                                     | **Frecuencia** | **Importancia** |
| ------------------------------------------------------------------- | -------------- | --------------- |
| Supervisar la ocupación de los espacios de estacionamiento          | Alta           | Alta            |
| Coordinar el ingreso y salida de vehículos                          | Alta           | Alta            |
| Gestionar al personal de seguridad y orientación                    | Alta           | Alta            |
| Controlar el uso de tickets y sistemas de cobro                     | Alta           | Alta            |
| Generar reportes de ingresos y ocupación                            | Alta           | Alta            |
| Establecer y actualizar tarifas del estacionamiento                 | Media          | Alta            |
| Supervisar la infraestructura y el mantenimiento de equipos         | Media          | Alta            |
| Resolver incidencias operativas y reclamos de usuarios              | Alta           | Alta            |
| Monitorear la congestión vehicular en horas punta                   | Alta           | Alta            |
| Registrar datos operativos en hojas de cálculo o sistemas básicos   | Media          | Alta            |
| Coordinar con proveedores de tecnología y mantenimiento             | Media          | Media           |
| Implementar mejoras para optimizar la operación del estacionamiento | Media          | Alta            |
| Garantizar el cumplimiento de protocolos de seguridad y emergencia  | Alta           | Alta            |
| Analizar estadísticas para la toma de decisiones estratégicas       | Media          | Alta            |
| Evaluar e implementar nuevas soluciones tecnológicas                | Baja           | Alta            |

<br>

**Segmento 2: Administradores de estacionamientos de centros comerciales**

| **Task Matrix**                                                              | **Frecuencia** | **Importancia** |
| ---------------------------------------------------------------------------- | -------------- | --------------- |
| Coordinar y asignar rutas a los camiones                                     | Alta           | Alta            |
| Cotizar precios y responder solicitudes de transporte                        | Alta           | Alta            |
| Gestionar la documentación de envío (guías de remisión, contratos, facturas) | Alta           | Alta            |
| Supervisar el estado y mantenimiento de los camiones                         | Media          | Alta            |
| Contactar y negociar con nuevos clientes                                     | Alta           | Alta            |
| Hacer seguimiento del transporte y ubicación de las unidades en tiempo real  | Alta           | Alta            |
| Controlar pagos, ingresos y liquidaciones con clientes y transportistas      | Alta           | Alta            |
| Publicar y responder mensajes en Facebook, WhatsApp y otras plataformas      | Alta           | Media           |
| Registrar datos de viajes, pagos y clientes en hojas de cálculo o cuadernos  | Media          | Alta            |
| Capacitarse en nuevas herramientas tecnológicas para optimizar procesos      | Baja           | Alta            |

#### Análisis de la User Task Matrix

##### Tareas más críticas

- Conductores:
    - Buscar espacios disponibles.
    - Estacionar el vehículo.
    - Realizar pagos y salir del estacionamiento.
    - Recordar la ubicación del automóvil.

- Administradores:
    - Supervisar la ocupación del estacionamiento.
    - Controlar accesos e ingresos.
    - Generar reportes operativos.
    - Gestionar incidencias y garantizar la seguridad.

##### Principales diferencias

| Conductores                                                                     | Administradores                                                   |
| ------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Se enfocan en encontrar estacionamiento rápidamente y pagar sin complicaciones. | Se enfocan en optimizar la operación y maximizar la rentabilidad. |
| Buscan comodidad y ahorro de tiempo.                                            | Buscan eficiencia operativa y control estratégico.                |
| Interactúan directamente con la infraestructura física.                         | Supervisan y gestionan el sistema en su totalidad.                |


### 2.3.3. User Journey Mapping

A continuación presentamos los User Journey Map que describen las experiencias actuales de nuestros segmentos objetivos. Se presenta el recorrido end-to-end desde la necesidad de visitar el establecimiento hasta la salida del estacionamiento. Este análisis permite identificar puntos críticos, frustraciones y oportunidades de mejora que justifican el desarrollo de SpotFinder.

**Segmento 1: Conductores que visitan centros comerciales**

<img src="/assets/requirements/maps/JourneyMap1.png" alt="Journey Map - segmento 1" width="750"/>
<br><br>

**Segmento 2: Administradores de estacionamientos de centros comerciales**

<img src="/assets/requirements/maps/JourneyMap2.png" alt="Journey Map - segmento 2" width="750"/>

### 2.3.4. Empathy Mapping

En esta sección se presenta el Empathy Map de nuestros segmentos objetivos. Este artefacto permite comprender sus pensamientos, emociones, necesidades y comportamientos. El análisis se basa en la información obtenida de entrevistas, observación del contexto actual y estudio de soluciones existentes en el mercado. Su propósito es identificar los principales pains y gains, los cuales servirán como base para el diseño de la solución SpotFinder.

**Segmento 1: Conductores que visitan centros comerciales**

<img src="/assets/requirements/maps/EmpathyMap1.png" alt="Empathy Map - segmento 1" width="700"/>
<br><br>

**Segmento 2: Administradores de estacionamientos de centros comerciales**

<img src="/assets/requirements/maps/EmpathyMap2.png" alt="Empathy Map - segmento 2" width="700"/>


## 2.4. Big Picture Event Storming  

El Big Picture Event Storming es una técnica que permite identificar los eventos más relevantes dentro del sistema, los actores involucrados y la relación entre los distintos componentes. Su propósito es comprender de manera integral el flujo del negocio y detectar oportunidades de mejora en la gestión del estacionamiento.

En el contexto del sistema propuesto, se analizaron los eventos que ocurren desde que el usuario consulta la disponibilidad de espacios hasta que finaliza su experiencia dentro del estacionamiento. Asimismo, se incluyeron procesos adicionales como el monitoreo en tiempo real, la reserva de espacios, el pago digital y la solicitud de servicios.

---

## 2.4.1. EventStorming  

La actividad de Event Storming se realizó de forma colaborativa con la participación de los integrantes del equipo, utilizando un mural digital como soporte visual en la plataforma de Whiteboard. Durante la sesión se emplearon notas adhesivas para representar eventos de dominio, acciones del usuario, actores del sistema y otros elementos clave.

El objetivo principal fue construir una visión global del sistema, comprendiendo cómo interactúan sus componentes a lo largo del tiempo. Además, se buscó identificar puntos críticos del proceso y establecer una base para la definición de bounded contexts en etapas posteriores.

---

### Antes de la sesión  

Se habilitó un espacio de trabajo digital en el cual se organizaron los elementos necesarios para la dinámica. Se definieron lineamientos básicos para fomentar la participación activa y se estableció que todas las ideas propuestas serían consideradas. El enfoque estuvo orientado a promover la exploración libre del dominio.

![DDD0](./assets/diagrams/ddd/es-0.png)

---

### Durante la sesión  

#### Unstructured Exploration  

Se inició con una fase de exploración libre, en la que los participantes identificaron eventos relevantes sin seguir un orden específico. Entre los eventos destacados se encuentran la detección de vehículos, la ocupación de espacios, el inicio de sesiones de estacionamiento, la generación de pagos y el envío de notificaciones. Esta etapa permitió obtener una visión amplia del sistema.

![DDD1](./assets/diagrams/ddd/es-1.png)

---

#### Timelines  

Una vez recopilados los eventos, se procedió a organizarlos en una secuencia temporal. Se estructuraron en diferentes etapas del sistema, tales como ingreso, monitoreo de espacios, reserva, pago y salida. Esto permitió visualizar claramente el flujo del proceso y las interacciones entre eventos.

![DDD2.1](./assets/diagrams/ddd/es-2-1.png)
![DDD2.2](./assets/diagrams/ddd/es-2-2.png)

---

#### Pain Points  

Durante el análisis del flujo, se identificaron puntos problemáticos y áreas de incertidumbre. Entre ellos destacan la dificultad para encontrar espacios disponibles, la falta de información en tiempo real, posibles errores en sensores y limitaciones en el proceso de pago. Estos aspectos fueron señalados para su posterior mejora.

![DDD3.1](./assets/diagrams/ddd/es-3-1.png)
![DDD3.2](./assets/diagrams/ddd/es-3-2.png)

---

#### Pivotal Points  

Se identificaron eventos clave que representan cambios significativos en el sistema, como el inicio de la sesión de estacionamiento, la confirmación del pago y la liberación de un espacio. Estos eventos son fundamentales para comprender la dinámica del sistema y definir sus límites funcionales.

![DDD4.1](./assets/diagrams/ddd/es-4-1.png)
![DDD4.2](./assets/diagrams/ddd/es-4-2.png)

---

#### Commands  

Se determinaron las acciones que generan los eventos dentro del sistema. Entre ellas se incluyen consultar disponibilidad, estacionar un vehículo, realizar un pago y solicitar servicios adicionales. Esto permitió entender cómo interactúan los usuarios con la solución.

![DDD5.1](./assets/diagrams/ddd/es-5-1.png)
![DDD5.2](./assets/diagrams/ddd/es-5-2.png)

---

#### Policies  

Se establecieron reglas que controlan el comportamiento del sistema frente a ciertos eventos. Por ejemplo, el envío automático de notificaciones cuando el tiempo de estacionamiento está por finalizar, la validación de pagos antes de permitir la salida y la actualización del estado de los espacios en función de los sensores.

![DDD6.1](./assets/diagrams/ddd/es-6-1.png)
![DDD6.2](./assets/diagrams/ddd/es-6-2.png)


---

#### Read Models  

Se identificaron las vistas necesarias para mostrar información relevante a los usuarios. Estas incluyen el mapa de estacionamiento en tiempo real, el panel del administrador, el resumen de pagos y la visualización de servicios solicitados.

![DDD7.1](./assets/diagrams/ddd/es-7-1.png)
![DDD7.2](./assets/diagrams/ddd/es-7-2.png)

---

#### External Systems  

Se reconocieron los sistemas externos que interactúan con la solución, como las plataformas de pago, los sensores IoT y los servicios adicionales. Esto permitió identificar puntos de integración y dependencia.

![DDD8.1](./assets/diagrams/ddd/es-8-1.png)
![DDD8.2](./assets/diagrams/ddd/es-8-2.png)
![DDD8.3](./assets/diagrams/ddd/es-8-3.png)

---

#### Aggregates  

Se agruparon los elementos del dominio en entidades principales, tales como usuario, vehículo, espacio de estacionamiento, sesión de estacionamiento, pago y servicio. Estas agrupaciones permiten definir unidades de consistencia dentro del sistema.

![DDD9](./assets/diagrams/ddd/es-9.png)

---

#### Bounded Contexts  

Finalmente, se delimitaron los bounded contexts a partir de los eventos, agregados y relaciones identificadas. Estos contextos representan diferentes áreas del sistema, como ingreso, monitoreo, reserva, pago y gestión administrativa, y servirán como base para el diseño de la arquitectura del software.

![DDD10](./assets/diagrams/ddd/es-10.png)

## 2.5. Ubiquitous Language.

| Término            | Equivalente                     | Definición                                                                 |
|--------------------|--------------------------------|---------------------------------------------------------------------------|
| Driver             | Conductor                      | Usuario que utiliza el estacionamiento para ubicar, estacionar y pagar.   |
| Administrator      | Administrador                  | Encargado de supervisar y gestionar el sistema de estacionamiento.        |
| Parking Space      | Espacio de estacionamiento     | Espacio físico donde un vehículo puede estacionarse.                      |
| Occupancy          | Estado de ocupación            | Estado de un espacio, indicando si está libre u ocupado.                  |
| Vehicle            | Vehículo                       | Medio de transporte registrado dentro del sistema.                        |
| License Plate      | Placa del vehículo             | Identificador único asociado a cada vehículo.                             |
| Parking Session    | Sesión de estacionamiento      | Periodo de tiempo en el que un vehículo permanece estacionado.            |
| Payment            | Pago del estacionamiento       | Proceso mediante el cual el usuario paga por el tiempo de estacionamiento.|
| Service            | Servicio adicional             | Servicio solicitado para el vehículo, como lavado u otros.                |
| Notification       | Notificación                   | Mensaje enviado al usuario con información relevante del sistema.         |
| IoT Sensor System  | Sistema de sensores IoT        | Dispositivos que detectan la ocupación de los espacios en tiempo real.    |
| Payment System     | Sistema de pagos               | Plataforma externa que procesa los pagos digitales.                       |
| Space Detection    | Detección de espacios          | Proceso de identificación de espacios libres u ocupados mediante sensores.|
| Availability Check | Consulta de disponibilidad     | Acción de verificar los espacios disponibles en el estacionamiento.       |
| Parking Management | Gestión de estacionamiento     | Proceso completo desde el ingreso hasta la salida del vehículo.           |
| Notification Handling | Gestión de notificaciones   | Proceso de envío y recepción de alertas dentro del sistema.               |
| Payment Processing | Procesamiento de pagos         | Gestión de transacciones digitales realizadas por los usuarios.           |
| Service Management | Gestión de servicios           | Proceso de solicitud y ejecución de servicios adicionales.                |

---

# Capítulo III: Requirements Specification

## 3.1. User Stories.

## 3.2. Impact Mapping.

## 3.3. Product Backlog.

---

# Capítulo IV: Product Design

## 4.1. Style Guidelines.
### 4.1.1. General Style Guidelines.

### 4.1.2. Web Style Guidelines.

## 4.2. Information Architecture.
### 4.2.1. Organization Systems.

### 4.2.2. Labeling Systems.

### 4.2.3. SEO Tags and Meta Tags

### 4.2.4. Searching Systems.

### 4.2.5. Navigation Systems.

## 4.3. Landing Page UI Design.
### 4.3.1. Landing Page Wireframe.

### 4.3.2. Landing Page Mock-up.

## 4.4. Web Applications UX/UI Design.
### 4.4.1. Web Applications Wireframes.

### 4.4.2. Web Applications Wireflow Diagrams.

### 4.4.2. Web Applications Mock-ups.

### 4.4.3. Web Applications User Flow Diagrams.

## 4.5. Web Applications Prototyping.

## 4.6. Domain-Driven Software Architecture.
### 4.6.1. Design-Level Event Storming.

### 4.6.2. Software Architecture Context Diagram.

### 4.6.3. Software Architecture Container Diagrams.

### 4.6.4. Software Architecture Components Diagrams.

## 4.7. Software Object-Oriented Design.
### 4.7.1. Class Diagrams.

## 4.8. Database Design.
### 4.8.1. Database Diagrams.

---

# Capítulo V: Product Implementation, Validation & Deployment

## 5.1. Software Configuration Management.
### 5.1.1. Software Development Environment Configuration.
### 5.1.2. Source Code Management.
### 5.1.3. Source Code Style Guide & Conventions.
### 5.1.4. Software Deployment Configuration.

## 5.2. Landing Page, Services & Applications Implementation.
### 5.2.X. Sprint n
#### 5.2.X.1. Sprint Planning n.
#### 5.2.X.2. Aspect Leaders and Collaborators.
#### 5.2.X.3. Sprint Backlog n.
#### 5.2.X.4. Development Evidence for Sprint Review.
#### 5.2.X.5. Execution Evidence for Sprint Review.
#### 5.2.X.6. Services Documentation Evidence for Sprint Review.
#### 5.2.X.7. Software Deployment Evidence for Sprint Review.
#### 5.2.X.8. Team Collaboration Insights during Sprint.

## 5.3. Validation Interviews.
### 5.3.1. Diseño de Entrevistas.
### 5.3.2. Registro de Entrevistas.
### 5.3.3. Evaluaciones según heurísticas.

## 5.4. Video About-the-Product.

---

# Conclusiones
## Conclusiones y recomendaciones.
## Video About-the-Team.

---

# Bibliografía

---

# Anexos
