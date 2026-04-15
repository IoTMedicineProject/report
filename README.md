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

### 2.2.2. Registro de entrevistas

## Segmento Objetivo 1

### 2.2.2. Registro de entrevistas

## Segmento Objetivo 1

#### **Entrevista 1**
| Atributo | **Datos Personales** |
| :--- | :--- |
| **Nombres** | Maria Fernanda |
| **Apellidos** | Esteban Román |
| **Distrito** | Surco |
| **Edad** | 21 años |
| **Fecha de entrevista** | 11/04/2026 |
| **Timing**              | 00:00-03:05 |
| **Enlace** | [🔗 Ver grabación de la entrevista](https://1drv.ms/v/c/e7943890401aebc7/IQCsVfJnUhn9RJWEkmDyCX2pAQnBlD9IkX-cMPJdZnQzPF0?e=uymIhe) |

**Evidencia**
![Captura de la entrevista 1](./assets/images/screenshots/seg1entrevista1.jpeg)

**Resumen**
Estudiante universitaria que visita centros comerciales como el Jockey Plaza dos veces por semana. Su principal frustración es la pérdida de tiempo (15-20 minutos) buscando estacionamiento y la falta de información real sobre la disponibilidad en los sótanos. Usuario activo de herramientas tecnológicas como Waze y Yape, considera que un sistema de guiado por luces LED y una app con disponibilidad en tiempo real serían determinantes para mejorar su experiencia y reducir el estrés.

---

#### **Entrevista 2**
|Atributo | **Datos Personales** |
| :--- | :--- |
| **Nombres** | Freddy Carlos |
| **Apellidos** | Alvarez |
| **Distrito** | Miraflores |
| **Edad** | 22 años |
| **Fecha de entrevista** | 11/04/2026 |
| **Timing**              | 03:05-05:38 |
| **Enlace** | [🔗 Ver grabación de la entrevista](https://1drv.ms/v/c/e7943890401aebc7/IQCsVfJnUhn9RJWEkmDyCX2pAQnBlD9IkX-cMPJdZnQzPF0?e=uymIhe) |

**Evidencia**
![Captura de la entrevista 2](./assets/images/screenshots/seg1entrevista2.png)
  
**Resumen**
Usuario frecuente de estacionamientos en centros comerciales que prioriza la seguridad y la eficiencia en el pago. Reporta una alta frustración debido a las largas colas en los cajeros físicos y la dificultad de encontrar espacios en temporadas altas. Valora positivamente la automatización mediante el reconocimiento de placas vehiculares (ALPR) y la posibilidad de realizar pagos digitales a través de la app, lo cual considera una solución necesaria para modernizar el servicio actual.

---

#### **Entrevista 3**
| Atributo | **Datos Personales** |
| :--- | :--- |
| **Nombres** | Diego Ignacio |
| **Apellidos** | Ricra Falla |
| **Distrito** | San Borja |
| **Edad** | 24 años |
| **Fecha de entrevista** | 11/04/2026 |
| **Timing**              | 05:38-09:32|
| **Enlace** | [🔗 Ver grabación de la entrevista](https://1drv.ms/v/c/e7943890401aebc7/IQCsVfJnUhn9RJWEkmDyCX2pAQnBlD9IkX-cMPJdZnQzPF0?e=uymIhe) |

**Evidencia**
![Captura de la entrevista 3](./assets/images/screenshots/seg1entrevista3.png)


**Resumen**
Estudiante  joven que utiliza el vehículo para movilizarse a reuniones y recados, visitando malls hasta tres veces por semana. Su mayor problema es la desorientación dentro del estacionamiento (olvida la ubicación del vehículo) y la falta de métodos de pago prácticos cuando no cuenta con efectivo. [Se muestra muy interesado en las funciones de reserva de espacios con anticipación y en recibir notificaciones de seguridad en su smartphone para mayor tranquilidad durante su estancia.

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
| **Timing**              | 09:32-12:51|
| **Video**               | [Ver entrevista](https://1drv.ms/v/c/e7943890401aebc7/IQCsVfJnUhn9RJWEkmDyCX2pAQnBlD9IkX-cMPJdZnQzPF0?e=uymIhe) |
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
| **Timing**              | 12:51	19:36|
| **Video**               | [Ver entrevista](https://1drv.ms/v/c/e7943890401aebc7/IQCsVfJnUhn9RJWEkmDyCX2pAQnBlD9IkX-cMPJdZnQzPF0?e=uymIhe) |
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
| **Timing**              | 19:36-22:56 |
| **Video**               | [Ver entrevista](https://1drv.ms/v/c/e7943890401aebc7/IQCsVfJnUhn9RJWEkmDyCX2pAQnBlD9IkX-cMPJdZnQzPF0?e=uymIhe) |
| **Captura**             | ![Captura entrevista 3](./assets/images/screenshots/interview-admin3.png) |
| **Resumen**             | [Completar resumen de la entrevista] |


El video completo de las entrevistas puede ser visualizado en el siguiente link:

### 2.2.3. Análisis de entrevistas



## 2.3. Needfinding

En la siguiente sección, analizaremos a nuestros segmentos objetivos para identificar sus necesidades y de acuerdo a ello ofrecer una solución óptima a sus problemas.

### 2.3.1. User Personas
**Segmento 1: Conductores que visitan centros comerciales**

<img src="assets/requirements/personas/UserPersona1.png" alt="User persona - segmento 1" width="700"/>
<br><br>    

**Segmento 2: Administradores de estacionamientos de centros comerciales**

<img src="assets/requirements/personas/UserPersona2.png" alt="User persona - segmento 2" width="700"/>


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

<img src="assets/requirements/maps/JourneyMap1.png" alt="Journey Map - segmento 1" width="750"/>
<br><br>
**Segmento 2: Administradores de estacionamientos de centros comerciales**

<img src="assets/requirements/maps/JourneyMap2.png" alt="Journey Map - segmento 2" width="750"/>  
### 2.3.4. Empathy Mapping

En esta sección se presenta el Empathy Map de nuestros segmentos objetivos. Este artefacto permite comprender sus pensamientos, emociones, necesidades y comportamientos. El análisis se basa en la información obtenida de entrevistas, observación del contexto actual y estudio de soluciones existentes en el mercado. Su propósito es identificar los principales pains y gains, los cuales servirán como base para el diseño de la solución SpotFinder.

**Segmento 1: Conductores que visitan centros comerciales**

<img src="assets/requirements/maps/EmpathyMap1.png" alt="Empathy Map - segmento 1" width="750"/>
<br><br>

**Segmento 2: Administradores de estacionamientos de centros comerciales**

<img src="assets/requirements/maps/EmpathyMap2.png" alt="Empathy Map - segmento 2" width="750"/>

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
#### Epics :
 grandes funcionalidades que pueden descomponerse en varias historias más pequeñas.
 #### User Stories (US) :
 funcionalidades específicas que aportan valor directo al usuario.
Static Web Stories (SWS): historias relacionadas con la presentación y navegación en la interfaz web para los diferentes segmentos identificados.
 #### Technical Stories (TS):
 historias que abordan aspectos técnicos necesarios para el correcto funcionamiento del sistema, como la integración con servicios externos, seguridad, rendimiento, entre otros.
  #### Spike Stories (SS):
 historias que representan tareas de investigación o exploración técnica para resolver incertidumbres o evaluar alternativas antes de la implementación. Nota: Las Spike Stories se presentan aquí de manera resumida. Para un detalle completo, incluyendo criterios de aceptación y escenarios específicos, por favor véase el Anexo F: Detalle de Spike Stories.

 | Story ID | User | Title | Description | Acceptance Criteria | Priority | Epic |
|---|---|---|---|---|---|---|
| EP01 | Administrador | Monitoreo de Ocupación IoT | Como administrador, deseo que el sistema detecte automáticamente la ocupación mediante sensores para tener visibilidad en tiempo real. | — | Alta | — |
| EP02 | Administrador | Control de Acceso Vehicular | Como administrador, deseo identificar vehículos mediante ALPR para controlar ingreso y salida sin tickets físicos. | — | Alta | — |
| EP03 | Conductor | Visualización de Estacionamiento | Como conductor, deseo visualizar en tiempo real la disponibilidad de espacios para encontrar lugar rápidamente. | — | Alta | — |
| EP04 | Conductor | Sistema de Pagos | Como conductor, deseo realizar pagos digitales desde la app para evitar colas en cabinas. | — | Alta | — |
| EP05 | Administrador | Gestión Administrativa y Dashboard | Como administrador, deseo gestionar el estacionamiento mediante un dashboard web para controlar la operación. | — | Alta | — |
| EP06 | Administrador | Analítica y Reportes | Como administrador, deseo visualizar estadísticas y métricas para tomar decisiones informadas. | — | Media | — |
| EP07 | Usuario | Notificaciones | Como usuario, deseo recibir notificaciones relevantes sobre mi vehículo y el estacionamiento. | —| Media | — |
| EP08 | Administrador | Seguridad y Emergencias | Como administrador, deseo que el sistema detecte condiciones peligrosas y active protocolos automáticamente. | — | Alta | — |
| EP09 | Conductor | Servicios Adicionales y Wallet | Como conductor Premium, deseo acceder a servicios adicionales y pase digital de estancia. |— | Baja | — |
| EP10 | Usuario | Autenticación y Gestión de Usuarios | Como usuario, deseo registrarme, iniciar sesión y gestionar mi cuenta de forma segura. |— | Alta | — |
| EP11 | Visitante | Experiencia en Landing Page | Como visitante, deseo comprender el propósito del sistema a través de una landing page intuitiva. | — | Baja | — |
| EP12 | Developer | Servicios RESTful API | Como developer, deseo implementar endpoints RESTful para la interacción entre frontend y backend. | — | Alta | — |
| EP13 | Equipo de Desarrollo | Investigación y Prototipado | Como equipo de desarrollo, deseo realizar investigación técnica para resolver incertidumbres antes de implementar. | — | Alta | — |

 | |  | | |  |  |  |
|---|---|---|---|---|---|---|
| US01 | Administrador | Detección de ocupación por sensores | Como administrador, deseo que los sensores ultrasónicos detecten automáticamente si un espacio está ocupado o libre para tener información precisa sin intervención manual. | Scenario 1: Given sensor detecta objeto  When edge server procesa Then estado cambia a "Occupied" y LED a rojo. Scenario 2: Given sensor detecta ausencia When procesa Then estado cambia a "Available" y LED a verde. Scenario 3: Given lectura intermitente When procesa Then estado no cambia (debounce). | Alta | EP01 |
| US02 | Conductor | Visualización de espacios en tiempo real | Como conductor, deseo ver  en tiempo real de los espacios disponibles y ocupados en la app móvil para encontrar estacionamiento rápidamente. | Scenario 1: Given conductor accede a la información When carga información Then muestra espacios con colores (verde=libre, rojo=ocupado). Scenario 2: Given sensor cambia estado When sistema actualiza Then referencia  refleja cambio. | Alta | EP03 |
| US03 | Conductor | Ingreso automático con ALPR | Como conductor registrado, deseo que al llegar a la barrera, el sistema reconozca mi placa y abra la barrera sin ticket. | Scenario 1: Given conductor registrado llega When ALPR reconoce placa Then barrera se abre y sesión inicia. Scenario 2: Given placa no reconocida tras 3 intentos When sistema agota reintentos Then emite ticket temporal. Scenario 3: Given conductor no registrado When se captura placa Then crea sesión asociada a esa placa. | Alta | EP02 |
| US04 | Conductor | Salida automática con verificación de pago | Como conductor, deseo que al salir, el sistema verifique mi pago y abra la barrera automáticamente. | Scenario 1: Given conductor con pago completado When ALPR reconoce placa y estado "Paid" Then barrera se abre y sesión se cierra. Scenario 2: Given conductor sin pagar When ALPR reconoce placa Then barrera cerrada y envía notificación push con enlace de pago. | Alta | EP02 |
| US05 | Conductor | Pago digital del estacionamiento | Como conductor, deseo pagar desde la app con Yape o tarjeta para evitar colas. | Scenario 1: Given conductor elige Yape When confirma y Culqi procesa Then muestra confirmación con monto y recibo. Scenario 2: Given pago falla When Culqi retorna error Then muestra mensaje y ofrece reintentar. Scenario 3: Given pago con tarjeta When ingresa datos y confirma Then procesa y muestra recibo. | Alta | EP04 |
| US06 | Administrador | Dashboard de monitoreo en tiempo real | Como administrador, deseo un panel con ocupación en tiempo real para supervisar la operación. | Scenario 1: Given admin accede al dashboard When carga Then muestra plano interactivo con espacios y colores. Scenario 2: Given espacio cambia estado When sensor actualiza Then dashboard refleja sin refrescar. Scenario 3: Given admin accede When carga Then muestra tasa de ocupación, espacios libres y ocupados. | Alta | EP05 |
| US07 | Conductor | Find My Car | Como conductor, deseo localizar mi vehículo en el estacionamiento para encontrarlo al regresar. | Scenario 1: Given conductor con sesión activa When accede a "Find My Car" Then muestra código del espacio. Scenario 2: Given sin sesión activa When intenta consultar Then indica que no hay vehículo. | Alta | EP03 |
| US08 | Conductor | Visualización de tiempo y costo estimado | Como conductor, deseo ver el tiempo estacionado y costo acumulado para saber cuánto pagaré. | Scenario 1: Given sesión activa When consulta detalles Then muestra hora ingreso, duración y monto. Scenario 2: Given tiempo avanza When consulta de nuevo Then monto se actualiza dinámicamente. | Media | EP04 |
| US09 | Conductor | Espacios recomendados | Como conductor, deseo que el sistema me sugiera espacios cercanos disponibles para reducir tiempo de búsqueda. | Scenario 1: Given conductor consulta disponibilidad When sistema procesa Then sugiere espacios más cercanos. Scenario 2: Given múltiples espacios When muestra opciones Then prioriza los más próximos. | Media | EP03 |
| US10 | Conductor | Notificaciones de eventos del vehículo | Como conductor, deseo recibir notificaciones push sobre eventos relevantes de mi vehículo. | Scenario 1: Given vehículo ingresa When ALPR identifica Then recibe notificación de ingreso. Scenario 2: Given pago pendiente en salida When sistema detecta Then recibe notificación con enlace de pago. Scenario 3: Given emergencia activa When protocolo se dispara Then todos los conductores reciben alerta. | Media | EP07 |
| US11 | Administrador | Gestión de disponibilidad de espacios | Como administrador, deseo habilitar/deshabilitar espacios para gestionar mantenimientos. | Scenario 1: Given admin selecciona espacio When marca "Out of Service" Then deja de aparecer disponible y LED se apaga. Scenario 2: Given admin reactiva espacio When marca "Active" Then vuelve a ser monitoreado. | Media | EP05 |
| US12 | Administrador | Estadísticas de ocupación | Como administrador, deseo visualizar estadísticas para identificar patrones y optimizar gestión. | Scenario 1: Given admin accede a estadísticas When selecciona rango de fechas Then muestra gráficos de ocupación, horas punta y rotación. Scenario 2: Given datos históricos When consulta Then presenta comparativos con tendencias. | Media | EP06 |
| US13 | Administrador | Generación de reportes | Como administrador, deseo generar reportes de ocupación e ingresos para presentar a gerencia. | Scenario 1: Given admin selecciona período When genera reporte Then produce PDF descargable. Scenario 2: Given sin datos para período When intenta Then indica que no hay datos. | Media | EP06 |
| US14 | Administrador | Detección y alerta de emergencia | Como administrador, deseo que el sistema detecte gas/humo y active protocolos automáticamente. | Scenario 1: Given sensor MQ-2 detecta gas > 900 PPM When edge server procesa Then activa protocolo: LEDs rojo intermitente, barreras abiertas, alerta a admin. Scenario 2: Given emergencia activa When admin marca "Resolved" Then restaura operación normal. | Alta | EP08 |
| US15 | Conductor | Historial de pagos | Como conductor, deseo ver mi historial de pagos para llevar registro de gastos. | Scenario 1: Given conductor con pagos When accede al historial Then muestra lista con fecha, duración, monto y método. Scenario 2: Given sin pagos When accede Then indica que no hay registros. | Baja | EP04 |
| US16 | Conductor | Generación de pase digital (Google Wallet) | Como conductor Premium, deseo recibir un pase digital en Google Wallet al ingresar para ver info de estancia sin abrir app. | Scenario 1: Given conductor Premium ingresa When ALPR identifica Then recibe notificación para añadir pase con placa, hora, QR. Scenario 2: Given pase activo When paga Then pase cambia a verde y QR se activa para salida. | Baja | EP09 |
| US17 | Conductor | Solicitud de servicio de lavado | Como conductor Premium, deseo solicitar lavado desde la app mientras mi auto está estacionado. | Scenario 1: Given conductor Premium When selecciona "Lavado" y confirma Then registra solicitud con tiempo estimado. Scenario 2: Given conductor Free/Pro When intenta Then indica que debe actualizar plan. | Baja | EP09 |
| US18 | Conductor | Registro de usuario conductor | Como conductor nuevo, deseo registrarme proporcionando datos personales y placa para acceder al sistema. | Scenario 1: Given datos válidos When envía formulario Then cuenta se crea y recibe email de confirmación. Scenario 2: Given email ya registrado When intenta Then muestra que email está en uso. Scenario 3: Given campos vacíos When intenta enviar Then muestra errores específicos. | Alta | EP10 |
| US19 | Administrador | Registro de usuario administrador | Como administrador de centro comercial, deseo registrarme para acceder al dashboard. | Scenario 1: Given datos válidos When envía Then cuenta con rol admin y confirmación. Scenario 2: Given datos inválidos When intenta Then muestra errores. | Alta | EP10 |
| US20 | Usuario | Inicio de sesión | Como usuario registrado, deseo iniciar sesión de forma segura. | Scenario 1: Given credenciales válidas When inicia sesión Then accede según rol. Scenario 2: Given credenciales incorrectas When intenta Then muestra error genérico. | Alta | EP10 |
| US21 | Usuario | Recuperación de contraseña | Como usuario, deseo recuperar mi contraseña en caso de olvidarla. | Scenario 1: Given correo registrado When solicita Then recibe enlace. Scenario 2: Given correo no registrado When solicita Then muestra mensaje genérico. | Media | EP10 |
| US22 | Usuario | Edición de perfil | Como usuario, deseo editar mi información personal para mantener cuenta actualizada. | Scenario 1: Given datos válidos When guarda Then perfil se actualiza. Scenario 2: Given datos inválidos When intenta Then muestra errores. | Baja | EP10 |
| US23 | Conductor | Registro de vehículo adicional | Como conductor, deseo registrar más de un vehículo para usar el sistema con cualquiera de mis autos. | Scenario 1: Given cuenta activa When agrega vehículo con placa válida Then se asocia. Scenario 2: Given placa ya registrada When intenta Then indica que placa está en uso. | Baja | EP10 |

 
| | || |  |  |  |
|---|---|---|---|---|---|---|
| TS01 | Developer | Exponer endpoint para registrar lectura de sensor | Como developer, deseo exponer POST /api/v1/sensor-readings para recibir lecturas de sensores desde el edge server. | Scenario 1: Given datos válidos (sensorId, slotId, distance, timestamp) When servidor procesa Then almacena y devuelve 201 Created. Scenario 2: Given sensorId no registrado When procesa Then devuelve 404 Not Found. Scenario 3: Given datos inválidos (distancia negativa) When procesa Then devuelve 400 Bad Request. | Alta | EP12 |
| TS02 | Developer | Exponer endpoint para listar espacios de estacionamiento | Como developer, deseo exponer GET /api/v1/parking-slots para obtener lista de espacios con estado actual. | Scenario 1: Given espacios registrados When procesa Then devuelve 200 OK con lista (id, slotCode, status, lastUpdated). Scenario 2: Given sin registros When procesa Then devuelve 200 OK con lista vacía. | Alta | EP12 |
| TS03 | Developer | Exponer endpoint para consultar espacios disponibles | Como developer, deseo exponer GET /api/v1/parking-slots/available para obtener solo espacios libres. | Scenario 1: Given espacios disponibles When procesa Then devuelve 200 OK con lista filtrada. Scenario 2: Given sin disponibilidad When procesa Then devuelve 200 OK con lista vacía. | Alta | EP12 |
| TS04 | Developer | Exponer endpoint para actualizar estado de espacio | Como developer, deseo exponer PATCH /api/v1/parking-slots/{id}/status para actualizar el estado de un espacio. | Scenario 1: Given status válido (AVAILABLE, OCCUPIED, OUT_OF_SERVICE) When procesa Then actualiza y devuelve 200 OK. Scenario 2: Given espacio inexistente When procesa Then devuelve 404 Not Found. Scenario 3: Given status inválido When procesa Then devuelve 400 Bad Request. | Alta | EP12 |
| TS05 | Developer | Exponer endpoint para obtener detalles de un espacio | Como developer, deseo exponer GET /api/v1/parking-slots/{id} para obtener detalles de un espacio específico. | Scenario 1: Given espacio existente When procesa Then devuelve 200 OK con detalles (slotCode, status, sensorId, lastUpdated). Scenario 2: Given espacio inexistente When procesa Then devuelve 404 Not Found. | Alta | EP12 |
| TS06 | Developer | Exponer endpoint para recomendar espacios | Como developer, deseo exponer GET /api/v1/parking-slots/recommendations para sugerir espacios cercanos disponibles. | Scenario 1: Given recomendaciones disponibles When procesa Then devuelve 200 OK con lista priorizada por proximidad. Scenario 2: Given sin resultados When procesa Then devuelve 200 OK con lista vacía. | Media | EP12 |
| TS07 | Developer | Exponer endpoint para registrar ingreso vehicular | Como developer, deseo exponer POST /api/v1/access/entries para registrar el ingreso de un vehículo al estacionamiento. | Scenario 1: Given registro exitoso con placa reconocida When procesa Then devuelve 201 Created con sessionId y entryTimestamp. Scenario 2: Given placa no registrada en el sistema When procesa Then crea sesión como unidentified y devuelve 201 Created. Scenario 3: Given datos inválidos (imagen vacía) When procesa Then devuelve 400 Bad Request. | Alta | EP12 |
| TS08 | Developer | Exponer endpoint para registrar salida vehicular | Como developer, deseo exponer POST /api/v1/access/exits para registrar la salida de un vehículo del estacionamiento. | Scenario 1: Given salida con pago completado When procesa Then devuelve 200 OK, cierra sesión y libera espacio. Scenario 2: Given pago pendiente When procesa Then devuelve 402 Payment Required con mensaje indicando que debe completar el pago. Scenario 3: Given placa sin sesión activa When procesa Then devuelve 404 Not Found. | Alta | EP12 |
| TS09 | Developer | Exponer endpoint para reconocimiento de placas | Como developer, deseo exponer POST /api/v1/access/alpr para procesar imagen de placa vehicular. | Scenario 1: Given imagen válida con placa detectada When procesa Then devuelve 200 OK con licensePlate y confidence. Scenario 2: Given imagen inválida o ilegible When procesa Then devuelve 400 Bad Request con mensaje de error. Scenario 3: Given placa detectada con confianza < 85% When procesa Then devuelve 200 OK con flag lowConfidence=true. | Alta | EP12 |
| TS10 | Developer | Exponer endpoint para crear sesión de estacionamiento | Como developer, deseo exponer POST /api/v1/parking-sessions para crear una nueva sesión vehicular. | Scenario 1: Given datos válidos (licensePlate, entryTimestamp) When procesa Then crea sesión con status ACTIVE y devuelve 201 Created. Scenario 2: Given sesión activa existente para esa placa When procesa Then devuelve 409 Conflict indicando que ya tiene sesión en curso. Scenario 3: Given datos inválidos (placa vacía) When procesa Then devuelve 400 Bad Request. | Alta | EP12 |
| TS11 | Developer | Exponer endpoint para obtener sesión activa | Como developer, deseo exponer GET /api/v1/parking-sessions/active para consultar la sesión en curso del usuario autenticado. | Scenario 1: Given sesión activa existente When procesa Then devuelve 200 OK con sessionId, licensePlate, entryTimestamp, currentDuration, estimatedFee, slotCode. Scenario 2: Given sin sesión activa When procesa Then devuelve 404 Not Found. | Alta | EP12 |
| TS12 | Developer | Exponer endpoint para consultar sesión por ID | Como developer, deseo exponer GET /api/v1/parking-sessions/{id} para obtener detalles de una sesión específica. | Scenario 1: Given sesión existente When procesa Then devuelve 200 OK con todos los detalles. Scenario 2: Given sesión inexistente When procesa Then devuelve 404 Not Found. | Media | EP12 |
| TS13 | Developer | Exponer endpoint para finalizar sesión | Como developer, deseo exponer PATCH /api/v1/parking-sessions/{id}/end para cerrar una sesión vehicular al momento de la salida. | Scenario 1: Given sesión activa con pago completado When procesa Then cierra sesión, registra exitTimestamp, libera espacio y devuelve 200 OK. Scenario 2: Given sesión activa con pago pendiente When procesa Then devuelve 402 Payment Required. Scenario 3: Given sesión inexistente When procesa Then devuelve 404 Not Found. | Alta | EP12 |
| TS14 | Developer | Exponer endpoint para historial de sesiones | Como developer, deseo exponer GET /api/v1/parking-sessions/history para consultar sesiones pasadas del usuario. | Scenario 1: Given historial disponible When procesa Then devuelve 200 OK con lista ordenada por fecha descendente. Scenario 2: Given sin registros When procesa Then devuelve 200 OK con lista vacía. | Baja | EP12 |
| TS15 | Developer | Exponer endpoint para registrar pago | Como developer, deseo exponer POST /api/v1/payments para procesar un pago asociado a una sesión vehicular a través de Culqi. | Scenario 1: Given datos válidos (sessionId, paymentMethod, amount) y Culqi procesa exitosamente When procesa Then devuelve 201 Created con paymentId, amount, status COMPLETED y receiptUrl. Scenario 2: Given error de pasarela When Culqi falla Then devuelve 402 Payment Required con detalle del error. Scenario 3: Given sesión ya pagada When intenta pagar Then devuelve 409 Conflict. | Alta | EP12 |
| TS16 | Developer | Exponer endpoint para consultar pago | Como developer, deseo exponer GET /api/v1/payments/{id} para obtener detalles de un pago específico. | Scenario 1: Given pago existente When procesa Then devuelve 200 OK con paymentId, amount, method, status, timestamp, receiptUrl. Scenario 2: Given pago inexistente When procesa Then devuelve 404 Not Found. | Media | EP12 |
| TS17 | Developer | Exponer endpoint para historial de pagos | Como developer, deseo exponer GET /api/v1/payments/history para consultar pagos pasados del usuario autenticado. | Scenario 1: Given pagos registrados When procesa Then devuelve 200 OK con lista ordenada por fecha descendente incluyendo amount, method, date, duration. Scenario 2: Given sin pagos When procesa Then devuelve 200 OK con lista vacía. | Baja | EP12 |
| TS18 | Developer | Exponer endpoint para enviar notificación push | Como developer, deseo exponer POST /api/v1/notifications para enviar notificaciones push a usuarios via Firebase Cloud Messaging. | Scenario 1: Given datos válidos (userId, title, body, type) When FCM procesa el envío Then devuelve 200 OK con notificationId y deliveryStatus. Scenario 2: Given userId sin token FCM registrado When intenta enviar Then devuelve 404 Not Found indicando dispositivo no registrado. Scenario 3: Given datos inválidos (title vacío) When procesa Then devuelve 400 Bad Request. | Media | EP12 |
| TS19 | Developer | Exponer endpoint para listar notificaciones de un usuario | Como developer, deseo exponer GET /api/v1/notifications/user/{id} para listar las notificaciones recibidas por un usuario. | Scenario 1: Given notificaciones existentes When procesa Then devuelve 200 OK con lista ordenada por fecha. Scenario 2: Given sin notificaciones When procesa Then devuelve 200 OK con lista vacía. | Baja | EP12 |
| TS20 | Developer | Exponer endpoint para métricas de ocupación | Como developer, deseo exponer GET /api/v1/analytics/occupancy para obtener estadísticas de ocupación del estacionamiento. | Scenario 1: Given datos disponibles y parámetros válidos (startDate, endDate) When procesa Then devuelve 200 OK con occupancyRate, peakHours, turnoverRate y datos por hora. Scenario 2: Given fechas inválidas (startDate posterior a endDate) When procesa Then devuelve 400 Bad Request. Scenario 3: Given sin datos para el rango When procesa Then devuelve 200 OK con valores en cero. | Media | EP12 |
| TS21 | Developer | Exponer endpoint para métricas de ingresos | Como developer, deseo exponer GET /api/v1/analytics/revenue para obtener estadísticas financieras del estacionamiento. | Scenario 1: Given datos disponibles y rango válido When procesa Then devuelve 200 OK con totalRevenue, averageTicket, paymentsByMethod y datos por día. Scenario 2: Given sin datos para el rango When procesa Then devuelve 200 OK con valores en cero. | Media | EP12 |
| TS22 | Developer | Exponer endpoint para generar mapa de calor | Como developer, deseo exponer GET /api/v1/analytics/heatmap para visualizar patrones de ocupación por espacio. | Scenario 1: Given datos de ocupación disponibles When procesa Then devuelve 200 OK con datos de heatmap por slot y hora. Scenario 2: Given sin datos suficientes When procesa Then devuelve 200 OK con mapa vacío. | Baja | EP12 |
| TS23 | Developer | Exponer endpoint para registrar alerta de emergencia | Como developer, deseo exponer POST /api/v1/emergency/alerts para registrar una alerta de emergencia disparada por sensores de gas/humo. | Scenario 1: Given datos válidos (sensorId, gasLevel, type) When procesa Then crea alerta, activa protocolo de emergencia y devuelve 201 Created con emergencyId y activatedAt. Scenario 2: Given datos inválidos (gasLevel negativo) When procesa Then devuelve 400 Bad Request. | Alta | EP12 |
| TS24 | Developer | Exponer endpoint para consultar estado de emergencia | Como developer, deseo exponer GET /api/v1/emergency/status para consultar si hay una emergencia activa en el estacionamiento. | Scenario 1: Given emergencia activa When procesa Then devuelve 200 OK con emergencyId, type, triggeredAt, sensorLocation. Scenario 2: Given sin emergencias activas When procesa Then devuelve 200 OK con status "NORMAL". | Alta | EP12 |
| TS25 | Developer | Exponer endpoint para activar protocolo de evacuación | Como developer, deseo exponer POST /api/v1/emergency/evacuate para activar manualmente el protocolo de evacuación. | Scenario 1: Given emergencia activa When admin autorizado solicita Then activa protocolo (abrir barreras, LEDs evacuación) y devuelve 200 OK. Scenario 2: Given sin emergencia activa When solicita evacuación Then devuelve 409 Conflict indicando que no hay emergencia que justifique evacuación. | Alta | EP12 |
| TS26 | Developer | Exponer endpoint para resolver emergencia | Como developer, deseo exponer PATCH /api/v1/emergencies/{id}/resolve para marcar una emergencia como resuelta y restaurar operación normal. | Scenario 1: Given emergencia activa When admin envía solicitud de resolución Then marca como RESOLVED, restaura operación normal y devuelve 200 OK. Scenario 2: Given emergencia inexistente When procesa Then devuelve 404 Not Found. Scenario 3: Given emergencia ya resuelta When intenta resolver de nuevo Then devuelve 409 Conflict. | Alta | EP12 |
| TS27 | Developer | Exponer endpoint para generar pase digital | Como developer, deseo exponer POST /api/v1/wallet/passes para generar un pase digital de estancia asociado a una sesión vehicular. | Scenario 1: Given sesión activa válida When procesa Then genera pase con placa, hora, QR y devuelve 201 Created con passId y passUrl. Scenario 2: Given sesión inexistente When procesa Then devuelve 404 Not Found. Scenario 3: Given usuario sin plan Premium When solicita Then devuelve 403 Forbidden. | Baja | EP12 |
| TS28 | Developer | Exponer endpoint para obtener pase digital | Como developer, deseo exponer GET /api/v1/wallet/passes/{id} para consultar los detalles de un pase digital existente. | Scenario 1: Given pase existente When procesa Then devuelve 200 OK con passId, licensePlate, entryTime, currentAmount, qrCode, status. Scenario 2: Given pase inexistente When procesa Then devuelve 404 Not Found. | Baja | EP12 |
| TS29 | Developer | Exponer endpoint para generar pase Google Wallet | Como developer, deseo exponer POST /api/v1/wallet/google para crear un pase en Google Wallet del conductor. | Scenario 1: Given datos válidos (sessionId, userId) When Google Wallet API procesa Then genera pase y devuelve 201 Created con saveUrl para añadir a Wallet. Scenario 2: Given datos inválidos When procesa Then devuelve 400 Bad Request. Scenario 3: Given error de Google Wallet API When falla Then devuelve 502 Bad Gateway. | Baja | EP12 |
| TS30 | Developer | Exponer endpoint para registrar usuario | Como developer, deseo exponer POST /api/v1/auth/register para permitir el registro de nuevos usuarios en el sistema. | Scenario 1: Given datos válidos (name, email, password, role, licensePlate) When procesa Then crea cuenta y devuelve 201 Created con userId y role. Scenario 2: Given correo ya registrado When procesa Then devuelve 409 Conflict. Scenario 3: Given datos inválidos (email mal formado, contraseña corta) When procesa Then devuelve 400 Bad Request con errores específicos. | Alta | EP12 |
| TS31 | Developer | Exponer endpoint para autenticación de usuario | Como developer, deseo exponer POST /api/v1/auth/login para autenticar usuarios y devolver un token JWT. | Scenario 1: Given credenciales válidas (email, password) When procesa Then devuelve 200 OK con accessToken JWT, refreshToken y datos básicos del usuario. Scenario 2: Given credenciales inválidas When procesa Then devuelve 401 Unauthorized con mensaje genérico. Scenario 3: Given cuenta no verificada When intenta login Then devuelve 403 Forbidden indicando que debe verificar su cuenta. | Alta | EP12 |
| TS32 | Developer | Exponer endpoint para obtener perfil de usuario | Como developer, deseo exponer GET /api/v1/users/{id} para obtener los datos del perfil de un usuario. | Scenario 1: Given usuario existente When procesa Then devuelve 200 OK con name, email, role, vehicles, plan. Scenario 2: Given usuario inexistente When procesa Then devuelve 404 Not Found. | Media | EP12 |
| TS33 | Developer | Exponer endpoint para actualizar perfil de usuario | Como developer, deseo exponer PUT /api/v1/users/{id} para actualizar los datos del perfil de un usuario. | Scenario 1: Given datos válidos When procesa Then actualiza perfil y devuelve 200 OK con datos actualizados. Scenario 2: Given datos inválidos (email mal formado) When procesa Then devuelve 400 Bad Request. Scenario 3: Given usuario inexistente When procesa Then devuelve 404 Not Found. | Media | EP12 |
| TS34 | Developer | Exponer endpoint para recuperación de contraseña | Como developer, deseo exponer POST /api/v1/auth/forgot-password para enviar enlace de recuperación al correo del usuario. | Scenario 1: Given correo válido registrado When procesa Then envía enlace de recuperación y devuelve 200 OK. Scenario 2: Given correo inexistente When procesa Then devuelve 200 OK con mensaje genérico (por seguridad, no revela si el correo existe). | Media | EP12 |
| TS35 | Developer | Exponer endpoint para restablecer contraseña | Como developer, deseo exponer POST /api/v1/auth/reset-password para permitir cambiar la contraseña mediante un token de recuperación. | Scenario 1: Given token válido y contraseña nueva que cumple requisitos When procesa Then actualiza contraseña y devuelve 200 OK. Scenario 2: Given token inválido o expirado When procesa Then devuelve 400 Bad Request. Scenario 3: Given contraseña que no cumple requisitos (< 8 caracteres) When procesa Then devuelve 400 Bad Request con detalle. | Media | EP12 |
| TS36 | Developer | Exponer endpoint para registrar vehículo | Como developer, deseo exponer POST /api/v1/users/{id}/vehicles para agregar un vehículo a la cuenta de un usuario. | Scenario 1: Given datos válidos (licensePlate, make, model) When procesa Then agrega vehículo y devuelve 201 Created con vehicleId. Scenario 2: Given placa ya registrada en otra cuenta When procesa Then devuelve 409 Conflict. Scenario 3: Given usuario inexistente When procesa Then devuelve 404 Not Found. | Media | EP12 |
| TS37 | Developer | Exponer endpoint para listar vehículos de un usuario | Como developer, deseo exponer GET /api/v1/users/{id}/vehicles para obtener la lista de vehículos registrados por un usuario. | Scenario 1: Given usuario con vehículos registrados When procesa Then devuelve 200 OK con lista (vehicleId, licensePlate, make, model). Scenario 2: Given usuario sin vehículos When procesa Then devuelve 200 OK con lista vacía. Scenario 3: Given usuario inexistente When procesa Then devuelve 404 Not Found. | Media | EP12 |
| TS38 | Developer | Exponer endpoint para eliminar vehículo | Como developer, deseo exponer DELETE /api/v1/users/{userId}/vehicles/{vehicleId} para eliminar un vehículo de la cuenta de un usuario. | Scenario 1: Given vehículo existente asociado al usuario When procesa Then elimina vehículo y devuelve 204 No Content. Scenario 2: Given vehículo inexistente When procesa Then devuelve 404 Not Found. Scenario 3: Given vehículo con sesión activa When intenta eliminar Then devuelve 409 Conflict indicando que debe finalizar la sesión primero. | Media | EP12 |

 
| |  |  | || |  |
|---|---|---|---|---|---|---|
| SWS01 | Visitante | Ver sección Hero | Como visitante del segmento conductor, deseo ver la sección Hero para entender rápidamente el propósito de SpotFinder. | Scenario 1: Given visitante accede a landing When carga Then muestra título, descripción y CTA visible. Scenario 2: Given acceso móvil When carga Then contenido se adapta responsivamente. | Baja | EP11 |
| SWS02 | Visitante | Ver sección Features | Como visitante del segmento conductor, deseo ver funcionalidades principales para evaluar la solución. | Scenario 1: Given visitante navega a Features When visualiza Then encuentra al menos 4 funcionalidades con ícono y descripción. | Baja | EP11 |
| SWS03 | Visitante | Ver sección How It Works | Como visitante del segmento conductor, deseo entender el proceso paso a paso. | Scenario 1: Given visitante navega a How It Works When visualiza Then encuentra pasos numerados del flujo completo. | Baja | EP11 |
| SWS04 | Visitante | Ver sección About The Product | Como visitante del segmento administrador, deseo conocer las capacidades del producto. | Scenario 1: Given visitante navega a About The Product When visualiza Then encuentra descripción del dashboard, sensores y métricas. | Baja | EP11 |
| SWS05 | Visitante | Ver sección Pricing | Como visitante, deseo ver planes y precios para decidir cuál me conviene. | Scenario 1: Given visitante navega a Pricing When visualiza Then encuentra tabla comparativa de planes Free, Pro y Premium. | Baja | EP11 |
| SWS06 | Visitante | Ver sección Testimonials | Como visitante, deseo ver testimonios para generar confianza. | Scenario 1: Given visitante navega a Testimonials When visualiza Then encuentra al menos 2 testimonios con nombre, foto y opinión. | Baja | EP11 |
| SWS07 | Visitante | Ver sección About Us y About The Team | Como visitante, deseo conocer al equipo de ParkSense IoT. | Scenario 1: Given visitante navega a About Us When visualiza Then encuentra misión, visión y equipo con fotos y roles. | Baja | EP11 |
| SWS08 | Visitante | Ver sección FAQ | Como visitante, deseo encontrar respuestas a preguntas frecuentes. | Scenario 1: Given visitante navega a FAQ When visualiza Then encuentra al menos 5 preguntas con respuestas expandibles. | Baja | EP11 |
| SWS09 | Visitante | Ver sección Contact | Como visitante, deseo contactar al equipo de SpotFinder. | Scenario 1: Given visitante navega a Contact When visualiza Then encuentra formulario con nombre, email y mensaje. | Baja | EP11 |
| SWS10 | Visitante | Ver sección Footer | Como visitante, deseo acceder a enlaces legales y redes sociales. | Scenario 1: Given visitante visualiza footer When revisa Then encuentra enlaces a términos, privacidad y redes sociales. | Baja | EP11 |
| SWS11 | Visitante | Navegación responsive | Como visitante, deseo navegar fluidamente en desktop y móvil. | Scenario 1: Given visitante en desktop When selecciona sección Then scroll suave. Scenario 2: Given visitante en móvil When abre menú hamburguesa y selecciona Then navega y menú se cierra. | Baja | EP11 |
 

 
|  |  |  | |  | |  |
|---|---|---|---|---|---|---|
| SS01 | Equipo de Desarrollo | Investigación de integración de Culqi para pagos | Como equipo de desarrollo, deseo investigar la integración de Culqi para comprender cómo implementar pagos con tarjeta y Yape en SpotFinder. | Tarea 1: Revisar documentación Culqi API. Tarea 2: Analizar compatibilidad con Spring Boot. Tarea 3: Evaluar costos (3.44% + IGV). Tarea 4: PoC con pago de prueba en sandbox. | Media | EP13 |
| SS02 | Equipo de Desarrollo | Investigación de Plate Recognizer API para ALPR | Como equipo de desarrollo, deseo investigar Plate Recognizer para evaluar la precisión del reconocimiento de placas peruanas con ESP32-CAM. | Tarea 1: Revisar documentación y SDK. Tarea 2: Probar con fotos de placas peruanas. Tarea 3: Evaluar tier gratuito (2,500/mes). Tarea 4: PoC con ESP32-CAM. | Media | EP13 |
| SS03 | Equipo de Desarrollo | Investigación de Firebase Cloud Messaging | Como equipo de desarrollo, deseo investigar FCM para implementar notificaciones push en Flutter. | Tarea 1: Revisar docs FCM para Flutter. Tarea 2: Configurar Firebase Console. Tarea 3: PoC envío desde Spring Boot a Flutter. | Media | EP13 |
| SS04 | Equipo de Desarrollo | Investigación de Google Wallet API | Como equipo de desarrollo, deseo investigar Google Wallet API para implementar pase digital de estancia. | Tarea 1: Revisar docs Generic Passes. Tarea 2: Evaluar requisitos (cuenta gratuita). Tarea 3: PoC con pase de prueba. | Media | EP13 |
| SS05 | Equipo de Desarrollo | Prueba de bibliotecas MQTT para ESP32 | Como equipo de desarrollo, deseo probar bibliotecas MQTT para seleccionar la más adecuada para comunicación sensores-edge. | Tarea 1: Comparar PubSubClient vs AsyncMQTTClient. Tarea 2: Probar ESP32→Mosquitto. Tarea 3: Medir latencia. | Media | EP13 |
| SS06 | Equipo de Desarrollo | Prueba de bibliotecas para generación de PDF | Como equipo de desarrollo, deseo probar bibliotecas de PDF para reportes administrativos. | Tarea 1: Investigar iText, JasperReports, PDFBox. Tarea 2: Generar PDF de prueba. Tarea 3: Evaluar licencias. | Media | EP13 |
 
> **Nota:** Para el detalle completo de cada Spike Story (contexto, criterios de aceptación Given-When-Then y Definition of Done), véase el **Anexo F: Detalle de Spike Stories**.
 
---
## 3.2. Impact Mapping.

## 3.3. Product Backlog.

| # Orden | Story ID | Título | Story Points |
|---|---|---|---|
| 1 | US01 | Detección de ocupación por sensores | 8 |
| 2 | US02 | Visualización de espacios en tiempo real | 8 |
| 3 | TS01 | Exponer endpoint para registrar lectura de sensor | 5 |
| 4 | TS02 | Exponer endpoint para listar espacios | 3 |
| 5 | TS03 | Exponer endpoint para consultar espacios disponibles | 3 |
| 6 | TS04 | Exponer endpoint para actualizar estado de espacio | 3 |
| 7 | TS05 | Exponer endpoint para obtener detalles de un espacio | 2 |
| 8 | US03 | Ingreso automático con ALPR | 8 |
| 9 | US04 | Salida automática con verificación de pago | 8 |
| 10 | TS07 | Exponer endpoint para registrar ingreso vehicular | 5 |
| 11 | TS08 | Exponer endpoint para registrar salida vehicular | 5 |
| 12 | TS09 | Exponer endpoint para reconocimiento de placas | 5 |
| 13 | TS10 | Exponer endpoint para crear sesión de estacionamiento | 5 |
| 14 | TS11 | Exponer endpoint para obtener sesión activa | 3 |
| 15 | TS12 | Exponer endpoint para consultar sesión por ID | 2 |
| 16 | TS13 | Exponer endpoint para finalizar sesión | 5 |
| 17 | US05 | Pago digital del estacionamiento | 8 |
| 18 | TS15 | Exponer endpoint para registrar pago | 5 |
| 19 | TS16 | Exponer endpoint para consultar pago | 2 |
| 20 | US06 | Dashboard de monitoreo en tiempo real | 8 |
| 21 | US07 | Find My Car | 5 |
| 22 | US08 | Visualización de tiempo y costo estimado | 3 |
| 23 | US09 | Espacios recomendados | 5 |
| 24 | TS06 | Exponer endpoint para recomendar espacios | 3 |
| 25 | US10 | Notificaciones de eventos del vehículo | 5 |
| 26 | TS18 | Exponer endpoint para enviar notificación push | 3 |
| 27 | TS19 | Exponer endpoint para listar notificaciones | 2 |
| 28 | US11 | Gestión de disponibilidad de espacios | 3 |
| 29 | US12 | Estadísticas de ocupación | 5 |
| 30 | US13 | Generación de reportes | 5 |
| 31 | TS20 | Exponer endpoint para métricas de ocupación | 5 |
| 32 | TS21 | Exponer endpoint para métricas de ingresos | 3 |
| 33 | TS22 | Exponer endpoint para generar mapa de calor | 3 |
| 34 | US14 | Detección y alerta de emergencia | 8 |
| 35 | TS23 | Exponer endpoint para registrar alerta de emergencia | 5 |
| 36 | TS24 | Exponer endpoint para consultar estado de emergencia | 2 |
| 37 | TS25 | Exponer endpoint para activar evacuación | 3 |
| 38 | TS26 | Exponer endpoint para resolver emergencia | 3 |
| 39 | US15 | Historial de pagos | 3 |
| 40 | TS17 | Exponer endpoint para historial de pagos | 2 |
| 41 | TS14 | Exponer endpoint para historial de sesiones | 2 |
| 42 | US16 | Generación de pase digital (Google Wallet) | 8 |
| 43 | TS27 | Exponer endpoint para generar pase digital | 5 |
| 44 | TS28 | Exponer endpoint para obtener pase digital | 2 |
| 45 | TS29 | Exponer endpoint para generar pase Google Wallet | 5 |
| 46 | US17 | Solicitud de servicio de lavado | 5 |
| 47 | US18 | Registro de usuario conductor | 5 |
| 48 | US19 | Registro de usuario administrador | 5 |
| 49 | US20 | Inicio de sesión | 3 |
| 50 | TS30 | Exponer endpoint para registrar usuario | 3 |
| 51 | TS31 | Exponer endpoint para autenticación | 3 |
| 52 | US21 | Recuperación de contraseña | 3 |
| 53 | US22 | Edición de perfil | 3 |
| 54 | US23 | Registro de vehículo adicional | 3 |
| 55 | TS32 | Exponer endpoint para obtener perfil | 2 |
| 56 | TS33 | Exponer endpoint para actualizar perfil | 3 |
| 57 | TS34 | Exponer endpoint para recuperación de contraseña | 3 |
| 58 | TS35 | Exponer endpoint para restablecer contraseña | 3 |
| 59 | TS36 | Exponer endpoint para registrar vehículo | 3 |
| 60 | TS37 | Exponer endpoint para listar vehículos | 2 |
| 61 | TS38 | Exponer endpoint para eliminar vehículo | 2 |
| 62 | SWS01 | Ver sección Hero | 2 |
| 63 | SWS02 | Ver sección Features | 2 |
| 64 | SWS03 | Ver sección How It Works | 2 |
| 65 | SWS04 | Ver sección About The Product | 3 |
| 66 | SWS05 | Ver sección Pricing | 3 |
| 67 | SWS06 | Ver sección Testimonials | 2 |
| 68 | SWS07 | Ver sección About Us y About The Team | 2 |
| 69 | SWS08 | Ver sección FAQ | 2 |
| 70 | SWS09 | Ver sección Contact | 2 |
| 71 | SWS10 | Ver sección Footer | 2 |
| 72 | SWS11 | Navegación responsive | 3 |
| 73 | SS01 | Investigación de integración de Culqi | 8 |
| 74 | SS02 | Investigación de Plate Recognizer API | 8 |
| 75 | SS03 | Investigación de Firebase Cloud Messaging | 5 |
| 76 | SS04 | Investigación de Google Wallet API | 8 |
| 77 | SS05 | Prueba de bibliotecas MQTT para ESP32 | 5 |
| 78 | SS06 | Prueba de bibliotecas para generación de PDF | 5 |
---

# Capítulo IV: Solution Software Design

## 4.1. Strategic-Level Domain-Driven Design.

### 4.1.1. Design-Level EventStorming.

#### 4.1.1.1 Candidate Context Discovery.

#### 4.1.1.2 Domain Message Flows Modeling.

#### 4.1.1.3 Bounded Context Canvases.

### 4.1.2. Context Mapping.

### 4.1.3. Software Architecture.
#### 4.1.3.1. Software Architecture System Landscape Diagram.

#### 4.1.3.2. Software Architecture Context Level Diagrams.

#### 4.1.3.3. Software Architecture Container Level Diagrams.

#### 4.1.3.4. Software Architecture Deployment Diagrams.

## 4.2. Tactical-Level Domain-Driven Design

### 4.2.X. Bounded Context: <Bounded Context Name>

#### 4.2.X.1. Domain Layer.

#### 4.2.X.2. Interface Layer.

#### 4.2.X.3. Application Layer.

#### 4.2.X.4. Infrastructure Layer.

#### 4.2.X.5. Bounded Context Software Architecture Component Level Diagrams.

#### 4.2.X.6. Bounded Context Software Architecture Code Level Diagrams.

##### 4.2.X.6.1. Bounded Context Domain Layer Class Diagrams.

##### 4.2.X.6.2. Bounded Context Database Design Diagram.

---

# Conclusiones
## Conclusiones y recomendaciones.
## Video About-the-Team.

---

# Bibliografía

---

# Anexos
