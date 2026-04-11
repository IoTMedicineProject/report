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

En el desarrollo y despliegue de **SpotFinder**, hemos identificado dos grupos clave que se beneficiarán directamente de nuestra solución: los usuarios finales (conductores) y nuestros clientes corporativos (administradores).


#### Primer segmento Objetivo: Conductores que visitan centros comerciales

Los conductores constituyen el segmento principal de usuarios finales de SpotFinder. A nivel de infraestructura y adopción tecnológica, el mercado presenta un escenario ideal para la integración de la app:

> **Datos clave del mercado:**
> * Lima concentra aprox. **2.4 millones de vehículos** (68.6% del parque automotor nacional).
> * El parque automotor creció un **40%** en la última década, frente a un crecimiento vial de solo el **7%** (IPE y AAP).
> * El **93.2%** de los usuarios de internet en Lima Metropolitana accede a través de un smartphone (INEI, 2024).

Esta alta penetración móvil y la popularidad de billeteras digitales (como Yape y Plin) refuerzan la viabilidad de nuestra solución y sus pagos integrados.

##### Perfil del Usuario (Conductor)
* **Edad:** 25 a 55 años (mayor proporción de propietarios de vehículos y visitantes frecuentes).
* **Nivel Socioeconómico:** Segmentos A, B y C. *(Dato: El 70.1% del segmento A considera urgente incrementar la disponibilidad de estacionamientos).*
* **Necesidad Principal:** Encontrar espacio rápidamente, pagos sin fricciones, localización exacta del vehículo al regresar y seguridad/confianza durante su visita.
* **Adopción Tecnológica:** Alta familiaridad con apps de servicio (Yape, Rappi, Uber, Google Maps) y apertura hacia herramientas que simplifiquen su rutina diaria.

#### Segundo segmento objetivo: Administradores de Estacionamientos 

Este segmento engloba al personal operativo de los centros comerciales y a las empresas tercerizadas que gestionan la infraestructura. 

Actualmente, gran parte de los operadores en Perú (como Apparka, que lidera el mercado con ~300 estacionamientos) aún dependen de modelos semi-manuales: personal de orientación, tickets físicos y reportería artesanal. SpotFinder busca digitalizar y optimizar estas operaciones.

##### Perfil del Cliente (Administrador)
* **Edad:** 30 a 55 años (Personal operativo y gerencial).
* **Perfil Profesional:** Gerentes de operaciones, jefes de seguridad, coordinadores de mantenimiento y personal de TI. Formación técnica o universitaria en administración, ingeniería industrial o afines.
* **Necesidad Principal:** * Visibilidad en tiempo real de la ocupación.
  * Automatización del control de accesos.
  * Reducción de costos operativos (personal de orientación).
  * Generación de reportes analíticos para toma de decisiones.
  * Cumplimiento de protocolos de seguridad y emergencia.
* **Adopción Tecnológica:** Conocimiento intermedio/avanzado. Usuarios habituales de *dashboards*, ERPs y sistemas de gestión. Requieren interfaces visuales, intuitivas y accionables en web y tablets.

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

### 2.2.2. Registro de entrevistas.
[Contenido]

### 2.2.3. Análisis de entrevistas.
[Contenido]

## 2.3. Needfinding.
### 2.3.1. User Personas.
[Contenido]

### 2.3.2. User Task Matrix.
[Contenido]

### 2.3.3. User Journey Mapping.
[Contenido]

### 2.3.4. Empathy Mapping.
[Contenido]

## 2.4. Big Picture Event Storming.
[Contenido]

## 2.5. Ubiquitous Language.
[Contenido]

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
