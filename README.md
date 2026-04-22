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
[Contenido]

### 1.1.2. Perfiles de integrantes del equipo
[Contenido]

## 1.2. Solution Profile
### 1.2.1 Antecedentes y problemática
[Contenido]

### 1.2.2 Lean UX Process.
#### 1.2.2.1. Lean UX Problem Statements.
[Contenido]
#### 1.2.2.2. Lean UX Assumptions.
[Contenido]
#### 1.2.2.3. Lean UX Hypothesis Statements.
[Contenido]
#### 1.2.2.4. Lean UX Canvas.
[Contenido]

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

# Capítulo IV: Solution Software Design

## 4.1. Strategic-Level Domain-Driven Design.

### 4.1.1. Design-Level EventStorming.

#### 4.1.1.1 Candidate Context Discovery.

### Preparación de la sesión
La sesión de Candidate Context Discovery debe realizarse inmediatamente después del Event Storming, con duración aproximada de 1.5-2 horas. Insumos necesarios: la línea de tiempo de eventos del Event Storming, los aggregates identificados (paso 9), los pivotal events (paso 4), y los bounded contexts preliminares (paso 10).

**Paso 1 — Identificación de valor estratégico:**
Cada miembro del equipo responde en post-its naranjas a la pregunta: **"¿Qué parte del sistema genera directamente valor para los usuarios y diferencia a SpotFinder de otras soluciones?"**

<img src="assets/diagrams/context-candidate/candidate-context-step1.png" alt="Paso1" width="800
">


**Paso 2 — Agrupación de eventos en torno al valor:**
Revisar los aggregates del Event Storming y sus eventos asociados. Agrupar por afinidad y preguntar: "¿Este grupo de eventos genera valor directo al negocio o es un soporte necesario?"

<img src="assets/diagrams/context-candidate/candidate-context-step2.png" alt="Paso2" width="800
">

**Paso 3 — Clasificación Core, Supporting, Generic:**
Ubicar cada bounded context en la matriz de dos ejes (Business Differentiation vs Model Complexity).

<img src="assets/diagrams/context-candidate/candidate-context-step3.jpg" alt="Paso3" width="800
">

### Candidate Contexts identificados para SpotFinder
 
| Candidate Context | Eventos Clave Asociados | Clasificación | Descripción | Justificación |
|---|---|---|---|---|
| **Parking Monitoring** | Vehicle Presence Detected, Slot Status Changed to Occupied/Available, Sensor Reading Published, Availability Map Updated | **Core** | Detección de ocupación por sensores IoT, actualización de LEDs y mapa de disponibilidad en tiempo real. | Es el corazón tecnológico de SpotFinder. Sin sensores detectando espacios, el sistema no existe. Es lo que diferencia a SpotFinder de Apparka y Quadra. La complejidad del modelo es alta (comunicación MQTT, debounce, real-time updates). |
| **Access Control** | License Plate Captured, Plate Recognized, Entry Barrier Opened, Vehicle Session Started, Exit Barrier Opened, Vehicle Session Ended | **Core** | Gestión del ingreso y salida vehicular mediante ALPR (reconocimiento de placas) y control de barreras. | El ALPR es el segundo diferenciador clave: elimina los tickets físicos. La sesión vehicular que inicia/termina aquí conecta todo el sistema. Alta complejidad por integración con Plate Recognizer API y control de hardware (servomotor barrera). |
| **Payment Processing** | Payment Initiated, Fee Calculated, Payment Succeeded/Failed, Payment Receipt Generated | **Core** | Cálculo de tarifas y procesamiento de pagos digitales vía Culqi (Yape + tarjeta). | El pago digital sin cola es el tercer pilar del valor de negocio. Integración con pasarela externa (Culqi) agrega complejidad. Directamente vinculado a los ingresos del estacionamiento. |
| **Analytics & Reporting** | Occupancy Report Generated, Revenue Report Generated, Peak Hours Analyzed, Turnover Rate Calculated, Heatmap Generated | **Supporting** | Generación de métricas, estadísticas y reportes para la toma de decisiones administrativas. | Aporta valor al administrador pero no es el diferenciador principal frente a competidores. Complejidad media: agregación de datos, cálculos estadísticos. Podría externalizarse con herramientas BI estándar. |
| **Emergency & Safety** | Gas Level Exceeded, Emergency Alert Triggered, Protocol Activated, Barriers Opened, Emergency Resolved | **Supporting** | Detección de gas/humo mediante sensores MQ-2 y activación automática de protocolos de evacuación. | Funcionalidad diferenciadora (ningún competidor la ofrece) pero no es el core del negocio de estacionamiento. Complejidad baja-media: regla simple de umbral + acciones automáticas. |
| **Reservation Management** | Reservation Requested, Confirmed, Grace Period Started/Expired, Cancelled | **Supporting** | Reservas de espacios con grace period y cancelación automática. Disponible solo en planes Pro/Premium. | Agrega valor para usuarios premium pero el sistema funciona sin ella. Complejidad media: manejo de estados temporales y concurrencia. |
| **Identity & Access Management** | Account Created, Vehicle Registered, Logged In, Profile Updated, Password Reset | **Generic** | Registro de usuarios, autenticación JWT, gestión de perfiles y vehículos. | Necesario para operar pero no diferencia a SpotFinder. Existen soluciones estándar (Spring Security, Auth0, Firebase Auth). Baja complejidad relativa. |
| **Notification Management** | Notification Sent, Push Delivered | **Supporting** | Gestiona el envío de notificaciones push (FCM), email y alertas in-app a conductores y administradores. Administra templates de mensajes, preferencias de usuario y registro de notificaciones enviadas. | Aunque las notificaciones son transversales, tienen su propio ciclo de vida, templates específicos por tipo de evento, y preferencias de usuario que requieren persistencia propia. Es más que un simple servicio compartido porque necesita gestionar estado (leída/no leída) y reglas (no enviar si usuario desactivó ese tipo). |

### Clasificación estratégica en la matriz

> - **Eje X:** Business Differentiation (Low → High)
> - **Eje Y:** Model Complexity (Low → High)


<img src="assets/diagrams/context-candidate/candidate-context-discovery.png" alt="Paso3" width="800
">


### Resultados
 
Se definieron **8 candidate bounded contexts**, de los cuales:
- **3 Core:** Parking Monitoring, Access Control, Payment Processing
- **4 Supporting:** Analytics & Reporting, Emergency & Safety, Reservation Management, Notification Management
- **1 Generic:** Identity & Access Management

La aplicación de la técnica Start-with-Value permitió asegurar que la atención principal del diseño táctico se concentre en **Parking Monitoring, Access Control y Payment Processing**, dado que allí reside la propuesta de valor diferenciadora de SpotFinder frente a competidores como Apparka, ParkHelp y Quadra.


<img src="assets/diagrams/context-candidate/candidate-context-step2.png" alt="Paso2" width="800
">


#### 4.1.1.2 Domain Message Flows Modeling

###  **Descripción**

En esta sección se modelan los flujos de mensajes entre los distintos Bounded Contexts del sistema SpotFinder, mostrando cómo colaboran para resolver los principales escenarios del negocio.

A diferencia del Event Storming, que es exploratorio, el Domain Message Flow Modeling define de manera precisa los mensajes que se intercambian entre contextos, incluyendo comandos, eventos y queries, así como los datos transmitidos en cada interacción.

Para la representación visual se utilizó la técnica de Domain Storytelling, la cual permite describir de forma clara y colaborativa la interacción entre actores, sistemas externos y bounded contexts mediante una notación estándar.


###  **Escenarios de Integración**

####  **Escenario 1: Vehículo registrado ingresa al estacionamiento**

<img src="assets/diagrams/context-flow/escenario1-ingreso.png" alt="Ingreso de vehículo registrado" width="800
">
<br>

**Flujo de Integración:**
- El Conductor llega a la barrera de entrada, donde la cámara IoT captura la imagen de la placa.
- El dispositivo ESP32-CAM envía la imagen al Access Control BC.
- El sistema externo responde con la placa detectada (Plate Recognized).
- El Access Control BC consulta al IAM BC para verificar si el vehículo está registrado.
- El IAM BC confirma la existencia del vehículo (Vehicle Found).
- El Access Control BC envía el comando para abrir la barrera de entrada (Open Entry Barrier).
- Se genera el evento Vehicle Session Started al crear la sesión de estacionamiento.
- El Access Control BC envía una notificación al Notification Management BC:
    - Send Entry Notification {userId, type: ENTRY_CONFIRMED, data}
    
    Luego:
    - Se validan las preferencias del usuario
    - Se construye el mensaje mediante templates
    - Se envía vía Firebase Cloud Messaging
    - Se almacena la notificación (Notification Stored)


**Bounded Contexts Involucrados:**
- Access Control → IAM → Notification Management → Sistema externo: Plate Recognizer API

---

####  **Escenario 2: Sensor detecta vehículo y actualiza disponibilidad**

<img src="assets/diagrams/context-flow/escenario2-sensor.png" alt="Detección de ocupación de espacio" width="800
">
<br>

**Flujo de Integración:**
- El sensor ultrasónico ESP32 detecta un objeto y publica la lectura en el MQTT Broker.
- El MQTT Broker reenvía la información al Edge Server.
- El Edge Server aplica una regla de validación (debounce), confirmando la presencia del vehículo (Vehicle Presence Confirmed).
- Se registra la lectura en el Parking Monitoring BC.
- El Parking Monitoring BC actualiza el estado del espacio a ocupado (Parking Slot Status Changed).
- Se envía el comando para cambiar el LED a rojo.
- Se transmite la actualización en tiempo real mediante WebSocket hacia el dashboard y la app móvil.


**Bounded Contexts Involucrados:**
- Parking Monitoring → Edge Processing (Edge Server) → Infraestructura IoT (MQTT, sensores)

---

####  **Escenario 3: Conductor paga y sale del estacionamiento**

<img src="assets/diagrams/context-flow/escenario3-pago-salida.png" alt="Pago y salida del estacionamiento" width="800
">
<br>

**Flujo de Integración:**
- El Conductor inicia el pago desde la aplicación móvil.
- La App Móvil solicita el cálculo de la tarifa al Payment Processing BC.
- El sistema devuelve el monto calculado (Fee Calculated).
- El conductor confirma el pago.
- La app envía el comando Process Payment.
- El Payment Processing BC realiza el cobro mediante Culqi API.
- Se recibe el evento Payment Succeeded.
- El estado de la sesión se actualiza como pagado en el Access Control BC.
- El conductor llega a la salida y la cámara captura la placa.
- El Access Control BC verifica el estado del pago.
- Al confirmarse el pago, se abre la barrera (Exit Barrier Opened).
- Se finaliza la sesión (Vehicle Session Ended).
- Se libera el espacio en el Parking Monitoring BC (Parking Slot Released).


**Bounded Contexts Involucrados:**
- Payment Processing → Access Control → Parking Monitoring → Sistema externo: Culqi API

---

####  **Escenario 4: Emergencia detectada por sensor de gas**

<img src="assets/diagrams/context-flow/escenario4-emergencia.png" alt="Alerta de emergencia por gas" width="800
">
<br>

**Flujo de Integración:**
- El sensor MQ-2 detecta niveles peligrosos de gas y publica la lectura en el MQTT Broker.
- El Edge Server evalúa el umbral crítico (Gas Level Exceeded Threshold).
- Se registra una alerta en el Emergency & Safety BC (Emergency Alert Triggered).
- Se activa el protocolo de emergencia (Emergency Protocol Activated).
- Se ordena la apertura de todas las barreras mediante el Access Control BC.
- Se configuran todos los LEDs en modo evacuación mediante el Parking Monitoring BC.
- El Emergency & Safety BC envía una alerta masiva al Notification Management BC:
    - Broadcast Emergency {type, data, recipients}
    
    Luego:

    - Se obtiene la lista de usuarios activos desde Access Control BC
    - Se envían notificaciones masivas vía Firebase Cloud Messaging
    - Se genera el evento Emergency Notifications Sent

- Se actualiza el dashboard en el Analytics & Reporting BC mostrando la alerta.


**Bounded Contexts Involucrados:**
- Emergency & Safety → Access Control → Parking Monitoring → Notification Management → Analytics & Reporting


#### 4.1.1.3 Bounded Context Canvases.

## 4.1.2. Context Mapping

En esta sección se define el context mapping del sistema SpotFinder, con el propósito de representar las relaciones existentes entre los bounded contexts identificados a partir del Event Storming. Este análisis permite comprender cómo interactúan los distintos dominios del sistema y qué patrones de integración son más adecuados para mantener la independencia y coherencia del modelo.

A partir de la identificación de los contextos —Parking Monitoring, Access Control, Reservation Management, Payment Processing, Emergency & Safety, Identity & Access Management y Notifications— se establecieron relaciones utilizando patrones de Domain-Driven Design como Customer/Supplier, Shared Kernel, Conformist, Open Host Service (OHS) y Anti-Corruption Layer (ACL).

---

### Identificación de relaciones y patrones

**Identity & Access Management → Access Control**  
**Patrón: Open Host Service (OHS)**  
**Relación: IAM (U) → Access Control (D)**  
**Tipo de integración: OHS**  
El contexto de Identity & Access Management centraliza la autenticación y gestión de usuarios. Access Control consume estos servicios para validar identidad y permisos en los accesos físicos, utilizando interfaces definidas sin depender del modelo interno.

---

**Identity & Access Management → Reservation Management**  
**Patrón: Open Host Service (OHS)**  
**Relación: IAM (U) → Reservation Management (D)**  
**Tipo de integración: OHS**  
Reservation Management requiere validar usuarios antes de permitir la creación y gestión de reservas. IAM provee estos servicios mediante interfaces desacopladas.

---

**Identity & Access Management → Payment Processing**  
**Patrón: Open Host Service (OHS)**  
**Relación: IAM (U) → Payment Processing (D)**  
**Tipo de integración: OHS**  
Payment Processing utiliza IAM para autenticar usuarios antes de ejecutar transacciones, evitando dependencias directas con el modelo de identidad.

---

**Identity & Access Management → Notifications**  
**Patrón: Open Host Service (OHS)**  
**Relación: IAM (U) → Notifications (D)**  
**Tipo de integración: OHS**  
Notifications obtiene información básica del usuario (identidad/contacto) desde IAM para poder enviar mensajes correctamente.

---

**Access Control → Parking Monitoring**  
**Patrón: Customer/Supplier**  
**Relación: Access Control (U) → Parking Monitoring (D)**  
**Tipo de integración: Directo (eventos)**  
Access Control genera eventos como detección de entrada, lectura de placas o apertura de barreras. Parking Monitoring consume estos eventos para actualizar el estado del estacionamiento.

---

**Parking Monitoring ↔ Reservation Management**  
**Patrón: Shared Kernel**  
**Tipo de integración: Modelo compartido**  
Ambos contextos comparten el concepto de espacio de estacionamiento y disponibilidad, garantizando consistencia en la asignación y reserva de espacios.

---

**Reservation Management → Payment Processing**  
**Patrón: Customer/Supplier + Anti-Corruption Layer (ACL)**  
**Relación: Reservation Management (U) → Payment Processing (D)**  
**Tipo de integración: ACL**  
Reservation Management genera información de sesiones y reservas que es transformada mediante una ACL antes de ser utilizada por Payment Processing, evitando acoplamiento con el dominio financiero.

---

**Parking Monitoring → Payment Processing**  
**Patrón: Conformist**  
**Relación: Parking Monitoring (U) → Payment Processing (D)**  
**Tipo de integración: Directo (Conformist)**  
Payment Processing consume directamente información de ocupación y duración de sesiones, adaptándose al modelo de Parking Monitoring.

---

**Parking Monitoring → Emergency & Safety**  
**Patrón: Anti-Corruption Layer (ACL)**  
**Relación: Parking Monitoring (U) → Emergency & Safety (D)**  
**Tipo de integración: ACL**  
Los datos provenientes de sensores son transformados mediante una ACL para ser interpretados como eventos de seguridad, evitando dependencia del modelo técnico IoT.

---

**Parking Monitoring → Notifications**  
**Patrón: Customer/Supplier**  
**Relación: Parking Monitoring (U) → Notifications (D)**  
**Tipo de integración: Directo (eventos)**  
Eventos como cambios en la ocupación son enviados al sistema de notificaciones.

---

**Reservation Management → Notifications**  
**Patrón: Customer/Supplier**  
**Relación: Reservation Management (U) → Notifications (D)**  
**Tipo de integración: Directo (eventos)**  
Eventos de reservas (confirmaciones, cancelaciones, expiraciones) son comunicados al usuario.

---

**Payment Processing → Notifications**  
**Patrón: Customer/Supplier**  
**Relación: Payment Processing (U) → Notifications (D)**  
**Tipo de integración: Directo (eventos)**  
El estado de las transacciones es enviado al sistema de notificaciones.

---

**Emergency & Safety → Notifications**  
**Patrón: Customer/Supplier**  
**Relación: Emergency & Safety (U) → Notifications (D)**  
**Tipo de integración: Directo (eventos)**  
Las alertas críticas son enviadas al usuario o administrador mediante el sistema de notificaciones.

---

### Análisis de decisiones

Durante el diseño del context mapping se evaluaron distintas alternativas sobre cómo integrar los contextos y qué nivel de acoplamiento permitir entre ellos.

Se decidió mantener Identity & Access Management como un Open Host Service, permitiendo centralizar la autenticación sin generar dependencias directas entre contextos.

Asimismo, se priorizó el uso de Customer/Supplier y Anti-Corruption Layer en la mayoría de relaciones, asegurando independencia entre dominios.

En el caso de Parking Monitoring y Reservation Management, se utilizó Shared Kernel debido a la necesidad de consistencia en el manejo de espacios.

El contexto de Notifications se definió como un consumidor de eventos, centralizando la comunicación con el usuario sin afectar la lógica de otros contextos.

---

### Decisión final

El equipo adoptó una arquitectura basada en bounded contexts independientes conectados mediante patrones de integración bien definidos.

![Context Mapping](/SpotFinder-Report/assets/diagrams/ddd/context-mapping.png)

Enlace al Miro: https://miro.com/app/board/uXjVGhyZyRg=/ 

Esta decisión permite:

- Reducir el acoplamiento entre dominios  
- Facilitar la escalabilidad del sistema  
- Permitir la evolución independiente de cada contexto  
- Integrar nuevos servicios de manera sencilla  

El uso de un contexto de notificaciones mejora la experiencia del usuario al centralizar la comunicación.

En conjunto, esta arquitectura proporciona una base sólida, flexible y alineada con Domain-Driven Design.


### 4.1.3. Software Architecture.

A continuación, se presentan los diagramas del modelo C4 que describen la arquitectura del sistema SpotFinder, el cual integra aplicaciones web, móviles y componentes IoT para la gestión inteligente de estacionamientos.

#### 4.1.3.1. Software Architecture System Landscape Diagram.
El diagrama de System Landscape muestra una visión general del ecosistema de SpotFinder, identificando los principales actores y sistemas externos con los que interactúa.

En este contexto, el sistema tiene como usuarios principales al Driver (conductor) y al Parking Administrator (administrador de estacionamientos). Ambos interactúan directamente con la plataforma para consultar disponibilidad, gestionar espacios y monitorear el estado del estacionamiento.

Además, SpotFinder se integra con múltiples sistemas externos que complementan su funcionalidad. Entre ellos se encuentra un Payment Gateway (Yape/Culqi) para el procesamiento de pagos digitales, un servicio de Plate Recognition API para el reconocimiento automático de placas vehiculares, un Notification Service encargado del envío de notificaciones push, y los Mall Systems, que representan los sistemas internos del centro comercial con los que se comparten datos operativos.

Este diagrama permite entender el sistema como parte de un entorno más amplio, donde diferentes servicios externos enriquecen las capacidades de la plataforma.

<img src="/assets/diagrams/c4/System-Landscape.png" width="800
">
<br>

#### 4.1.3.2. Software Architecture Context Level Diagrams.

El Context Level Diagram presenta cómo el sistema SpotFinder interactúa con sus usuarios y sistemas externos a alto nivel.

Se identifican dos tipos de usuarios principales:

- Driver (Conductor): utiliza el sistema para consultar la disponibilidad de estacionamientos, realizar pagos digitales y recibir notificaciones.
- Parking Administrator (Administrador): se encarga de monitorear la ocupación, gestionar los espacios y supervisar el funcionamiento del sistema.

El sistema central SpotFinder actúa como núcleo de interacción, conectándose con servicios externos clave. Se comunica con el Payment Gateway para procesar pagos, con la Plate Recognition API para el reconocimiento de placas mediante imágenes, y con el Notification Service para el envío de notificaciones a los usuarios. Asimismo, intercambia información con los Mall Systems para mantener actualizados los datos operativos del estacionamiento.

En conjunto, este diagrama permite visualizar claramente los límites del sistema y sus dependencias externas.

<img src="/assets/diagrams/c4/Context-Diagram.png" width="800
">
<br>


#### 4.1.3.3. Software Architecture Container Level Diagrams.

El diagrama de Contenedores describe la estructura interna del sistema SpotFinder, mostrando cómo se organizan sus principales componentes y cómo interactúan entre sí.

El sistema está compuesto por los siguientes contenedores:

- Mobile App (Flutter): aplicación móvil utilizada por los conductores para buscar estacionamiento, consultar disponibilidad y realizar pagos.
- Web Dashboard (Angular): aplicación web orientada a administradores, que permite gestionar el estacionamiento y monitorear métricas en tiempo real.
- Backend API (Spring Boot): componente central que expone servicios REST y contiene la lógica de negocio del sistema. Actúa como intermediario entre las aplicaciones cliente, los servicios externos y la base de datos.
- Database (PostgreSQL): almacena la información del sistema, incluyendo usuarios, vehículos, pagos y datos de ocupación.
- IoT Gateway / Edge Server (Flask + MQTT): componente encargado de recibir datos desde sensores IoT (por ejemplo, ocupación de espacios) y enviarlos al backend para su procesamiento.

El Backend API también se encarga de integrarse con servicios externos como el sistema de pagos, el reconocimiento de placas y las notificaciones.

<img src="/assets/diagrams/c4/Container-Diagram.png" width="800
">
<br>

#### 4.1.3.4. Software Architecture Deployment Diagrams.

El diagrama de Deployment muestra cómo los distintos componentes del sistema SpotFinder se despliegan en la infraestructura física o en la nube.

Los principales nodos de despliegue son:

- User Device (iOS/Android): donde se ejecuta la aplicación móvil utilizada por los conductores.
- Admin Workstation (Browser): dispositivo desde el cual los administradores acceden al sistema mediante un navegador web.
- Frontend Hosting (CDN): infraestructura encargada de servir la aplicación web (Angular SPA) a los usuarios.
- API Hosting Platform (Spring Boot Runtime): entorno donde se despliega el Backend API, encargado de procesar las solicitudes del sistema.
- Database Infrastructure (Managed PostgreSQL Service): servicio gestionado donde se aloja la base de datos del sistema.
- IoT Processing Layer (Edge Gateway Node): nodo donde se ejecuta el servicio IoT (Flask + MQTT), encargado de procesar datos provenientes de sensores en tiempo real.

Las comunicaciones entre componentes se realizan mediante protocolos como HTTPS para las aplicaciones cliente, MQTT para la comunicación con dispositivos IoT y SQL para el acceso a la base de datos.

Este diagrama evidencia una arquitectura distribuida en múltiples capas, combinando dispositivos de usuario, infraestructura en la nube y procesamiento en el borde (edge computing), lo que permite escalabilidad y eficiencia en el manejo de datos en tiempo real.

<img src="/assets/diagrams/c4/Deployment-Diagrams.png" width="800
">
<br>

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
