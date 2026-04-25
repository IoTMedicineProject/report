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

<img src="/assets/diagrams/ddd/context-mapping.png" width="800">


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

# 4.2. Tactical-Level Domain-Driven Design
 
---
 
## 4.2.1. Bounded Context: Parking Monitoring
 
Este bounded context gestiona la detección de ocupación de espacios mediante sensores ultrasónicos IoT, controla el estado de los LEDs indicadores y mantiene el mapa de disponibilidad en tiempo real. Es el contexto core que conecta el mundo físico (sensores ESP32) con el mundo digital (app móvil y dashboard).
 
### 4.2.1.1. Domain Layer
 
En esta sección se describen los elementos del Domain Layer del contexto de Parking Monitoring, que encapsulan la lógica central relacionada con la detección de ocupación y gestión de disponibilidad de espacios.
 
#### 1. ParkingSlot (Aggregate Root)
 
Representa un espacio individual de estacionamiento monitoreado por un sensor ultrasónico.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único del espacio. |
| slotCode | SlotCode | private | Código identificador del espacio (e.g., "A-15", "B-03"). |
| status | SlotStatus | private | Estado actual del espacio (AVAILABLE, OCCUPIED, OUT_OF_SERVICE). |
| sensorId | SensorId | private | Identificador del sensor ultrasónico asignado al espacio. |
| facilityId | FacilityId | private | Identificador del estacionamiento al que pertenece. |
| lastUpdated | LocalDateTime | private | Timestamp de la última actualización de estado. |
 
**Métodos principales:**
 
| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| ParkingSlot() | Constructor | protected | Constructor protegido para JPA. |
| ParkingSlot(RegisterParkingSlotCommand command) | Constructor | public | Crea un espacio a partir de un comando de registro. |
| occupy() | void | public | Cambia el estado a OCCUPIED y actualiza lastUpdated. Lanza excepción si ya está ocupado o fuera de servicio. |
| release() | void | public | Cambia el estado a AVAILABLE y actualiza lastUpdated. Lanza excepción si ya está disponible. |
| markOutOfService() | void | public | Marca el espacio como fuera de servicio para mantenimiento. |
| markActive() | void | public | Reactiva un espacio que estaba fuera de servicio, cambiando a AVAILABLE. |
| isAvailable() | boolean | public | Devuelve true si el estado es AVAILABLE. |
| isOccupied() | boolean | public | Devuelve true si el estado es OCCUPIED. |
 
#### 2. ParkingFacility (Aggregate Root)
 
Representa el estacionamiento completo de un centro comercial.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único del estacionamiento. |
| name | FacilityName | private | Nombre del estacionamiento (e.g., "Jockey Plaza B2"). |
| totalSlots | int | private | Cantidad total de espacios. |
| address | Address | private | Dirección física del estacionamiento. |
 
**Métodos principales:**
 
| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| ParkingFacility() | Constructor | protected | Constructor protegido para JPA. |
| ParkingFacility(RegisterFacilityCommand command) | Constructor | public | Crea un estacionamiento a partir de un comando. |
| updateInfo(String name, String address) | ParkingFacility | public | Actualiza nombre y dirección del estacionamiento. |
 
#### 3. RegisterParkingSlotCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| slotCode | String | public | Código del espacio (e.g., "A-15"). |
| sensorId | String | public | Identificador del sensor asignado. |
| facilityId | Long | public | ID del estacionamiento. |
 
#### 4. UpdateSlotStatusCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| slotId | Long | public | ID del espacio a actualizar. |
| newStatus | SlotStatus | public | Nuevo estado (AVAILABLE, OCCUPIED, OUT_OF_SERVICE). |
 
#### 5. ProcessSensorReadingCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sensorId | String | public | ID del sensor que envía la lectura. |
| slotId | Long | public | ID del espacio monitoreado. |
| distance | double | public | Distancia detectada en centímetros. |
| timestamp | LocalDateTime | public | Momento de la lectura. |
 
#### 6. Queries
 
| Query | Atributos principales | Descripción |
|---|---|---|
| GetAllSlotsQuery | facilityId : Long | Obtiene todos los espacios de un estacionamiento. |
| GetAvailableSlotsQuery | facilityId : Long | Obtiene solo los espacios disponibles. |
| GetSlotByIdQuery | slotId : Long | Obtiene un espacio por su identificador. |
| GetSlotRecommendationsQuery | facilityId : Long | Obtiene espacios recomendados por proximidad. |
 
#### 7. SlotStatusChangedEvent (Domain Event)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| slotId | Long | private | ID del espacio que cambió. |
| slotCode | String | private | Código del espacio. |
| previousStatus | SlotStatus | private | Estado anterior. |
| newStatus | SlotStatus | private | Nuevo estado. |
| timestamp | LocalDateTime | private | Momento del cambio. |
 
#### 8. ParkingSlotCommandService (Domain Service)
 
Proporciona métodos para manejar comandos relacionados con la gestión de espacios.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(RegisterParkingSlotCommand command) | Optional\<ParkingSlot> | public | Registra un nuevo espacio en el sistema. |
| handle(UpdateSlotStatusCommand command) | void | public | Actualiza el estado de un espacio (admin: habilitar/deshabilitar). |
| handle(ProcessSensorReadingCommand command) | void | public | Procesa una lectura de sensor y actualiza el estado del espacio si corresponde. |
 
#### 9. ParkingSlotQueryService (Domain Service)
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetAllSlotsQuery query) | List\<ParkingSlot> | public | Obtiene todos los espacios del estacionamiento. |
| handle(GetAvailableSlotsQuery query) | List\<ParkingSlot> | public | Obtiene solo los espacios con estado AVAILABLE. |
| handle(GetSlotByIdQuery query) | Optional\<ParkingSlot> | public | Obtiene un espacio específico por su ID. |
| handle(GetSlotRecommendationsQuery query) | List\<ParkingSlot> | public | Obtiene espacios disponibles recomendados por proximidad. |
 
#### 10. OccupancyCalculationService (Domain Service)
 
Servicio de dominio que encapsula la lógica de cálculo de ocupación y debounce de sensores.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| evaluateSensorReading(double distance, SlotStatus currentStatus) | Optional\<SlotStatus> | public | Evalúa una lectura de sensor y determina si debe cambiar el estado. Aplica regla de debounce: distancia < 15cm → OCCUPIED, > 50cm → AVAILABLE. |
| calculateOccupancyRate(long totalSlots, long occupiedSlots) | double | public | Calcula la tasa de ocupación como porcentaje. |
| shouldTriggerAlert(double occupancyRate) | boolean | public | Devuelve true si la ocupación supera el 90% (umbral configurable). |
 
#### 11. SlotCode (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| code | String | private | Código del espacio (máx. 20 caracteres, formato "LETRA-NÚMERO"). |
 
| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| SlotCode() | Constructor | public | Constructor requerido por JPA. |
| SlotCode(String code) | Constructor | public | Inicializa y valida el formato del código. |
 
#### 12. SlotStatus (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| AVAILABLE | Enum | public | El espacio está libre. |
| OCCUPIED | Enum | public | El espacio está ocupado por un vehículo. |
| OUT_OF_SERVICE | Enum | public | El espacio está fuera de servicio (mantenimiento). |
 
#### 13. SensorId (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sensorId | String | private | Identificador único del sensor (e.g., "ESP32-SLOT-A15"). |
 
| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| SensorId() | Constructor | public | Constructor requerido por JPA. |
| SensorId(String sensorId) | Constructor | public | Inicializa y valida que no sea vacío. |
 
#### 14. FacilityId (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| facilityId | Long | private | ID del estacionamiento; debe ser > 0. |
 
---
 
### 4.2.1.2. Interface Layer
 
#### 1. ParkingSlotsController (REST Controller)
 
Controlador REST que expone endpoints para gestionar y consultar espacios de estacionamiento.
 
| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| getAllSlots | /api/v1/parking-slots | GET | Obtiene todos los espacios con su estado actual. |
| getAvailableSlots | /api/v1/parking-slots/available | GET | Obtiene solo los espacios disponibles. |
| getSlotById | /api/v1/parking-slots/{id} | GET | Obtiene un espacio específico por su ID. |
| updateSlotStatus | /api/v1/parking-slots/{id}/status | PATCH | Actualiza el estado de un espacio (admin). |
| getRecommendations | /api/v1/parking-slots/recommendations | GET | Obtiene espacios recomendados por proximidad. |
 
#### 2. SensorReadingsController (REST Controller)
 
Controlador REST que recibe las lecturas de sensores desde el edge server.
 
| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| registerReading | /api/v1/sensor-readings | POST | Recibe y procesa una lectura de sensor ultrasónico. |
 
#### 3. Resources (DTOs)
 
| Resource | Atributos principales | Descripción |
|---|---|---|
| ParkingSlotResource | id: Long, slotCode: String, status: String, sensorId: String, lastUpdated: LocalDateTime | Representación de un espacio para la API. |
| SensorReadingResource | sensorId: String, slotId: Long, distance: double, timestamp: LocalDateTime | Lectura de sensor recibida del edge server. |
| SlotStatusUpdateResource | status: String | Datos para actualizar estado de un espacio. |
 
#### 4. Transform (Assemblers)
 
| Assembler | Entrada | Salida | Descripción |
|---|---|---|---|
| ParkingSlotResourceFromEntityAssembler | ParkingSlot | ParkingSlotResource | Convierte entidad de dominio a DTO de respuesta. |
| ProcessSensorReadingCommandFromResourceAssembler | SensorReadingResource | ProcessSensorReadingCommand | Convierte DTO de lectura en comando de dominio. |
| UpdateSlotStatusCommandFromResourceAssembler | SlotStatusUpdateResource, Long slotId | UpdateSlotStatusCommand | Convierte DTO de actualización en comando. |
 
---
 
### 4.2.1.3. Application Layer
 
#### 1. ParkingSlotCommandServiceImpl (Command Service Implementation)
 
Implementación del servicio de comandos para gestionar espacios de estacionamiento.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| parkingSlotRepository | ParkingSlotRepository | private | Repositorio para persistencia de espacios. |
| occupancyCalculationService | OccupancyCalculationService | private | Servicio de cálculo de ocupación y debounce. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(RegisterParkingSlotCommand command) | Optional\<ParkingSlot> | public | Crea y persiste un nuevo espacio; valida que el slotCode sea único y el sensorId no esté ya asignado. |
| handle(UpdateSlotStatusCommand command) | void | public | Actualiza el estado de un espacio (admin: habilitar/deshabilitar para mantenimiento); persiste el cambio y publica SlotStatusChangedEvent. |
| handle(ProcessSensorReadingCommand command) | void | public | Procesa lectura del sensor: evalúa con OccupancyCalculationService si debe cambiar el estado, si cambia lo persiste y publica evento. |
 
#### 2. ParkingSlotQueryServiceImpl (Query Service Implementation)
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| parkingSlotRepository | ParkingSlotRepository | private | Repositorio para acceso de lectura. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetAllSlotsQuery query) | List\<ParkingSlot> | public | Obtiene todos los espacios del estacionamiento. |
| handle(GetAvailableSlotsQuery query) | List\<ParkingSlot> | public | Obtiene espacios con status AVAILABLE. |
| handle(GetSlotByIdQuery query) | Optional\<ParkingSlot> | public | Obtiene un espacio por su ID. |
| handle(GetSlotRecommendationsQuery query) | List\<ParkingSlot> | public | Obtiene espacios disponibles recomendados, priorizando por proximidad. |
 
#### 3. SlotStatusChangedEventHandler (Domain Event Handler)
 
Maneja el evento de cambio de estado para notificar vía WebSocket a clientes conectados.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| webSocketBroadcaster | WebSocketBroadcaster | private | Servicio para enviar actualizaciones en tiempo real. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| on(SlotStatusChangedEvent event) | void | public | Envía la actualización de estado del espacio vía WebSocket a dashboard y app móvil. |
 
---
 
### 4.2.1.4. Infrastructure Layer
 
#### 1. ParkingSlotRepository (Repository Interface)
 
Interfaz del repositorio para gestionar espacios de estacionamiento.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<ParkingSlot> | public | Busca un espacio por su ID. |
| save(ParkingSlot slot) | ParkingSlot | public | Persiste o actualiza un espacio. |
| findByStatus(SlotStatus status) | List\<ParkingSlot> | public | Obtiene espacios por estado. |
| findByFacilityId(FacilityId facilityId) | List\<ParkingSlot> | public | Obtiene todos los espacios de un estacionamiento. |
| countByStatus(SlotStatus status) | long | public | Cuenta espacios por estado (para cálculo de ocupación). |
| existsBySlotCode(SlotCode slotCode) | boolean | public | Verifica si un código de espacio ya existe. |
| existsBySensorId(SensorId sensorId) | boolean | public | Verifica si un sensor ya está asignado. |
| findBySensorId(SensorId sensorId) | Optional\<ParkingSlot> | public | Busca espacio por sensor (para procesar lecturas). |
 
#### 2. SensorReadingRepository (Repository Interface)
 
Interfaz del repositorio para almacenar lecturas históricas de sensores.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| save(SensorReading reading) | SensorReading | public | Persiste una lectura de sensor. |
| findBySensorIdAndTimestampBetween(String sensorId, LocalDateTime start, LocalDateTime end) | List\<SensorReading> | public | Obtiene lecturas de un sensor en un rango de tiempo. |
 
#### 3. WebSocketBroadcaster (Infrastructure Service)
 
Servicio que envía actualizaciones de estado en tiempo real vía WebSocket.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| broadcastSlotUpdate(Long slotId, SlotStatus status, String slotCode) | void | public | Envía actualización de estado a todos los clientes suscritos al canal de disponibilidad. |
| broadcastOccupancySummary(long total, long available, long occupied) | void | public | Envía resumen de ocupación actualizado. |
 
---
 
### 4.2.1.5. Bounded Context Software Architecture Component Level Diagrams
 
En esta sección se presentan los diagramas de nivel componente que ilustran la arquitectura de software del contexto de Parking Monitoring. Se muestra la interacción entre los diferentes componentes, servicios y capas que conforman este bounded context.
 
> **Diagrama a crear en Structurizr DSL:**

### 4.2.1.6. Bounded Context Software Architecture Code Level Diagrams
 
En esta sección se presentan los diagramas de nivel código que detallan la estructura interna del contexto de Parking Monitoring.
 
#### 4.2.1.6.1. Bounded Context Domain Layer Class Diagrams
 
El diagrama de clases del Domain Layer del contexto de Parking Monitoring ilustra las entidades, objetos de valor y servicios que componen este bounded context.
 
> **Diagrama a crear en LucidChart o PlantUML:**

#### 4.2.1.6.2. Bounded Context Database Design Diagram
 
El diagrama de diseño de base de datos del contexto de Parking Monitoring muestra la estructura de las tablas y sus relaciones en la base de datos relacional.
 
> **Diagrama a crear en Vertabelo:**

## 4.2.2. Bounded Context: Access Control
 
Este bounded context gestiona el ingreso y salida vehicular mediante ALPR (reconocimiento automático de placas) y control de barreras. Administra el ciclo de vida completo de las sesiones vehiculares desde el ingreso hasta la salida, incluyendo la verificación del estado de pago antes de autorizar la apertura de la barrera de salida.
 
### 4.2.2.1. Domain Layer
 
En esta sección se describen los elementos del Domain Layer del contexto de Access Control, que encapsulan la lógica central relacionada con el control de acceso vehicular y la gestión de sesiones.
 
#### 1. VehicleSession (Aggregate Root)
 
Representa el período completo desde que un vehículo ingresa al estacionamiento hasta que sale. Es la entidad central del bounded context.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único de la sesión. |
| licensePlate | LicensePlate | private | Placa del vehículo asociado a la sesión. |
| entryTimestamp | LocalDateTime | private | Fecha y hora de ingreso del vehículo. |
| exitTimestamp | LocalDateTime | private | Fecha y hora de salida del vehículo (null mientras está activa). |
| slotId | SlotId | private | Identificador del espacio donde se estacionó el vehículo. |
| paymentStatus | PaymentStatus | private | Estado del pago de la sesión (PENDING o PAID). |
| sessionStatus | SessionStatus | private | Estado de la sesión (ACTIVE o COMPLETED). |
| userId | UserId | private | Identificador del usuario propietario del vehículo (null si no registrado). |
 
**Métodos principales:**
 
| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| VehicleSession() | Constructor | protected | Constructor protegido para JPA. |
| VehicleSession(CreateVehicleSessionCommand command) | Constructor | public | Crea una sesión a partir de un comando de ingreso. Inicializa con sessionStatus=ACTIVE, paymentStatus=PENDING, exitTimestamp=null. |
| end(LocalDateTime exitTimestamp) | void | public | Finaliza la sesión registrando el timestamp de salida y cambiando sessionStatus a COMPLETED. Lanza excepción si paymentStatus no es PAID. |
| markAsPaid() | void | public | Cambia paymentStatus a PAID. Lanza excepción si ya está pagada o si la sesión no está activa. |
| assignSlot(SlotId slotId) | void | public | Asocia un espacio de estacionamiento a la sesión (para Find My Car). |
| calculateDuration() | Duration | public | Calcula la duración entre entryTimestamp y el momento actual (si activa) o exitTimestamp (si completada). |
| isActive() | boolean | public | Devuelve true si sessionStatus es ACTIVE. |
| isPaid() | boolean | public | Devuelve true si paymentStatus es PAID. |
 
#### 2. AccessBarrier (Aggregate Root)
 
Representa una barrera física motorizada ubicada en un punto de entrada o salida del estacionamiento.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único de la barrera. |
| barrierCode | BarrierCode | private | Código identificador de la barrera (e.g., "ENTRY-01", "EXIT-01"). |
| position | BarrierPosition | private | Posición de la barrera (ENTRY o EXIT). |
| status | BarrierStatus | private | Estado actual de la barrera (OPEN o CLOSED). |
| facilityId | FacilityId | private | Identificador del estacionamiento al que pertenece. |
 
**Métodos principales:**
 
| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| AccessBarrier() | Constructor | protected | Constructor protegido para JPA. |
| AccessBarrier(RegisterBarrierCommand command) | Constructor | public | Crea una barrera a partir de un comando. |
| open() | void | public | Cambia el estado a OPEN. Publica BarrierOpenedEvent. |
| close() | void | public | Cambia el estado a CLOSED. |
| forceOpen(String reason) | void | public | Abre la barrera forzosamente (emergencia). Ignora validaciones normales. |
 
#### 3. CreateVehicleSessionCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| licensePlate | String | public | Texto de la placa reconocida por ALPR. |
| entryTimestamp | LocalDateTime | public | Momento del ingreso. |
| userId | Long | public | ID del usuario (null si vehículo no registrado). |
 
#### 4. EndVehicleSessionCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sessionId | Long | public | ID de la sesión a finalizar. |
| exitTimestamp | LocalDateTime | public | Momento de la salida. |
 
#### 5. RecognizePlateCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| imageData | byte[] | public | Imagen capturada por ESP32-CAM. |
| cameraPosition | String | public | Posición de la cámara (ENTRY o EXIT). |
 
#### 6. RegisterEntryCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| imageData | byte[] | public | Imagen de la placa capturada. |
| barrierCode | String | public | Código de la barrera de entrada. |
 
#### 7. RegisterExitCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| imageData | byte[] | public | Imagen de la placa capturada en salida. |
| barrierCode | String | public | Código de la barrera de salida. |
 
#### 8. OpenAllBarriersCommand (Command)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| reason | String | public | Razón de la apertura (e.g., "EMERGENCY"). |
 
#### 9. Queries
 
| Query | Atributos principales | Descripción |
|---|---|---|
| GetActiveSessionQuery | userId : Long | Obtiene la sesión activa del usuario autenticado. |
| GetSessionByIdQuery | sessionId : Long | Obtiene una sesión específica por ID. |
| GetSessionByPlateQuery | licensePlate : String | Obtiene la sesión activa asociada a una placa. |
| GetSessionHistoryQuery | userId : Long | Obtiene las sesiones pasadas del usuario. |
| GetBarrierStatusQuery | barrierCode : String | Obtiene el estado de una barrera. |
 
#### 10. VehicleSessionStartedEvent (Domain Event)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| sessionId | Long | private | ID de la sesión creada. |
| licensePlate | String | private | Placa del vehículo. |
| entryTimestamp | LocalDateTime | private | Momento del ingreso. |
| userId | Long | private | ID del usuario (null si no registrado). |
 
#### 11. VehicleSessionEndedEvent (Domain Event)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| sessionId | Long | private | ID de la sesión finalizada. |
| licensePlate | String | private | Placa del vehículo. |
| exitTimestamp | LocalDateTime | private | Momento de la salida. |
| slotId | Long | private | ID del espacio que se libera. |
 
#### 12. BarrierOpenedEvent (Domain Event)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| barrierCode | String | private | Código de la barrera que se abrió. |
| position | BarrierPosition | private | Posición (ENTRY o EXIT). |
| reason | String | private | Razón de apertura (PLATE_RECOGNIZED, PAYMENT_VERIFIED, EMERGENCY). |
 
#### 13. AccessCommandService (Domain Service)
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(RegisterEntryCommand command) | Optional\<VehicleSession> | public | Procesa ingreso: captura placa via ALPR, verifica registro, abre barrera, crea sesión. |
| handle(RegisterExitCommand command) | void | public | Procesa salida: captura placa, verifica pago, abre barrera, finaliza sesión. |
| handle(RecognizePlateCommand command) | Optional\<LicensePlate> | public | Envía imagen a Plate Recognizer API y retorna la placa reconocida. |
| handle(OpenAllBarriersCommand command) | void | public | Abre todas las barreras (emergencia). |
 
#### 14. VehicleSessionCommandService (Domain Service)
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(CreateVehicleSessionCommand command) | Optional\<VehicleSession> | public | Crea una nueva sesión vehicular. Valida que la placa no tenga sesión activa. |
| handle(EndVehicleSessionCommand command) | void | public | Finaliza una sesión. Valida que el pago esté completado. |
 
#### 15. VehicleSessionQueryService (Domain Service)
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetActiveSessionQuery query) | Optional\<VehicleSession> | public | Obtiene la sesión activa del usuario. |
| handle(GetSessionByIdQuery query) | Optional\<VehicleSession> | public | Obtiene una sesión por ID. |
| handle(GetSessionByPlateQuery query) | Optional\<VehicleSession> | public | Obtiene sesión activa por placa. |
| handle(GetSessionHistoryQuery query) | List\<VehicleSession> | public | Obtiene historial de sesiones del usuario. |
 
#### 16. LicensePlate (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| plateText | String | private | Texto alfanumérico de la placa (formato peruano: A0B-123). |
| confidence | double | private | Nivel de confianza del reconocimiento ALPR (0.0 a 1.0). |
 
| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| LicensePlate() | Constructor | public | Constructor requerido por JPA. |
| LicensePlate(String plateText, double confidence) | Constructor | public | Inicializa y valida formato de placa y confianza > 0. |
| isHighConfidence() | boolean | public | Devuelve true si confidence > 0.85. |
 
#### 17. SessionStatus (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| ACTIVE | Enum | public | La sesión está en curso. |
| COMPLETED | Enum | public | La sesión ha finalizado (vehículo salió). |
 
#### 18. PaymentStatus (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| PENDING | Enum | public | El pago está pendiente. |
| PAID | Enum | public | El pago ha sido completado. |
 
#### 19. BarrierPosition (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| ENTRY | Enum | public | Barrera de entrada. |
| EXIT | Enum | public | Barrera de salida. |
 
#### 20. BarrierStatus (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| OPEN | Enum | public | La barrera está abierta. |
| CLOSED | Enum | public | La barrera está cerrada. |
 
#### 21. BarrierCode (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| code | String | private | Código identificador de la barrera (e.g., "ENTRY-01"). |
 
#### 22. SlotId (Value Object)
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| slotId | Long | private | ID del espacio de estacionamiento asociado. |
 
#### 23. PlateRecognitionService (Domain Service Interface)
 
Interfaz del servicio de reconocimiento de placas. La implementación concreta vive en Infrastructure Layer.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| recognizePlate(byte[] imageData) | Optional\<LicensePlate> | public | Envía imagen a servicio externo y retorna la placa reconocida con nivel de confianza. |
 
---
 
### 4.2.2.2. Interface Layer
 
#### 1. AccessController (REST Controller)
 
Controlador REST que expone endpoints para el control de acceso vehicular (ingreso y salida).
 
| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| registerEntry | /api/v1/access/entries | POST | Registra el ingreso de un vehículo. Recibe imagen de placa, procesa ALPR, abre barrera y crea sesión. |
| registerExit | /api/v1/access/exits | POST | Registra la salida de un vehículo. Verifica pago, abre barrera y finaliza sesión. |
| recognizePlate | /api/v1/access/alpr | POST | Procesa una imagen para reconocimiento de placa (endpoint auxiliar). |
 
#### 2. ParkingSessionsController (REST Controller)
 
Controlador REST que expone endpoints para gestionar y consultar sesiones vehiculares.
 
| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| createSession | /api/v1/parking-sessions | POST | Crea una nueva sesión vehicular. |
| getActiveSession | /api/v1/parking-sessions/active | GET | Obtiene la sesión activa del usuario autenticado. |
| getSessionById | /api/v1/parking-sessions/{id} | GET | Obtiene una sesión específica por su ID. |
| endSession | /api/v1/parking-sessions/{id}/end | PATCH | Finaliza una sesión vehicular (requiere pago completado). |
| getSessionHistory | /api/v1/parking-sessions/history | GET | Obtiene el historial de sesiones del usuario. |
 
#### 3. Resources (DTOs)
 
| Resource | Atributos principales | Descripción |
|---|---|---|
| EntryRequestResource | imageData: String (base64), barrierCode: String | Solicitud de ingreso con imagen de placa. |
| ExitRequestResource | imageData: String (base64), barrierCode: String | Solicitud de salida con imagen de placa. |
| PlateRecognitionResource | imageData: String (base64), cameraPosition: String | Imagen para reconocimiento de placa. |
| PlateRecognitionResultResource | licensePlate: String, confidence: double, isHighConfidence: boolean | Resultado del reconocimiento de placa. |
| VehicleSessionResource | id: Long, licensePlate: String, entryTimestamp: LocalDateTime, exitTimestamp: LocalDateTime, slotCode: String, paymentStatus: String, sessionStatus: String, currentDuration: String, estimatedFee: BigDecimal | Representación completa de una sesión. |
| CreateSessionResource | licensePlate: String | Datos para crear sesión manualmente. |
 
#### 4. Transform (Assemblers)
 
| Assembler | Entrada | Salida | Descripción |
|---|---|---|---|
| VehicleSessionResourceFromEntityAssembler | VehicleSession | VehicleSessionResource | Convierte entidad a DTO de respuesta, calcula duración y fee estimado. |
| RegisterEntryCommandFromResourceAssembler | EntryRequestResource | RegisterEntryCommand | Convierte DTO de ingreso en comando. |
| RegisterExitCommandFromResourceAssembler | ExitRequestResource | RegisterExitCommand | Convierte DTO de salida en comando. |
| RecognizePlateCommandFromResourceAssembler | PlateRecognitionResource | RecognizePlateCommand | Convierte imagen en comando de reconocimiento. |
 
---
 
### 4.2.2.3. Application Layer
 
#### 1. AccessCommandServiceImpl (Command Service Implementation)
 
Implementación del servicio de comandos para controlar el acceso vehicular.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| vehicleSessionRepository | VehicleSessionRepository | private | Repositorio para persistencia de sesiones. |
| accessBarrierRepository | AccessBarrierRepository | private | Repositorio para persistencia de barreras. |
| plateRecognitionService | PlateRecognitionService | private | Servicio de reconocimiento de placas (Plate Recognizer API). |
| externalIamService | ExternalIamService | private | Servicio ACL para verificar si la placa está registrada en IAM. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(RegisterEntryCommand command) | Optional\<VehicleSession> | public | Procesa ingreso completo: (1) envía imagen a PlateRecognitionService, (2) verifica si la placa está registrada via IAM, (3) crea VehicleSession, (4) abre barrera de entrada, (5) publica VehicleSessionStartedEvent. Si ALPR falla tras 3 intentos, crea sesión como "unidentified". |
| handle(RegisterExitCommand command) | void | public | Procesa salida completa: (1) reconoce placa, (2) busca sesión activa por placa, (3) verifica paymentStatus==PAID, (4) si pagado abre barrera y finaliza sesión publicando VehicleSessionEndedEvent; si no pagado devuelve 402. |
| handle(RecognizePlateCommand command) | Optional\<LicensePlate> | public | Envía imagen al PlateRecognitionService y retorna el resultado. |
| handle(OpenAllBarriersCommand command) | void | public | Abre todas las barreras del estacionamiento (recibido desde Emergency BC via evento). |
 
#### 2. VehicleSessionCommandServiceImpl (Command Service Implementation)
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| vehicleSessionRepository | VehicleSessionRepository | private | Repositorio para persistencia de sesiones. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(CreateVehicleSessionCommand command) | Optional\<VehicleSession> | public | Crea sesión; valida que la placa no tenga sesión activa (409 Conflict si existe). |
| handle(EndVehicleSessionCommand command) | void | public | Finaliza sesión; valida pago completado (402 si pendiente). Publica VehicleSessionEndedEvent. |
 
#### 3. VehicleSessionQueryServiceImpl (Query Service Implementation)
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| vehicleSessionRepository | VehicleSessionRepository | private | Repositorio para acceso de lectura. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetActiveSessionQuery query) | Optional\<VehicleSession> | public | Obtiene la sesión activa del usuario por su userId. |
| handle(GetSessionByIdQuery query) | Optional\<VehicleSession> | public | Obtiene sesión por ID. |
| handle(GetSessionByPlateQuery query) | Optional\<VehicleSession> | public | Obtiene sesión activa por placa (para el flujo de salida). |
| handle(GetSessionHistoryQuery query) | List\<VehicleSession> | public | Obtiene sesiones completadas del usuario, ordenadas por fecha descendente. |
 
#### 4. VehicleSessionStartedEventHandler (Domain Event Handler)
 
Maneja el evento de inicio de sesión para notificar al conductor.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| externalNotificationService | ExternalNotificationService | private | Servicio ACL para enviar notificaciones al BC de Notification. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| on(VehicleSessionStartedEvent event) | void | public | Envía notificación push al conductor confirmando el ingreso con hora y placa. Solo envía si userId no es null (vehículo registrado). |
 
#### 5. VehicleSessionEndedEventHandler (Domain Event Handler)
 
Maneja el evento de fin de sesión para liberar el espacio en Parking Monitoring.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| externalParkingMonitoringService | ExternalParkingMonitoringService | private | Servicio ACL para comunicarse con Parking Monitoring BC. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| on(VehicleSessionEndedEvent event) | void | public | Notifica a Parking Monitoring para liberar el espacio (slotId) asociado a la sesión finalizada. |
 
#### 6. ExternalIamService (Outbound ACL Service)
 
Adaptador de salida hacia IAM para verificar si una placa está registrada.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findUserByLicensePlate(String licensePlate) | Optional\<Long> | public | Busca en IAM si existe un usuario con la placa indicada. Retorna userId si existe. |
 
#### 7. ExternalNotificationService (Outbound ACL Service)
 
Adaptador de salida hacia Notification Management BC.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| sendEntryNotification(Long userId, String licensePlate, LocalDateTime entryTime) | void | public | Solicita al BC de Notificaciones enviar push de confirmación de ingreso. |
| sendPaymentReminderNotification(Long userId, Long sessionId) | void | public | Solicita enviar recordatorio de pago pendiente cuando el conductor llega a la salida sin pagar. |
 
#### 8. ExternalParkingMonitoringService (Outbound ACL Service)
 
Adaptador de salida hacia Parking Monitoring BC.
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| releaseSlot(Long slotId) | void | public | Notifica a Parking Monitoring que el espacio debe liberarse tras la salida del vehículo. |
 
---
 
### 4.2.2.4. Infrastructure Layer
 
#### 1. VehicleSessionRepository (Repository Interface)
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<VehicleSession> | public | Busca una sesión por su ID. |
| save(VehicleSession session) | VehicleSession | public | Persiste o actualiza una sesión. |
| findByLicensePlate_PlateTextAndSessionStatus(String plateText, SessionStatus status) | Optional\<VehicleSession> | public | Busca sesión activa por texto de placa. |
| findByUserIdAndSessionStatus(UserId userId, SessionStatus status) | Optional\<VehicleSession> | public | Busca sesión activa por usuario. |
| findByUserIdOrderByEntryTimestampDesc(UserId userId) | List\<VehicleSession> | public | Obtiene historial de sesiones ordenado por fecha. |
| existsByLicensePlate_PlateTextAndSessionStatus(String plateText, SessionStatus status) | boolean | public | Verifica si existe sesión activa para una placa. |
 
#### 2. AccessBarrierRepository (Repository Interface)
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<AccessBarrier> | public | Busca una barrera por su ID. |
| save(AccessBarrier barrier) | AccessBarrier | public | Persiste o actualiza una barrera. |
| findByBarrierCode(BarrierCode code) | Optional\<AccessBarrier> | public | Busca barrera por código. |
| findByPosition(BarrierPosition position) | List\<AccessBarrier> | public | Obtiene barreras por posición (ENTRY/EXIT). |
| findAll() | List\<AccessBarrier> | public | Obtiene todas las barreras (para abrir todas en emergencia). |
 
#### 3. PlateRecognizerClient (Infrastructure Service)
 
Implementación concreta del servicio de reconocimiento de placas usando Plate Recognizer API.
 
**Atributos principales:**
 
| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| apiUrl | String | private | URL del endpoint de Plate Recognizer API (configurado en application.properties). |
| apiToken | String | private | Token de autenticación para la API (tier gratuito: 2,500 consultas/mes). |
| restTemplate | RestTemplate | private | Cliente HTTP para realizar las llamadas a la API. |
 
**Métodos principales:**
 
| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| recognizePlate(byte[] imageData) | Optional\<LicensePlate> | public | Envía imagen como multipart/form-data a Plate Recognizer API. Parsea la respuesta JSON y retorna LicensePlate con plateText y confidence. Retorna empty si no se detecta placa. |
 
---
 
### 4.2.2.5. Bounded Context Software Architecture Component Level Diagrams
 
En esta sección se presentan los diagramas de nivel componente que ilustran la arquitectura de software del contexto de Access Control. Se muestra la interacción entre los diferentes componentes, servicios y capas que conforman este bounded context, incluyendo la integración con sistemas externos (Plate Recognizer API, ESP32-CAM).
 
> **Diagrama a crear en Structurizr DSL:**

### 4.2.2.6. Bounded Context Software Architecture Code Level Diagrams
 
En esta sección se presentan los diagramas de nivel código que detallan la estructura interna del contexto de Access Control.
 
#### 4.2.2.6.1. Bounded Context Domain Layer Class Diagrams
 
El diagrama de clases del Domain Layer del contexto de Access Control ilustra las entidades, objetos de valor y servicios que componen este bounded context.
 
> **Diagrama a crear en LucidChart o PlantUML:**

#### 4.2.2.6.2. Bounded Context Database Design Diagram
 
El diagrama de diseño de base de datos del contexto de Access Control muestra la estructura de las tablas y sus relaciones.
 
> **Diagrama a crear en Vertabelo:**

## 4.2.3. Bounded Context: Payment Processing

Este bounded context gestiona el cálculo de tarifas y el procesamiento de pagos digitales del estacionamiento a través de la pasarela Culqi (tarjeta de crédito/débito y Yape). Genera recibos digitales, mantiene el historial de transacciones y notifica a Access Control cuando un pago se completa para autorizar la salida del vehículo.

### 4.2.3.1. Domain Layer

En esta sección se describen los elementos del Domain Layer del contexto de Payment Processing, que encapsulan la lógica central relacionada con el cálculo de tarifas, procesamiento de pagos y generación de recibos.

#### 1. Payment (Aggregate Root)

Representa una transacción de pago asociada a una sesión vehicular.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único del pago. |
| sessionId | SessionId | private | Identificador de la sesión vehicular asociada al pago. |
| amount | Money | private | Monto cobrado por el estacionamiento. |
| currency | Currency | private | Moneda de la transacción (PEN por defecto). |
| paymentMethod | PaymentMethod | private | Método de pago utilizado (YAPE, CREDIT_CARD, DEBIT_CARD). |
| status | PaymentTransactionStatus | private | Estado de la transacción (PENDING, COMPLETED, FAILED). |
| transactionId | String | private | Identificador de la transacción devuelto por Culqi. |
| receiptUrl | String | private | URL del recibo digital generado tras pago exitoso. |
| paidAt | LocalDateTime | private | Fecha y hora en que se completó el pago. |
| parkingFee | ParkingFee | private | Detalle del cálculo de la tarifa (duración, tarifa por hora, monto). |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| Payment() | Constructor | protected | Constructor protegido para JPA. |
| Payment(InitiatePaymentCommand command) | Constructor | public | Crea un pago a partir de un comando. Inicializa con status=PENDING, paidAt=null, transactionId=null. |
| markAsCompleted(String transactionId, String receiptUrl) | void | public | Marca el pago como completado. Registra transactionId de Culqi, receiptUrl y paidAt. Lanza excepción si ya está completado. Publica PaymentSucceededEvent. |
| markAsFailed(String errorDetail) | void | public | Marca el pago como fallido. Registra el detalle del error. Publica PaymentFailedEvent. |
| isCompleted() | boolean | public | Devuelve true si status es COMPLETED. |
| isFailed() | boolean | public | Devuelve true si status es FAILED. |
| isPending() | boolean | public | Devuelve true si status es PENDING. |

#### 2. InitiatePaymentCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sessionId | Long | public | ID de la sesión vehicular a pagar. |
| paymentMethod | String | public | Método de pago ("YAPE", "CREDIT_CARD", "DEBIT_CARD"). |
| token | String | public | Token de pago generado por Culqi Checkout en el frontend. |

#### 3. CalculateFeeCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sessionId | Long | public | ID de la sesión para calcular la tarifa. |
| entryTimestamp | LocalDateTime | public | Hora de ingreso del vehículo. |
| exitTimestamp | LocalDateTime | public | Hora actual o de salida (para cálculo). |

#### 4. Queries

| Query | Atributos principales | Descripción |
|---|---|---|
| GetPaymentByIdQuery | paymentId : Long | Obtiene un pago por su identificador. |
| GetPaymentBySessionIdQuery | sessionId : Long | Obtiene el pago asociado a una sesión. |
| GetPaymentHistoryQuery | userId : Long | Obtiene el historial de pagos del usuario. |
| GetPaymentStatusQuery | sessionId : Long | Verifica el estado de pago de una sesión (usado por Access Control). |

#### 5. PaymentSucceededEvent (Domain Event)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| paymentId | Long | private | ID del pago completado. |
| sessionId | Long | private | ID de la sesión vehicular pagada. |
| amount | BigDecimal | private | Monto cobrado. |
| paymentMethod | String | private | Método de pago utilizado. |
| transactionId | String | private | ID de transacción de Culqi. |
| paidAt | LocalDateTime | private | Momento del pago. |

#### 6. PaymentFailedEvent (Domain Event)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| paymentId | Long | private | ID del pago fallido. |
| sessionId | Long | private | ID de la sesión vehicular. |
| errorDetail | String | private | Detalle del error retornado por Culqi. |

#### 7. PaymentCommandService (Domain Service)

Proporciona métodos para manejar comandos relacionados con el procesamiento de pagos.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(InitiatePaymentCommand command) | Optional\<Payment> | public | Inicia el proceso de pago: calcula tarifa, envía a pasarela Culqi, marca como completado o fallido según respuesta. |
| handle(CalculateFeeCommand command) | ParkingFee | public | Calcula la tarifa de estacionamiento basada en la duración de la sesión. |

#### 8. PaymentQueryService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetPaymentByIdQuery query) | Optional\<Payment> | public | Obtiene un pago por su ID. |
| handle(GetPaymentBySessionIdQuery query) | Optional\<Payment> | public | Obtiene el pago asociado a una sesión. |
| handle(GetPaymentHistoryQuery query) | List\<Payment> | public | Obtiene historial de pagos del usuario. |
| handle(GetPaymentStatusQuery query) | Optional\<PaymentTransactionStatus> | public | Retorna el estado del pago de una sesión (para verificación de Access Control en la salida). |

#### 9. FeeCalculationService (Domain Service)

Servicio de dominio que encapsula la lógica de cálculo de tarifas de estacionamiento.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| calculateFee(LocalDateTime entryTimestamp, LocalDateTime currentTimestamp, BigDecimal ratePerHour) | ParkingFee | public | Calcula la tarifa usando la regla: monto = ceil(horas) × tarifa_por_hora. Ejemplo: 2h 15min → 3 horas × S/ 5.00 = S/ 15.00. |
| getDefaultRatePerHour() | BigDecimal | public | Retorna la tarifa por hora configurada por defecto (S/ 5.00, configurable). |

#### 10. PaymentGatewayService (Domain Service Interface)

Interfaz del servicio de pasarela de pagos. La implementación concreta vive en Infrastructure Layer.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| processPayment(BigDecimal amount, String currency, String token, PaymentMethod method) | PaymentGatewayResponse | public | Envía la solicitud de cobro a la pasarela y retorna la respuesta con transactionId y status. |

#### 11. Money (Value Object)

Representa un monto monetario con precisión decimal.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| amount | BigDecimal | private | Monto monetario con precisión de 2 decimales. |

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| Money() | Constructor | public | Constructor requerido por JPA (valor 0.00). |
| Money(BigDecimal amount) | Constructor | public | Inicializa y valida que el monto sea >= 0. |
| Money(double amount) | Constructor | public | Inicializa desde double, convierte a BigDecimal con escala 2. |
| add(Money other) | Money | public | Suma dos montos y retorna nuevo Money. |
| isGreaterThan(Money other) | boolean | public | Compara si es mayor que otro monto. |

#### 12. Currency (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| PEN | Enum | public | Sol peruano (moneda por defecto). |
| USD | Enum | public | Dólar americano (futuro soporte). |

#### 13. PaymentMethod (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| YAPE | Enum | public | Pago via Yape (procesado a través de Culqi). |
| CREDIT_CARD | Enum | public | Pago con tarjeta de crédito. |
| DEBIT_CARD | Enum | public | Pago con tarjeta de débito. |

#### 14. PaymentTransactionStatus (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| PENDING | Enum | public | El pago está en proceso. |
| COMPLETED | Enum | public | El pago se completó exitosamente. |
| FAILED | Enum | public | El pago falló (error de pasarela, fondos insuficientes, etc.). |

#### 15. ParkingFee (Value Object)

Representa el detalle del cálculo de la tarifa de estacionamiento.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| amount | BigDecimal | private | Monto total a pagar. |
| duration | Duration | private | Duración de la estancia (entre entrada y momento del cálculo). |
| ratePerHour | BigDecimal | private | Tarifa por hora aplicada. |
| hoursCharged | int | private | Número de horas cobradas (ceil de la duración). |

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| ParkingFee(BigDecimal amount, Duration duration, BigDecimal ratePerHour, int hoursCharged) | Constructor | public | Inicializa con todos los valores del cálculo. |
| getFormattedDuration() | String | public | Retorna la duración formateada como "Xh Ymin". |

#### 16. SessionId (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sessionId | Long | private | ID de la sesión vehicular asociada; debe ser > 0. |

#### 17. PaymentGatewayResponse (Value Object)

Respuesta de la pasarela de pagos tras procesar una transacción.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| success | boolean | private | Indica si la transacción fue exitosa. |
| transactionId | String | private | ID de transacción asignado por Culqi. |
| errorDetail | String | private | Detalle del error (null si fue exitosa). |
| receiptUrl | String | private | URL del recibo generado por Culqi (null si falló). |

---

### 4.2.3.2. Interface Layer

#### 1. PaymentsController (REST Controller)

Controlador REST que expone endpoints para gestionar pagos de estacionamiento.

| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| initiatePayment | /api/v1/payments | POST | Procesa un pago asociado a una sesión vehicular. Recibe sessionId, paymentMethod y token de Culqi. |
| getPaymentById | /api/v1/payments/{id} | GET | Obtiene los detalles de un pago específico por su ID. |
| getPaymentBySessionId | /api/v1/payments/session/{sessionId} | GET | Obtiene el pago asociado a una sesión vehicular. |
| getPaymentHistory | /api/v1/payments/history | GET | Obtiene el historial de pagos del usuario autenticado. |
| calculateFee | /api/v1/payments/calculate-fee/{sessionId} | GET | Calcula y retorna la tarifa estimada para una sesión activa. |

#### 2. Resources (DTOs)

| Resource | Atributos principales | Descripción |
|---|---|---|
| InitiatePaymentResource | sessionId: Long, paymentMethod: String, token: String | Datos para iniciar un pago. El token es generado por Culqi Checkout en el frontend. |
| PaymentResource | id: Long, sessionId: Long, amount: BigDecimal, currency: String, paymentMethod: String, status: String, transactionId: String, receiptUrl: String, paidAt: LocalDateTime, duration: String, hoursCharged: int | Representación completa de un pago para la API. |
| ParkingFeeResource | amount: BigDecimal, duration: String, ratePerHour: BigDecimal, hoursCharged: int, currency: String | Detalle del cálculo de tarifa para mostrar al conductor. |
| PaymentStatusResource | sessionId: Long, paymentStatus: String | Estado del pago de una sesión (para verificación en salida). |

#### 3. Transform (Assemblers)

| Assembler | Entrada | Salida | Descripción |
|---|---|---|---|
| PaymentResourceFromEntityAssembler | Payment | PaymentResource | Convierte entidad Payment a DTO de respuesta. Incluye duración formateada y horas cobradas. |
| InitiatePaymentCommandFromResourceAssembler | InitiatePaymentResource | InitiatePaymentCommand | Convierte DTO de pago en comando de dominio. |
| ParkingFeeResourceFromValueObjectAssembler | ParkingFee | ParkingFeeResource | Convierte value object ParkingFee a DTO de respuesta. |

---

### 4.2.3.3. Application Layer

#### 1. PaymentCommandServiceImpl (Command Service Implementation)

Implementación del servicio de comandos para gestionar pagos de estacionamiento.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| paymentRepository | PaymentRepository | private | Repositorio para persistencia de pagos. |
| paymentGatewayService | PaymentGatewayService | private | Servicio de pasarela de pagos (Culqi). |
| feeCalculationService | FeeCalculationService | private | Servicio de cálculo de tarifas. |
| externalAccessControlService | ExternalAccessControlService | private | Servicio ACL para comunicarse con Access Control BC. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(InitiatePaymentCommand command) | Optional\<Payment> | public | Procesa pago completo: (1) obtiene datos de sesión via ACL a Access Control, (2) calcula tarifa con FeeCalculationService, (3) crea entidad Payment, (4) envía a Culqi via PaymentGatewayService, (5) si exitoso marca como COMPLETED y publica PaymentSucceededEvent, (6) si falla marca como FAILED y publica PaymentFailedEvent. Valida que la sesión no haya sido pagada previamente (409 Conflict). |
| handle(CalculateFeeCommand command) | ParkingFee | public | Calcula la tarifa para una sesión activa sin procesar el pago. Obtiene timestamps de la sesión y aplica la regla de cálculo. |

#### 2. PaymentQueryServiceImpl (Query Service Implementation)

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| paymentRepository | PaymentRepository | private | Repositorio para acceso de lectura. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetPaymentByIdQuery query) | Optional\<Payment> | public | Obtiene un pago por su ID. |
| handle(GetPaymentBySessionIdQuery query) | Optional\<Payment> | public | Obtiene el pago asociado a una sesión. |
| handle(GetPaymentHistoryQuery query) | List\<Payment> | public | Obtiene pagos del usuario ordenados por fecha descendente. |
| handle(GetPaymentStatusQuery query) | Optional\<PaymentTransactionStatus> | public | Retorna el estado del pago de una sesión. Usado por Access Control para verificar si puede abrir la barrera de salida. |

#### 3. PaymentSucceededEventHandler (Domain Event Handler)

Maneja el evento de pago exitoso para notificar a Access Control y al conductor.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| externalAccessControlService | ExternalAccessControlService | private | Servicio ACL para notificar a Access Control. |
| externalNotificationService | ExternalNotificationService | private | Servicio ACL para enviar notificación al conductor. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| on(PaymentSucceededEvent event) | void | public | (1) Notifica a Access Control que la sesión fue pagada (actualiza paymentStatus a PAID en VehicleSession). (2) Envía notificación push al conductor confirmando el pago con monto y recibo. |

#### 4. PaymentFailedEventHandler (Domain Event Handler)

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| on(PaymentFailedEvent event) | void | public | Envía notificación push al conductor informando que el pago falló y debe reintentar. |

#### 5. ExternalAccessControlService (Outbound ACL Service)

Adaptador de salida hacia Access Control BC.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| getSessionDetails(Long sessionId) | Optional\<SessionDetailsDto> | public | Obtiene los datos de la sesión (entryTimestamp, licensePlate, userId) para calcular la tarifa. |
| markSessionAsPaid(Long sessionId) | void | public | Notifica a Access Control que la sesión ha sido pagada, actualizando el paymentStatus. |

#### 6. ExternalNotificationService (Outbound ACL Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| sendPaymentSuccessNotification(Long userId, BigDecimal amount, String receiptUrl) | void | public | Envía notificación push de confirmación de pago al conductor. |
| sendPaymentFailedNotification(Long userId, String errorDetail) | void | public | Envía notificación push informando que el pago falló. |

---

### 4.2.3.4. Infrastructure Layer

#### 1. PaymentRepository (Repository Interface)

Interfaz del repositorio para gestionar pagos.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<Payment> | public | Busca un pago por su ID. |
| save(Payment payment) | Payment | public | Persiste o actualiza un pago. |
| findBySessionId(SessionId sessionId) | Optional\<Payment> | public | Busca el pago asociado a una sesión vehicular. |
| findBySessionId_SessionIdAndStatus(Long sessionId, PaymentTransactionStatus status) | Optional\<Payment> | public | Busca pago por sesión y estado (para verificar si ya existe pago completado). |
| findByUserIdOrderByPaidAtDesc(Long userId) | List\<Payment> | public | Obtiene historial de pagos del usuario ordenado por fecha de pago descendente. |
| existsBySessionId(SessionId sessionId) | boolean | public | Verifica si ya existe un pago para la sesión. |

#### 2. CulqiPaymentGateway (Infrastructure Service)

Implementación concreta de PaymentGatewayService usando la API de Culqi como pasarela de pagos.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| culqiPublicKey | String | private | Clave pública de Culqi (configurada en application.properties). |
| culqiPrivateKey | String | private | Clave privada de Culqi para procesar cargos. |
| culqiApiUrl | String | private | URL base de la API de Culqi (https://api.culqi.com/v2). |
| restTemplate | RestTemplate | private | Cliente HTTP para realizar llamadas a la API de Culqi. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| processPayment(BigDecimal amount, String currency, String token, PaymentMethod method) | PaymentGatewayResponse | public | Envía solicitud POST /v2/charges a Culqi con amount (en céntimos: S/ 15.00 → 1500), currency_code ("PEN"), source_id (token de Culqi Checkout) y email del usuario. Parsea la respuesta y retorna PaymentGatewayResponse con transactionId, success y receiptUrl. Si Culqi retorna error, retorna success=false con errorDetail. |

---

### 4.2.3.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presentan los diagramas de nivel componente que ilustran la arquitectura de software del contexto de Payment Processing. Se muestra la interacción entre los componentes internos y la integración con la pasarela de pagos Culqi.

> **Diagrama a crear en Structurizr DSL:**


### 4.2.3.6. Bounded Context Software Architecture Code Level Diagrams

En esta sección se presentan los diagramas de nivel código que detallan la estructura interna del contexto de Payment Processing.

#### 4.2.3.6.1. Bounded Context Domain Layer Class Diagrams

El diagrama de clases del Domain Layer del contexto de Payment Processing ilustra las entidades, objetos de valor y servicios que componen este bounded context.

> **Diagrama a crear en LucidChart o PlantUML:**


#### 4.2.3.6.2. Bounded Context Database Design Diagram

El diagrama de diseño de base de datos del contexto de Payment Processing muestra la estructura de las tablas y sus relaciones.

> **Diagrama a crear en Vertabelo:**

## 4.2.4. Bounded Context: Emergency & Safety

Este bounded context gestiona la detección de condiciones peligrosas (fuga de gas, humo) mediante sensores MQ-2 y la activación automática de protocolos de emergencia. Cuando se detecta una condición peligrosa, el sistema abre todas las barreras, cambia todos los LEDs a modo evacuación y notifica a administradores y conductores. Es un bounded context Supporting que, cuando se activa, sobrescribe el comportamiento normal de los bounded contexts Core (Access Control y Parking Monitoring).

### 4.2.4.1. Domain Layer

En esta sección se describen los elementos del Domain Layer del contexto de Emergency & Safety, que encapsulan la lógica central relacionada con la detección de emergencias y la activación de protocolos de evacuación.

#### 1. EmergencyAlert (Aggregate Root)

Representa una alerta de emergencia detectada por los sensores de gas/humo del estacionamiento. Tiene su propio ciclo de vida: TRIGGERED → ACTIVE → RESOLVED.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único de la alerta. |
| sensorId | EmergencySensorId | private | Identificador del sensor MQ-2 que disparó la alerta. |
| gasLevel | int | private | Nivel de gas detectado en PPM (partes por millón). |
| type | EmergencyType | private | Tipo de emergencia (GAS o SMOKE). |
| status | EmergencyStatus | private | Estado actual de la alerta (ACTIVE o RESOLVED). |
| triggeredAt | LocalDateTime | private | Fecha y hora en que se disparó la alerta. |
| resolvedAt | LocalDateTime | private | Fecha y hora de resolución (null mientras está activa). |
| resolvedBy | Long | private | ID del administrador que resolvió la emergencia (null mientras está activa). |
| sensorLocation | String | private | Ubicación física del sensor dentro del estacionamiento (e.g., "Nivel B2, Zona A"). |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| EmergencyAlert() | Constructor | protected | Constructor protegido para JPA. |
| EmergencyAlert(TriggerEmergencyAlertCommand command) | Constructor | public | Crea una alerta a partir de un comando. Inicializa con status=ACTIVE, resolvedAt=null, resolvedBy=null. Publica EmergencyAlertTriggeredEvent. |
| resolve(Long adminUserId) | void | public | Marca la emergencia como RESOLVED, registra resolvedAt y resolvedBy. Lanza excepción si ya está resuelta. Publica EmergencyResolvedEvent. |
| isActive() | boolean | public | Devuelve true si status es ACTIVE. |
| isResolved() | boolean | public | Devuelve true si status es RESOLVED. |
| exceedsThreshold() | boolean | public | Devuelve true si gasLevel supera el umbral de peligro (900 PPM por defecto). |

#### 2. TriggerEmergencyAlertCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sensorId | String | public | ID del sensor MQ-2 que detectó la condición peligrosa. |
| gasLevel | int | public | Nivel de gas en PPM. |
| type | String | public | Tipo de emergencia ("GAS" o "SMOKE"). |
| sensorLocation | String | public | Ubicación del sensor en el estacionamiento. |

#### 3. ResolveEmergencyCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| emergencyId | Long | public | ID de la alerta a resolver. |
| adminUserId | Long | public | ID del administrador que resuelve la emergencia. |

#### 4. ActivateEvacuationCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| emergencyId | Long | public | ID de la emergencia que justifica la evacuación. |

#### 5. Queries

| Query | Atributos principales | Descripción |
|---|---|---|
| GetEmergencyStatusQuery | (sin atributos) | Obtiene el estado actual de emergencia del estacionamiento (NORMAL o detalle de emergencia activa). |
| GetEmergencyByIdQuery | emergencyId : Long | Obtiene una alerta específica por su ID. |
| GetActiveEmergenciesQuery | (sin atributos) | Obtiene todas las emergencias activas. |
| GetEmergencyHistoryQuery | startDate : LocalDate, endDate : LocalDate | Obtiene historial de emergencias en un rango de fechas. |

#### 6. EmergencyAlertTriggeredEvent (Domain Event)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| emergencyId | Long | private | ID de la alerta creada. |
| type | EmergencyType | private | Tipo de emergencia (GAS o SMOKE). |
| gasLevel | int | private | Nivel de gas detectado. |
| sensorLocation | String | private | Ubicación del sensor. |
| triggeredAt | LocalDateTime | private | Momento de la detección. |

#### 7. EmergencyResolvedEvent (Domain Event)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| emergencyId | Long | private | ID de la alerta resuelta. |
| resolvedAt | LocalDateTime | private | Momento de la resolución. |
| resolvedBy | Long | private | ID del administrador que resolvió. |

#### 8. EmergencyCommandService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(TriggerEmergencyAlertCommand command) | Optional\<EmergencyAlert> | public | Crea una alerta de emergencia y activa el protocolo de evacuación. Valida que el gasLevel supere el umbral de 900 PPM. |
| handle(ResolveEmergencyCommand command) | void | public | Resuelve una emergencia activa y restaura la operación normal del estacionamiento. |
| handle(ActivateEvacuationCommand command) | void | public | Activa manualmente el protocolo de evacuación (requiere emergencia activa). |

#### 9. EmergencyQueryService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetEmergencyStatusQuery query) | EmergencyStatusResponse | public | Retorna el estado actual: si hay emergencia activa retorna sus detalles, si no retorna status "NORMAL". |
| handle(GetEmergencyByIdQuery query) | Optional\<EmergencyAlert> | public | Obtiene una alerta por su ID. |
| handle(GetActiveEmergenciesQuery query) | List\<EmergencyAlert> | public | Obtiene todas las emergencias activas (normalmente 0 o 1). |
| handle(GetEmergencyHistoryQuery query) | List\<EmergencyAlert> | public | Obtiene historial de emergencias en un rango de fechas. |

#### 10. EmergencyThresholdService (Domain Service)

Servicio de dominio que encapsula la lógica de evaluación de umbrales de peligro.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| isGasLevelDangerous(int gasPPM) | boolean | public | Evalúa si el nivel de gas supera el umbral de peligro (900 PPM configurable). |
| isDangerousCondition(int gasPPM, EmergencyType type) | boolean | public | Evalúa según el tipo de emergencia si la condición es peligrosa. |
| getGasThreshold() | int | public | Retorna el umbral actual de gas en PPM (configurable). |

#### 11. EmergencyType (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| GAS | Enum | public | Emergencia por fuga de gas. |
| SMOKE | Enum | public | Emergencia por detección de humo. |

#### 12. EmergencyStatus (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| ACTIVE | Enum | public | La emergencia está activa. |
| RESOLVED | Enum | public | La emergencia ha sido resuelta. |

#### 13. EmergencySensorId (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| sensorId | String | private | Identificador del sensor MQ-2 (e.g., "MQ2-B2-A01"). |

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| EmergencySensorId() | Constructor | public | Constructor requerido por JPA. |
| EmergencySensorId(String sensorId) | Constructor | public | Inicializa y valida que no sea vacío. |

#### 14. EmergencyStatusResponse (Value Object)

Respuesta que encapsula el estado actual de emergencia del estacionamiento.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| isEmergencyActive | boolean | private | Indica si hay una emergencia activa. |
| emergencyId | Long | private | ID de la emergencia activa (null si no hay). |
| type | EmergencyType | private | Tipo de emergencia (null si no hay). |
| gasLevel | int | private | Nivel de gas (0 si no hay emergencia). |
| sensorLocation | String | private | Ubicación del sensor (null si no hay). |
| triggeredAt | LocalDateTime | private | Momento de la detección (null si no hay). |
| overallStatus | String | private | "NORMAL" o "EMERGENCY". |

---

### 4.2.4.2. Interface Layer

#### 1. EmergencyController (REST Controller)

Controlador REST que expone endpoints para gestionar alertas de emergencia.

| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| triggerAlert | /api/v1/emergency/alerts | POST | Registra una nueva alerta de emergencia disparada por el sensor MQ-2 (llamado desde el edge server). |
| getEmergencyStatus | /api/v1/emergency/status | GET | Consulta el estado actual de emergencia del estacionamiento. |
| activateEvacuation | /api/v1/emergency/evacuate | POST | Activa manualmente el protocolo de evacuación (solo admin). |
| resolveEmergency | /api/v1/emergencies/{id}/resolve | PATCH | Marca una emergencia como resuelta y restaura operación normal (solo admin). |
| getEmergencyById | /api/v1/emergencies/{id} | GET | Obtiene detalles de una alerta específica. |
| getEmergencyHistory | /api/v1/emergencies/history | GET | Obtiene historial de emergencias con filtros de fecha. |

#### 2. Resources (DTOs)

| Resource | Atributos principales | Descripción |
|---|---|---|
| TriggerAlertResource | sensorId: String, gasLevel: int, type: String, sensorLocation: String | Datos de la alerta recibida del edge server. |
| EmergencyAlertResource | id: Long, sensorId: String, gasLevel: int, type: String, status: String, triggeredAt: LocalDateTime, resolvedAt: LocalDateTime, resolvedBy: Long, sensorLocation: String | Representación completa de una alerta. |
| EmergencyStatusResource | isEmergencyActive: boolean, emergencyId: Long, type: String, gasLevel: int, sensorLocation: String, triggeredAt: LocalDateTime, overallStatus: String | Estado actual de emergencia del estacionamiento. |
| ResolveEmergencyResource | adminUserId: Long | Datos para resolver una emergencia. |

#### 3. Transform (Assemblers)

| Assembler | Entrada | Salida | Descripción |
|---|---|---|---|
| EmergencyAlertResourceFromEntityAssembler | EmergencyAlert | EmergencyAlertResource | Convierte entidad a DTO de respuesta. |
| TriggerEmergencyAlertCommandFromResourceAssembler | TriggerAlertResource | TriggerEmergencyAlertCommand | Convierte DTO del edge server en comando. |
| ResolveEmergencyCommandFromResourceAssembler | ResolveEmergencyResource, Long id | ResolveEmergencyCommand | Convierte DTO de resolución en comando. |
| EmergencyStatusResourceFromResponseAssembler | EmergencyStatusResponse | EmergencyStatusResource | Convierte response del dominio a DTO. |

---

### 4.2.4.3. Application Layer

#### 1. EmergencyCommandServiceImpl (Command Service Implementation)

Implementación del servicio de comandos para gestionar alertas de emergencia.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| emergencyAlertRepository | EmergencyAlertRepository | private | Repositorio para persistencia de alertas. |
| emergencyThresholdService | EmergencyThresholdService | private | Servicio de evaluación de umbrales de peligro. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(TriggerEmergencyAlertCommand command) | Optional\<EmergencyAlert> | public | Procesa alerta: (1) evalúa umbral con EmergencyThresholdService, (2) si es peligroso crea EmergencyAlert, (3) persiste y publica EmergencyAlertTriggeredEvent. Si gasLevel no supera umbral, retorna empty sin crear alerta. |
| handle(ResolveEmergencyCommand command) | void | public | Resuelve emergencia: (1) busca alerta activa, (2) marca como RESOLVED con adminUserId, (3) persiste y publica EmergencyResolvedEvent. Lanza 404 si no existe o 409 si ya está resuelta. |
| handle(ActivateEvacuationCommand command) | void | public | Activa evacuación manual: verifica que exista emergencia activa (409 si no existe), luego publica evento de evacuación. |

#### 2. EmergencyQueryServiceImpl (Query Service Implementation)

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| emergencyAlertRepository | EmergencyAlertRepository | private | Repositorio para acceso de lectura. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetEmergencyStatusQuery query) | EmergencyStatusResponse | public | Busca emergencias activas. Si existe al menos una, retorna detalles con overallStatus="EMERGENCY". Si no hay, retorna overallStatus="NORMAL". |
| handle(GetEmergencyByIdQuery query) | Optional\<EmergencyAlert> | public | Obtiene alerta por ID. |
| handle(GetActiveEmergenciesQuery query) | List\<EmergencyAlert> | public | Obtiene todas las emergencias con status ACTIVE. |
| handle(GetEmergencyHistoryQuery query) | List\<EmergencyAlert> | public | Obtiene alertas en un rango de fechas, ordenadas por triggeredAt descendente. |

#### 3. EmergencyAlertTriggeredEventHandler (Domain Event Handler)

Maneja el evento de alerta disparada para activar el protocolo de emergencia en otros bounded contexts.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| externalAccessControlService | ExternalAccessControlService | private | Servicio ACL para abrir todas las barreras. |
| externalParkingMonitoringService | ExternalParkingMonitoringService | private | Servicio ACL para cambiar LEDs a modo evacuación. |
| externalNotificationService | ExternalNotificationService | private | Servicio ACL para enviar notificaciones masivas. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| on(EmergencyAlertTriggeredEvent event) | void | public | Ejecuta el protocolo de emergencia en paralelo: (1) envía comando a Access Control para abrir TODAS las barreras, (2) envía comando a Parking Monitoring para cambiar TODOS los LEDs a rojo intermitente (evacuación), (3) envía notificación push a TODOS los conductores con sesión activa via Notification BC, (4) envía alerta al dashboard del administrador. |

#### 4. EmergencyResolvedEventHandler (Domain Event Handler)

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| externalAccessControlService | ExternalAccessControlService | private | Servicio ACL para restaurar barreras. |
| externalParkingMonitoringService | ExternalParkingMonitoringService | private | Servicio ACL para restaurar LEDs. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| on(EmergencyResolvedEvent event) | void | public | Restaura operación normal: (1) notifica a Access Control para restaurar control normal de barreras, (2) notifica a Parking Monitoring para restaurar LEDs según estado actual de sensores. |

#### 5. ExternalAccessControlService (Outbound ACL Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| openAllBarriers(String reason) | void | public | Envía comando a Access Control BC para abrir todas las barreras del estacionamiento. |
| restoreBarrierControl() | void | public | Notifica a Access Control que restaure el control normal de barreras. |

#### 6. ExternalParkingMonitoringService (Outbound ACL Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| setAllLedsToEvacuationMode() | void | public | Envía comando a Parking Monitoring para cambiar todos los LEDs a rojo intermitente. |
| restoreLedsToNormalMode() | void | public | Notifica a Parking Monitoring que restaure los LEDs según el estado actual de los sensores. |

#### 7. ExternalNotificationService (Outbound ACL Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| broadcastEmergencyAlert(String message, String sensorLocation) | void | public | Envía notificación push a TODOS los conductores con sesión activa alertando sobre la emergencia. Ignora preferencias de notificación del usuario (regla de negocio: alertas de emergencia siempre se envían). |
| sendAdminEmergencyAlert(String message, String sensorLocation, int gasLevel) | void | public | Envía alerta al dashboard del administrador con detalles de la emergencia. |

---

### 4.2.4.4. Infrastructure Layer

#### 1. EmergencyAlertRepository (Repository Interface)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<EmergencyAlert> | public | Busca una alerta por su ID. |
| save(EmergencyAlert alert) | EmergencyAlert | public | Persiste o actualiza una alerta. |
| findByStatus(EmergencyStatus status) | List\<EmergencyAlert> | public | Obtiene alertas por estado (ACTIVE o RESOLVED). |
| findByTriggeredAtBetween(LocalDateTime start, LocalDateTime end) | List\<EmergencyAlert> | public | Obtiene alertas en un rango de fechas. |
| existsByStatus(EmergencyStatus status) | boolean | public | Verifica si existe alguna emergencia con el estado indicado. |
| findFirstByStatusOrderByTriggeredAtDesc(EmergencyStatus status) | Optional\<EmergencyAlert> | public | Obtiene la emergencia activa más reciente. |

---

### 4.2.4.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presentan los diagramas de nivel componente que ilustran la arquitectura de software del contexto de Emergency & Safety. Se muestra la interacción entre los componentes internos y la comunicación con los bounded contexts que deben reaccionar ante una emergencia.

> **Diagrama a crear en Structurizr DSL:**


### 4.2.4.6. Bounded Context Software Architecture Code Level Diagrams

En esta sección se presentan los diagramas de nivel código que detallan la estructura interna del contexto de Emergency & Safety.

#### 4.2.4.6.1. Bounded Context Domain Layer Class Diagrams

El diagrama de clases del Domain Layer del contexto de Emergency & Safety ilustra las entidades, objetos de valor y servicios que componen este bounded context.

> **Diagrama a crear en LucidChart o PlantUML:**


#### 4.2.4.6.2. Bounded Context Database Design Diagram

El diagrama de diseño de base de datos del contexto de Emergency & Safety muestra la estructura de las tablas y sus relaciones.

> **Diagrama a crear en Vertabelo:**

## 4.2.5. Bounded Context: Analytics & Reporting

Este bounded context gestiona la generación de métricas, estadísticas y reportes para la toma de decisiones administrativas. Consume datos de otros bounded contexts (Parking Monitoring, Access Control, Payment Processing) para calcular tasas de ocupación, rotación, horas punta, ingresos y mapas de calor. Es un bounded context Supporting de naturaleza predominantemente de lectura, ya que no modifica datos de otros contexts sino que los agrega y transforma en información accionable.

### 4.2.5.1. Domain Layer

En esta sección se describen los elementos del Domain Layer del contexto de Analytics & Reporting, que encapsulan la lógica relacionada con el cálculo de métricas y la generación de reportes.

#### 1. Report (Aggregate Root)

Representa un reporte generado por el sistema, que puede ser descargado en formato PDF por el administrador.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único del reporte. |
| reportType | ReportType | private | Tipo de reporte (OCCUPANCY, REVENUE, COMBINED). |
| reportPeriod | ReportPeriod | private | Período cubierto por el reporte (fecha inicio y fin). |
| generatedAt | LocalDateTime | private | Fecha y hora de generación del reporte. |
| generatedBy | Long | private | ID del administrador que generó el reporte. |
| fileUrl | String | private | URL del archivo PDF generado. |
| status | ReportStatus | private | Estado del reporte (GENERATING, COMPLETED, FAILED). |
| facilityId | Long | private | ID del estacionamiento al que pertenece el reporte. |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| Report() | Constructor | protected | Constructor protegido para JPA. |
| Report(GenerateReportCommand command) | Constructor | public | Crea un reporte a partir de un comando. Inicializa con status=GENERATING, fileUrl=null. |
| markAsCompleted(String fileUrl) | void | public | Marca el reporte como completado y asigna la URL del archivo PDF generado. |
| markAsFailed(String errorDetail) | void | public | Marca el reporte como fallido. |
| isCompleted() | boolean | public | Devuelve true si status es COMPLETED. |

#### 2. GenerateReportCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| reportType | String | public | Tipo de reporte ("OCCUPANCY", "REVENUE", "COMBINED"). |
| startDate | LocalDate | public | Fecha de inicio del período. |
| endDate | LocalDate | public | Fecha de fin del período. |
| generatedBy | Long | public | ID del administrador que solicita el reporte. |
| facilityId | Long | public | ID del estacionamiento. |

#### 3. Queries

| Query | Atributos principales | Descripción |
|---|---|---|
| GetOccupancyMetricsQuery | startDate : LocalDate, endDate : LocalDate, facilityId : Long | Obtiene métricas de ocupación para un rango de fechas. |
| GetRevenueMetricsQuery | startDate : LocalDate, endDate : LocalDate, facilityId : Long | Obtiene métricas de ingresos para un rango de fechas. |
| GetHeatmapDataQuery | startDate : LocalDate, endDate : LocalDate, facilityId : Long | Obtiene datos para el mapa de calor de uso por espacio. |
| GetPeakHoursQuery | startDate : LocalDate, endDate : LocalDate, facilityId : Long | Obtiene las horas punta del estacionamiento. |
| GetReportByIdQuery | reportId : Long | Obtiene un reporte específico por su ID. |
| GetReportsByFacilityQuery | facilityId : Long | Obtiene todos los reportes de un estacionamiento. |

#### 4. ReportGeneratedEvent (Domain Event)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| reportId | Long | private | ID del reporte generado. |
| reportType | ReportType | private | Tipo de reporte. |
| fileUrl | String | private | URL del PDF generado. |
| generatedBy | Long | private | ID del administrador. |

#### 5. AnalyticsQueryService (Domain Service)

Proporciona métodos para consultar métricas calculadas a partir de datos de otros bounded contexts.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetOccupancyMetricsQuery query) | OccupancyMetrics | public | Calcula y retorna métricas de ocupación: tasa promedio, horas punta, tasa de rotación, datos por hora. |
| handle(GetRevenueMetricsQuery query) | RevenueMetrics | public | Calcula y retorna métricas de ingresos: total, ticket promedio, pagos por método, datos por día. |
| handle(GetHeatmapDataQuery query) | List\<HeatmapEntry> | public | Calcula datos del mapa de calor: uso por espacio (cuántas veces fue ocupado y duración promedio). |
| handle(GetPeakHoursQuery query) | PeakHoursData | public | Identifica las horas con mayor ocupación promedio. |

#### 6. ReportCommandService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GenerateReportCommand command) | Optional\<Report> | public | Inicia la generación de un reporte PDF. Crea entidad Report, genera el PDF y lo almacena, actualiza status a COMPLETED. |

#### 7. ReportQueryService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetReportByIdQuery query) | Optional\<Report> | public | Obtiene un reporte por su ID. |
| handle(GetReportsByFacilityQuery query) | List\<Report> | public | Obtiene todos los reportes de un estacionamiento. |

#### 8. OccupancyAnalyticsService (Domain Service)

Servicio de dominio que encapsula la lógica de cálculo de métricas de ocupación.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| calculateAverageOccupancyRate(List\<SlotStatusSnapshot> snapshots) | double | public | Calcula la tasa de ocupación promedio a partir de snapshots históricos. |
| calculateTurnoverRate(long totalSessions, long totalSlots, int days) | double | public | Calcula la tasa de rotación: sesiones / (espacios × días). |
| identifyPeakHours(List\<SlotStatusSnapshot> snapshots) | List\<Integer> | public | Identifica las horas del día con mayor ocupación promedio. |

#### 9. RevenueAnalyticsService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| calculateTotalRevenue(List\<PaymentSummary> payments) | BigDecimal | public | Suma el monto total de pagos en el período. |
| calculateAverageTicket(List\<PaymentSummary> payments) | BigDecimal | public | Calcula el ticket promedio (total / cantidad de pagos). |
| groupByPaymentMethod(List\<PaymentSummary> payments) | Map\<String, BigDecimal> | public | Agrupa ingresos por método de pago (YAPE, CREDIT_CARD, DEBIT_CARD). |
| groupByDay(List\<PaymentSummary> payments) | Map\<LocalDate, BigDecimal> | public | Agrupa ingresos por día. |

#### 10. OccupancyMetrics (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| averageOccupancyRate | double | private | Tasa de ocupación promedio en porcentaje (0-100). |
| peakHours | List\<Integer> | private | Horas del día con mayor ocupación (e.g., [12, 13, 18, 19]). |
| turnoverRate | double | private | Tasa de rotación (sesiones por espacio por día). |
| dataByHour | Map\<Integer, Double> | private | Ocupación promedio desglosada por hora del día (0-23). |
| totalSlots | int | private | Total de espacios en el estacionamiento. |
| periodStart | LocalDate | private | Inicio del período analizado. |
| periodEnd | LocalDate | private | Fin del período analizado. |

#### 11. RevenueMetrics (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| totalRevenue | BigDecimal | private | Ingresos totales en el período. |
| averageTicket | BigDecimal | private | Ticket promedio por sesión. |
| totalTransactions | int | private | Cantidad total de transacciones. |
| paymentsByMethod | Map\<String, BigDecimal> | private | Ingresos desglosados por método de pago. |
| dataByDay | Map\<LocalDate, BigDecimal> | private | Ingresos desglosados por día. |
| currency | String | private | Moneda (PEN). |

#### 12. HeatmapEntry (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| slotId | Long | private | ID del espacio. |
| slotCode | String | private | Código del espacio (e.g., "A-15"). |
| usageCount | int | private | Cantidad de veces que fue ocupado en el período. |
| averageDurationMinutes | double | private | Duración promedio de ocupación en minutos. |
| totalOccupiedMinutes | long | private | Tiempo total que estuvo ocupado en minutos. |

#### 13. PeakHoursData (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| peakHours | List\<Integer> | private | Horas con mayor ocupación (e.g., [12, 13, 18, 19, 20]). |
| occupancyByHour | Map\<Integer, Double> | private | Porcentaje de ocupación promedio por hora (0-23). |
| busiestDay | String | private | Día de la semana con mayor ocupación promedio. |

#### 14. SlotStatusSnapshot (Value Object)

Snapshot del estado de un espacio en un momento dado (usado para cálculos históricos).

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| slotId | Long | private | ID del espacio. |
| status | String | private | Estado en ese momento (AVAILABLE, OCCUPIED). |
| timestamp | LocalDateTime | private | Momento del snapshot. |

#### 15. PaymentSummary (Value Object)

Resumen de un pago (proyección de datos del BC Payment Processing).

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| paymentId | Long | private | ID del pago. |
| amount | BigDecimal | private | Monto del pago. |
| paymentMethod | String | private | Método de pago utilizado. |
| paidAt | LocalDateTime | private | Momento del pago. |

#### 16. ReportType (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| OCCUPANCY | Enum | public | Reporte de ocupación. |
| REVENUE | Enum | public | Reporte de ingresos. |
| COMBINED | Enum | public | Reporte combinado (ocupación + ingresos). |

#### 17. ReportStatus (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| GENERATING | Enum | public | El reporte se está generando. |
| COMPLETED | Enum | public | El reporte se generó exitosamente. |
| FAILED | Enum | public | La generación del reporte falló. |

#### 18. ReportPeriod (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| startDate | LocalDate | private | Fecha de inicio del período. |
| endDate | LocalDate | private | Fecha de fin del período. |

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| ReportPeriod(LocalDate start, LocalDate end) | Constructor | public | Inicializa y valida que startDate sea anterior a endDate. |
| getDurationInDays() | long | public | Retorna la cantidad de días del período. |
| includes(LocalDate date) | boolean | public | Verifica si una fecha está dentro del período. |

---

### 4.2.5.2. Interface Layer

#### 1. AnalyticsController (REST Controller)

Controlador REST que expone endpoints para consultar métricas y estadísticas del estacionamiento.

| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| getOccupancyMetrics | /api/v1/analytics/occupancy | GET | Obtiene métricas de ocupación (tasa promedio, rotación, horas punta). Parámetros: startDate, endDate. |
| getRevenueMetrics | /api/v1/analytics/revenue | GET | Obtiene métricas de ingresos (total, ticket promedio, por método). Parámetros: startDate, endDate. |
| getHeatmapData | /api/v1/analytics/heatmap | GET | Obtiene datos del mapa de calor de uso por espacio. Parámetros: startDate, endDate. |
| getPeakHours | /api/v1/analytics/peak-hours | GET | Obtiene las horas punta del estacionamiento. Parámetros: startDate, endDate. |

#### 2. ReportsController (REST Controller)

Controlador REST que expone endpoints para generar y consultar reportes.

| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| generateReport | /api/v1/reports | POST | Genera un nuevo reporte PDF de ocupación o ingresos. |
| getReportById | /api/v1/reports/{id} | GET | Obtiene un reporte específico por su ID. |
| getReportsByFacility | /api/v1/reports | GET | Obtiene todos los reportes del estacionamiento. |
| downloadReport | /api/v1/reports/{id}/download | GET | Descarga el archivo PDF del reporte. |

#### 3. Resources (DTOs)

| Resource | Atributos principales | Descripción |
|---|---|---|
| OccupancyMetricsResource | averageOccupancyRate: double, peakHours: List\<Integer>, turnoverRate: double, dataByHour: Map\<Integer, Double>, totalSlots: int, periodStart: String, periodEnd: String | Métricas de ocupación formateadas. |
| RevenueMetricsResource | totalRevenue: BigDecimal, averageTicket: BigDecimal, totalTransactions: int, paymentsByMethod: Map\<String, BigDecimal>, dataByDay: Map\<String, BigDecimal>, currency: String | Métricas de ingresos formateadas. |
| HeatmapEntryResource | slotId: Long, slotCode: String, usageCount: int, averageDurationMinutes: double | Entrada del mapa de calor. |
| PeakHoursResource | peakHours: List\<Integer>, occupancyByHour: Map\<Integer, Double>, busiestDay: String | Datos de horas punta. |
| ReportResource | id: Long, reportType: String, periodStart: String, periodEnd: String, generatedAt: LocalDateTime, status: String, fileUrl: String | Representación de un reporte. |
| GenerateReportResource | reportType: String, startDate: String, endDate: String | Datos para solicitar generación de reporte. |

#### 4. Transform (Assemblers)

| Assembler | Entrada | Salida | Descripción |
|---|---|---|---|
| OccupancyMetricsResourceFromValueObjectAssembler | OccupancyMetrics | OccupancyMetricsResource | Convierte VO a DTO. |
| RevenueMetricsResourceFromValueObjectAssembler | RevenueMetrics | RevenueMetricsResource | Convierte VO a DTO. |
| HeatmapEntryResourceFromValueObjectAssembler | HeatmapEntry | HeatmapEntryResource | Convierte VO a DTO. |
| ReportResourceFromEntityAssembler | Report | ReportResource | Convierte entidad a DTO. |
| GenerateReportCommandFromResourceAssembler | GenerateReportResource | GenerateReportCommand | Convierte DTO en comando. |

---

### 4.2.5.3. Application Layer

#### 1. AnalyticsQueryServiceImpl (Query Service Implementation)

Implementación del servicio de consultas que calcula métricas agregando datos de otros bounded contexts.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| occupancyAnalyticsService | OccupancyAnalyticsService | private | Servicio de cálculo de métricas de ocupación. |
| revenueAnalyticsService | RevenueAnalyticsService | private | Servicio de cálculo de métricas de ingresos. |
| externalParkingDataService | ExternalParkingDataService | private | Servicio ACL para obtener datos de Parking Monitoring BC. |
| externalPaymentDataService | ExternalPaymentDataService | private | Servicio ACL para obtener datos de Payment Processing BC. |
| externalSessionDataService | ExternalSessionDataService | private | Servicio ACL para obtener datos de Access Control BC. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetOccupancyMetricsQuery query) | OccupancyMetrics | public | Obtiene snapshots de estado de espacios via ACL, calcula ocupación promedio, rotación y horas punta usando OccupancyAnalyticsService. |
| handle(GetRevenueMetricsQuery query) | RevenueMetrics | public | Obtiene datos de pagos via ACL, calcula total, ticket promedio y agrupaciones usando RevenueAnalyticsService. |
| handle(GetHeatmapDataQuery query) | List\<HeatmapEntry> | public | Obtiene datos de sesiones por espacio via ACL, calcula frecuencia de uso y duración promedio por slot. |
| handle(GetPeakHoursQuery query) | PeakHoursData | public | Obtiene snapshots de ocupación por hora via ACL, identifica las horas con mayor demanda. |

#### 2. ReportCommandServiceImpl (Command Service Implementation)

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| reportRepository | ReportRepository | private | Repositorio para persistencia de reportes. |
| analyticsQueryService | AnalyticsQueryService | private | Servicio de consulta de métricas (para incluir en el PDF). |
| pdfGenerationService | PdfGenerationService | private | Servicio de generación de archivos PDF. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GenerateReportCommand command) | Optional\<Report> | public | Genera reporte: (1) crea entidad Report con status GENERATING, (2) obtiene métricas via AnalyticsQueryService, (3) genera PDF via PdfGenerationService, (4) almacena archivo y actualiza fileUrl, (5) marca como COMPLETED. Si falla, marca como FAILED. |

#### 3. ReportQueryServiceImpl (Query Service Implementation)

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| reportRepository | ReportRepository | private | Repositorio para acceso de lectura. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetReportByIdQuery query) | Optional\<Report> | public | Obtiene un reporte por su ID. |
| handle(GetReportsByFacilityQuery query) | List\<Report> | public | Obtiene todos los reportes del estacionamiento, ordenados por generatedAt descendente. |

#### 4. ExternalParkingDataService (Outbound ACL Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| getSlotStatusSnapshots(LocalDate start, LocalDate end, Long facilityId) | List\<SlotStatusSnapshot> | public | Obtiene snapshots históricos de estados de espacios desde Parking Monitoring BC. |
| getTotalSlots(Long facilityId) | int | public | Obtiene el total de espacios del estacionamiento. |

#### 5. ExternalPaymentDataService (Outbound ACL Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| getPaymentSummaries(LocalDate start, LocalDate end) | List\<PaymentSummary> | public | Obtiene resúmenes de pagos completados desde Payment Processing BC. |

#### 6. ExternalSessionDataService (Outbound ACL Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| getCompletedSessionCount(LocalDate start, LocalDate end) | long | public | Obtiene cantidad de sesiones completadas desde Access Control BC. |
| getSessionsBySlot(LocalDate start, LocalDate end) | Map\<Long, List\<SessionSummary>> | public | Obtiene sesiones agrupadas por slotId para cálculo de heatmap. |

#### 7. PdfGenerationService (Outbound Service Port)

Interfaz para la generación de archivos PDF. La implementación concreta vive en Infrastructure.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| generateOccupancyReport(OccupancyMetrics metrics, ReportPeriod period) | byte[] | public | Genera PDF de reporte de ocupación con tablas y gráficos. |
| generateRevenueReport(RevenueMetrics metrics, ReportPeriod period) | byte[] | public | Genera PDF de reporte de ingresos. |
| generateCombinedReport(OccupancyMetrics occ, RevenueMetrics rev, ReportPeriod period) | byte[] | public | Genera PDF de reporte combinado. |

---

### 4.2.5.4. Infrastructure Layer

#### 1. ReportRepository (Repository Interface)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<Report> | public | Busca un reporte por su ID. |
| save(Report report) | Report | public | Persiste o actualiza un reporte. |
| findByFacilityIdOrderByGeneratedAtDesc(Long facilityId) | List\<Report> | public | Obtiene reportes de un estacionamiento ordenados por fecha. |
| findByReportTypeAndFacilityId(ReportType type, Long facilityId) | List\<Report> | public | Obtiene reportes por tipo. |

#### 2. PdfGenerationServiceImpl (Infrastructure Service)

Implementación concreta del servicio de generación de PDF usando iText o Apache PDFBox.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| fileStoragePath | String | private | Ruta de almacenamiento de archivos PDF generados. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| generateOccupancyReport(OccupancyMetrics metrics, ReportPeriod period) | byte[] | public | Genera PDF con tablas de ocupación por hora, gráfico de barras de horas punta y resumen ejecutivo. |
| generateRevenueReport(RevenueMetrics metrics, ReportPeriod period) | byte[] | public | Genera PDF con tabla de ingresos por día, gráfico de ingresos por método de pago y totales. |
| generateCombinedReport(OccupancyMetrics occ, RevenueMetrics rev, ReportPeriod period) | byte[] | public | Genera PDF combinado con ambas secciones. |

#### 3. SlotStatusSnapshotRepository (Repository Interface)

Repositorio para acceder a los snapshots históricos de estado de espacios (datos que se almacenan periódicamente desde Parking Monitoring para análisis histórico).

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findByTimestampBetween(LocalDateTime start, LocalDateTime end) | List\<SlotStatusSnapshot> | public | Obtiene snapshots en un rango de tiempo. |
| findBySlotIdAndTimestampBetween(Long slotId, LocalDateTime start, LocalDateTime end) | List\<SlotStatusSnapshot> | public | Obtiene snapshots de un espacio específico. |

---

### 4.2.5.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presentan los diagramas de nivel componente que ilustran la arquitectura de software del contexto de Analytics & Reporting.

> **Diagrama a crear en Structurizr DSL:**


### 4.2.5.6. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.5.6.1. Bounded Context Domain Layer Class Diagrams

> **Diagrama a crear en LucidChart o PlantUML:**
#### 4.2.5.6.2. Bounded Context Database Design Diagram

> **Diagrama a crear en Vertabelo:**

## 4.2.6. Bounded Context: Notification Management

Este bounded context gestiona el envío de notificaciones push, alertas in-app y la administración de preferencias de notificación por usuario. Recibe solicitudes de envío desde otros bounded contexts (Access Control, Payment Processing, Emergency & Safety) y las procesa a través de Firebase Cloud Messaging (FCM). Administra templates de mensajes, el registro histórico de notificaciones enviadas con su estado (enviada/leída) y respeta las preferencias de cada usuario, con la excepción de las alertas de emergencia que siempre se envían.

### 4.2.6.1. Domain Layer

En esta sección se describen los elementos del Domain Layer del contexto de Notification Management, que encapsulan la lógica central relacionada con el envío, almacenamiento y gestión de notificaciones.

#### 1. Notification (Aggregate Root)

Representa una notificación enviada a un usuario del sistema. Tiene su propio ciclo de vida: PENDING → SENT → DELIVERED → READ (o FAILED).

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único de la notificación. |
| userId | NotificationUserId | private | Identificador del usuario destinatario. |
| type | NotificationType | private | Tipo de notificación (ENTRY_CONFIRMED, PAYMENT_REMINDER, PAYMENT_SUCCESS, EMERGENCY_ALERT, SESSION_END). |
| title | String | private | Título de la notificación mostrado al usuario. |
| body | String | private | Contenido del mensaje de la notificación. |
| data | String | private | Datos adicionales en formato JSON (e.g., sessionId, amount, slotCode). |
| status | NotificationStatus | private | Estado actual de la notificación (PENDING, SENT, DELIVERED, READ, FAILED). |
| channel | NotificationChannel | private | Canal de envío utilizado (PUSH, IN_APP). |
| createdAt | LocalDateTime | private | Fecha y hora de creación de la notificación. |
| sentAt | LocalDateTime | private | Fecha y hora de envío (null si aún no se envió). |
| readAt | LocalDateTime | private | Fecha y hora en que el usuario la leyó (null si no leída). |
| errorDetail | String | private | Detalle del error si el envío falló (null si exitoso). |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| Notification() | Constructor | protected | Constructor protegido para JPA. |
| Notification(SendNotificationCommand command) | Constructor | public | Crea una notificación a partir de un comando. Inicializa con status=PENDING, sentAt=null, readAt=null. |
| markAsSent() | void | public | Cambia status a SENT y registra sentAt. |
| markAsDelivered() | void | public | Cambia status a DELIVERED. |
| markAsRead() | void | public | Cambia status a READ y registra readAt. Lanza excepción si ya fue leída. |
| markAsFailed(String errorDetail) | void | public | Cambia status a FAILED y registra el detalle del error. |
| isRead() | boolean | public | Devuelve true si status es READ. |
| isPending() | boolean | public | Devuelve true si status es PENDING. |

#### 2. NotificationPreference (Entity)

Representa la preferencia de un usuario sobre un tipo específico de notificación (si desea recibirla o no).

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único de la preferencia. |
| userId | NotificationUserId | private | Identificador del usuario. |
| notificationType | NotificationType | private | Tipo de notificación al que aplica la preferencia. |
| enabled | boolean | private | Indica si el usuario desea recibir este tipo de notificación. |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| NotificationPreference() | Constructor | protected | Constructor protegido para JPA. |
| NotificationPreference(Long userId, NotificationType type, boolean enabled) | Constructor | public | Crea una preferencia con valores iniciales. |
| enable() | void | public | Habilita la recepción de este tipo de notificación. |
| disable() | void | public | Deshabilita la recepción de este tipo de notificación. |
| isEnabled() | boolean | public | Devuelve el estado actual de la preferencia. |

#### 3. NotificationTemplate (Entity)

Representa una plantilla predefinida de mensaje para cada tipo de notificación, con placeholders que se resuelven con datos del evento.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único de la plantilla. |
| type | NotificationType | private | Tipo de notificación al que corresponde la plantilla. |
| titleTemplate | String | private | Plantilla del título (e.g., "Ingreso confirmado"). |
| bodyTemplate | String | private | Plantilla del cuerpo con placeholders (e.g., "Tu vehículo {{licensePlate}} ingresó a las {{entryTime}}"). |
| language | String | private | Idioma de la plantilla (es_PE por defecto). |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| NotificationTemplate() | Constructor | protected | Constructor protegido para JPA. |
| resolveTitle(Map\<String, String> data) | String | public | Resuelve los placeholders del título con los datos proporcionados. |
| resolveBody(Map\<String, String> data) | String | public | Resuelve los placeholders del cuerpo con los datos proporcionados. |

#### 4. SendNotificationCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| userId | Long | public | ID del usuario destinatario. |
| type | String | public | Tipo de notificación ("ENTRY_CONFIRMED", "PAYMENT_REMINDER", etc.). |
| title | String | public | Título de la notificación (puede ser null si se usa template). |
| body | String | public | Cuerpo del mensaje (puede ser null si se usa template). |
| data | Map\<String, String> | public | Datos adicionales para resolver template y enviar como payload. |

#### 5. BroadcastNotificationCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| type | String | public | Tipo de notificación (típicamente "EMERGENCY_ALERT"). |
| title | String | public | Título del mensaje. |
| body | String | public | Cuerpo del mensaje. |
| data | Map\<String, String> | public | Datos adicionales (sensorLocation, gasLevel). |
| recipientUserIds | List\<Long> | public | Lista de IDs de usuarios destinatarios. |

#### 6. MarkNotificationAsReadCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| notificationId | Long | public | ID de la notificación a marcar como leída. |

#### 7. UpdatePreferencesCommand (Command)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| userId | Long | public | ID del usuario. |
| preferences | Map\<String, Boolean> | public | Mapa de tipo → habilitado (e.g., {"ENTRY_CONFIRMED": true, "PAYMENT_REMINDER": false}). |

#### 8. Queries

| Query | Atributos principales | Descripción |
|---|---|---|
| GetNotificationsByUserQuery | userId : Long | Obtiene todas las notificaciones de un usuario. |
| GetUnreadNotificationsQuery | userId : Long | Obtiene solo las notificaciones no leídas de un usuario. |
| GetNotificationByIdQuery | notificationId : Long | Obtiene una notificación específica. |
| GetPreferencesByUserQuery | userId : Long | Obtiene las preferencias de notificación del usuario. |

#### 9. NotificationSentEvent (Domain Event)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| source | Object | private | Objeto origen del evento. |
| notificationId | Long | private | ID de la notificación enviada. |
| userId | Long | private | ID del usuario destinatario. |
| type | NotificationType | private | Tipo de notificación. |
| channel | NotificationChannel | private | Canal utilizado (PUSH, IN_APP). |
| sentAt | LocalDateTime | private | Momento del envío. |

#### 10. NotificationCommandService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(SendNotificationCommand command) | Optional\<Notification> | public | Envía una notificación individual a un usuario. Verifica preferencias antes de enviar (excepto EMERGENCY_ALERT que siempre se envía). |
| handle(BroadcastNotificationCommand command) | List\<Notification> | public | Envía notificaciones masivas a múltiples usuarios (usado para emergencias). |
| handle(MarkNotificationAsReadCommand command) | void | public | Marca una notificación como leída. |
| handle(UpdatePreferencesCommand command) | void | public | Actualiza las preferencias de notificación del usuario. |

#### 11. NotificationQueryService (Domain Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetNotificationsByUserQuery query) | List\<Notification> | public | Obtiene todas las notificaciones del usuario, ordenadas por createdAt descendente. |
| handle(GetUnreadNotificationsQuery query) | List\<Notification> | public | Obtiene solo notificaciones no leídas (status != READ). |
| handle(GetNotificationByIdQuery query) | Optional\<Notification> | public | Obtiene una notificación por ID. |
| handle(GetPreferencesByUserQuery query) | List\<NotificationPreference> | public | Obtiene las preferencias del usuario. |

#### 12. PreferenceValidationService (Domain Service)

Servicio de dominio que encapsula la lógica de validación de preferencias antes del envío.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| shouldSendNotification(Long userId, NotificationType type, List\<NotificationPreference> preferences) | boolean | public | Evalúa si una notificación debe enviarse. Retorna true siempre para EMERGENCY_ALERT (ignora preferencias). Para otros tipos, verifica si el usuario tiene la preferencia habilitada. Si no tiene preferencia configurada, retorna true por defecto. |
| isEmergencyType(NotificationType type) | boolean | public | Devuelve true si el tipo es EMERGENCY_ALERT. |

#### 13. TemplateResolverService (Domain Service)

Servicio de dominio que resuelve los templates de notificación con datos concretos.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| resolveTemplate(NotificationType type, Map\<String, String> data) | ResolvedNotification | public | Busca el template para el tipo dado, resuelve los placeholders con los datos proporcionados y retorna título y cuerpo resueltos. |

#### 14. NotificationType (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| ENTRY_CONFIRMED | Enum | public | Confirmación de ingreso del vehículo al estacionamiento. |
| PAYMENT_REMINDER | Enum | public | Recordatorio de pago pendiente (enviado cuando el conductor llega a la salida sin pagar). |
| PAYMENT_SUCCESS | Enum | public | Confirmación de pago exitoso. |
| EMERGENCY_ALERT | Enum | public | Alerta de emergencia (gas/humo). Ignora preferencias del usuario. |
| SESSION_END | Enum | public | Notificación de fin de sesión (vehículo salió del estacionamiento). |
| PAYMENT_FAILED | Enum | public | Notificación de pago fallido. |

#### 15. NotificationStatus (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| PENDING | Enum | public | La notificación está pendiente de envío. |
| SENT | Enum | public | La notificación fue enviada a FCM. |
| DELIVERED | Enum | public | La notificación fue entregada al dispositivo. |
| READ | Enum | public | El usuario leyó la notificación. |
| FAILED | Enum | public | El envío de la notificación falló. |

#### 16. NotificationChannel (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| PUSH | Enum | public | Notificación push via Firebase Cloud Messaging. |
| IN_APP | Enum | public | Notificación almacenada solo en la app (cuando no hay token FCM). |

#### 17. NotificationUserId (Value Object)

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| userId | Long | private | ID del usuario destinatario; debe ser > 0. |

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| NotificationUserId() | Constructor | public | Constructor requerido por JPA. |
| NotificationUserId(Long userId) | Constructor | public | Inicializa y valida que userId > 0. |

#### 18. ResolvedNotification (Value Object)

Resultado de resolver un template con datos concretos.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| title | String | private | Título resuelto de la notificación. |
| body | String | private | Cuerpo resuelto del mensaje. |

#### 19. PushMessagingService (Domain Service Interface)

Interfaz del servicio de mensajería push. La implementación concreta vive en Infrastructure Layer.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| sendPushNotification(String fcmToken, String title, String body, Map\<String, String> data) | boolean | public | Envía una notificación push individual via FCM. Retorna true si fue exitoso. |
| sendBulkPushNotifications(List\<String> fcmTokens, String title, String body, Map\<String, String> data) | int | public | Envía notificaciones push masivas. Retorna la cantidad de envíos exitosos. |

#### 20. FcmTokenService (Domain Service Interface)

Interfaz para obtener los tokens FCM de los usuarios. La implementación consulta al BC IAM.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| getFcmToken(Long userId) | Optional\<String> | public | Obtiene el token FCM registrado para un usuario. |
| getFcmTokens(List\<Long> userIds) | Map\<Long, String> | public | Obtiene los tokens FCM de múltiples usuarios. |

---

### 4.2.6.2. Interface Layer

#### 1. NotificationsController (REST Controller)

Controlador REST que expone endpoints para gestionar notificaciones y preferencias.

| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| sendNotification | /api/v1/notifications | POST | Envía una notificación a un usuario específico. |
| getNotificationsByUser | /api/v1/notifications/user/{userId} | GET | Obtiene todas las notificaciones de un usuario. |
| getUnreadNotifications | /api/v1/notifications/user/{userId}/unread | GET | Obtiene solo las notificaciones no leídas. |
| markAsRead | /api/v1/notifications/{id}/read | PATCH | Marca una notificación como leída. |
| getPreferences | /api/v1/users/{userId}/notification-preferences | GET | Obtiene las preferencias de notificación del usuario. |
| updatePreferences | /api/v1/users/{userId}/notification-preferences | PUT | Actualiza las preferencias de notificación del usuario. |

#### 2. Resources (DTOs)

| Resource | Atributos principales | Descripción |
|---|---|---|
| SendNotificationResource | userId: Long, type: String, title: String, body: String, data: Map\<String, String> | Datos para enviar una notificación. |
| NotificationResource | id: Long, userId: Long, type: String, title: String, body: String, status: String, channel: String, createdAt: LocalDateTime, readAt: LocalDateTime | Representación de una notificación. |
| NotificationPreferenceResource | notificationType: String, enabled: boolean | Preferencia individual de un tipo de notificación. |
| UpdatePreferencesResource | preferences: List\<NotificationPreferenceResource> | Lista de preferencias a actualizar. |
| UnreadCountResource | userId: Long, unreadCount: int | Cantidad de notificaciones no leídas. |

#### 3. Transform (Assemblers)

| Assembler | Entrada | Salida | Descripción |
|---|---|---|---|
| NotificationResourceFromEntityAssembler | Notification | NotificationResource | Convierte entidad a DTO. |
| SendNotificationCommandFromResourceAssembler | SendNotificationResource | SendNotificationCommand | Convierte DTO en comando. |
| NotificationPreferenceResourceFromEntityAssembler | NotificationPreference | NotificationPreferenceResource | Convierte entidad de preferencia a DTO. |
| UpdatePreferencesCommandFromResourceAssembler | UpdatePreferencesResource, Long userId | UpdatePreferencesCommand | Convierte DTO de preferencias en comando. |

---

### 4.2.6.3. Application Layer

#### 1. NotificationCommandServiceImpl (Command Service Implementation)

Implementación del servicio de comandos para gestionar notificaciones.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| notificationRepository | NotificationRepository | private | Repositorio para persistencia de notificaciones. |
| preferenceRepository | NotificationPreferenceRepository | private | Repositorio para persistencia de preferencias. |
| templateRepository | NotificationTemplateRepository | private | Repositorio para acceso a templates. |
| pushMessagingService | PushMessagingService | private | Servicio de envío push (FCM). |
| fcmTokenService | FcmTokenService | private | Servicio para obtener tokens FCM. |
| preferenceValidationService | PreferenceValidationService | private | Servicio de validación de preferencias. |
| templateResolverService | TemplateResolverService | private | Servicio de resolución de templates. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(SendNotificationCommand command) | Optional\<Notification> | public | Proceso completo de envío: (1) verifica preferencias del usuario con PreferenceValidationService (EMERGENCY_ALERT ignora preferencias), (2) si título/body son null, resuelve template con TemplateResolverService, (3) obtiene token FCM del usuario, (4) si tiene token envía via PushMessagingService y marca como SENT, si no tiene token almacena como IN_APP, (5) persiste y publica NotificationSentEvent. Si envío falla, marca como FAILED con errorDetail. |
| handle(BroadcastNotificationCommand command) | List\<Notification> | public | Envío masivo: (1) obtiene tokens FCM de todos los recipientUserIds, (2) envía bulk push via PushMessagingService, (3) crea una entidad Notification por cada usuario, (4) persiste todas. No verifica preferencias para EMERGENCY_ALERT. |
| handle(MarkNotificationAsReadCommand command) | void | public | Busca notificación, marca como READ con readAt. Lanza 404 si no existe. |
| handle(UpdatePreferencesCommand command) | void | public | Para cada entrada en el mapa de preferencias: si existe la preferencia la actualiza, si no existe la crea. No permite deshabilitar EMERGENCY_ALERT (siempre se ignora). |

#### 2. NotificationQueryServiceImpl (Query Service Implementation)

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| notificationRepository | NotificationRepository | private | Repositorio para acceso de lectura de notificaciones. |
| preferenceRepository | NotificationPreferenceRepository | private | Repositorio para acceso de lectura de preferencias. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetNotificationsByUserQuery query) | List\<Notification> | public | Obtiene todas las notificaciones del usuario, ordenadas por createdAt descendente. |
| handle(GetUnreadNotificationsQuery query) | List\<Notification> | public | Obtiene notificaciones con status distinto de READ, ordenadas por createdAt descendente. |
| handle(GetNotificationByIdQuery query) | Optional\<Notification> | public | Obtiene una notificación por su ID. |
| handle(GetPreferencesByUserQuery query) | List\<NotificationPreference> | public | Obtiene todas las preferencias del usuario. Si el usuario no tiene preferencias configuradas, retorna defaults (todas habilitadas). |

#### 3. DefaultPreferencesInitializer (Application Service)

Servicio que inicializa las preferencias por defecto cuando un usuario nuevo se registra.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| initializeDefaultPreferences(Long userId) | void | public | Crea una entrada de NotificationPreference por cada NotificationType con enabled=true para el nuevo usuario. |

---

### 4.2.6.4. Infrastructure Layer

#### 1. NotificationRepository (Repository Interface)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<Notification> | public | Busca una notificación por su ID. |
| save(Notification notification) | Notification | public | Persiste o actualiza una notificación. |
| saveAll(List\<Notification> notifications) | List\<Notification> | public | Persiste múltiples notificaciones (broadcast). |
| findByUserId_UserIdOrderByCreatedAtDesc(Long userId) | List\<Notification> | public | Obtiene notificaciones del usuario ordenadas por fecha. |
| findByUserId_UserIdAndStatusNot(Long userId, NotificationStatus status) | List\<Notification> | public | Obtiene notificaciones no leídas del usuario. |
| countByUserId_UserIdAndStatusNot(Long userId, NotificationStatus status) | int | public | Cuenta notificaciones no leídas. |

#### 2. NotificationPreferenceRepository (Repository Interface)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findByUserId_UserId(Long userId) | List\<NotificationPreference> | public | Obtiene todas las preferencias del usuario. |
| findByUserId_UserIdAndNotificationType(Long userId, NotificationType type) | Optional\<NotificationPreference> | public | Obtiene una preferencia específica. |
| save(NotificationPreference preference) | NotificationPreference | public | Persiste o actualiza una preferencia. |
| existsByUserId_UserId(Long userId) | boolean | public | Verifica si el usuario tiene preferencias configuradas. |

#### 3. NotificationTemplateRepository (Repository Interface)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findByType(NotificationType type) | Optional\<NotificationTemplate> | public | Obtiene el template para un tipo de notificación. |
| findByTypeAndLanguage(NotificationType type, String language) | Optional\<NotificationTemplate> | public | Obtiene template por tipo e idioma. |

#### 4. FirebaseMessagingClient (Infrastructure Service)

Implementación concreta del servicio de mensajería push usando Firebase Cloud Messaging.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| firebaseMessaging | FirebaseMessaging | private | Instancia del cliente de Firebase Admin SDK para envío de mensajes. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| sendPushNotification(String fcmToken, String title, String body, Map\<String, String> data) | boolean | public | Construye un Message de Firebase con notification (title, body) y data payload, lo envía al token FCM indicado. Retorna true si Firebase responde con éxito, false si falla. |
| sendBulkPushNotifications(List\<String> fcmTokens, String title, String body, Map\<String, String> data) | int | public | Construye un MulticastMessage de Firebase con los tokens y lo envía en batch. Retorna la cantidad de envíos exitosos. |

#### 5. IamFcmTokenClient (Infrastructure Service)

Implementación de FcmTokenService que consulta al BC IAM para obtener tokens FCM.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| getFcmToken(Long userId) | Optional\<String> | public | Consulta al BC IAM via REST el token FCM registrado para el usuario. |
| getFcmTokens(List\<Long> userIds) | Map\<Long, String> | public | Consulta en batch los tokens FCM de múltiples usuarios. |

---

### 4.2.6.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presentan los diagramas de nivel componente que ilustran la arquitectura de software del contexto de Notification Management.

> **Diagrama a crear en Structurizr DSL:**


### 4.2.6.6. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.6.6.1. Bounded Context Domain Layer Class Diagrams

> **Diagrama a crear en LucidChart o PlantUML:**


#### 4.2.6.6.2. Bounded Context Database Design Diagram

> **Diagrama a crear en Vertabelo:**

## 4.2.7. Bounded Context: Identity & Access Management

Este bounded context gestiona la identidad y los accesos de todos los usuarios del sistema. Provee registro y autenticación de usuarios mediante JWT, gestión de contraseñas, asignación de roles (ADMIN, CAR_OWNER) y gestión de perfiles. Es un bounded context Generic ya que la autenticación no es específica del dominio de estacionamiento y podría resolverse con soluciones estándar, pero se implementa de forma personalizada para adaptarse a los requisitos específicos de SpotFinder (registro con placa vehicular, roles de conductor y administrador). Este bounded context ya se encuentra implementado en el código del proyecto.

### 4.2.7.1. Domain Layer

En esta sección se describen los elementos del Domain Layer del contexto de IAM, que encapsulan las reglas y lógica del dominio relacionadas con la gestión de identidades y accesos.

#### 1. User (Aggregate Root)

Representa al usuario del sistema con sus credenciales, estado y roles asignados. Es la entidad central del bounded context.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único del usuario (autogenerado). |
| email | String | private | Correo electrónico del usuario (único en el sistema). |
| passwordHash | String | private | Contraseña hasheada con BCrypt. |
| firstName | String | private | Nombre del usuario. |
| lastName | String | private | Apellido del usuario. |
| isVerified | boolean | private | Indica si el usuario ha verificado su cuenta por email. |
| active | Boolean | private | Indica si la cuenta está activa (true por defecto). |
| roles | List\<Role> | private | Lista de roles asignados al usuario (relación ManyToMany). |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| User() | Constructor | protected | Constructor protegido para JPA. Inicializa roles como lista vacía. |
| User(String email, String passwordHash, String firstName, String lastName, boolean isVerified) | Constructor | public | Crea un usuario con sus datos de autenticación. Inicializa roles vacíos y active=true. |
| addRole(Role role) | void | public | Agrega un rol al usuario si no lo tiene ya asignado. Valida que role no sea null. |
| getFullName() | String | public | Retorna el nombre completo formateado como "firstName lastName". |

#### 2. Role (Entity)

Define un rol específico que puede ser asignado a un usuario dentro del sistema.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| id | Long | private | Identificador único del rol (autogenerado). |
| name | Roles | private | Nombre del rol como enum (ADMIN, CAR_OWNER). Almacenado como String en BD. |

**Métodos principales:**

| Método | Tipo Retorno | Visibilidad | Descripción |
|---|---|---|---|
| Role() | Constructor | protected | Constructor vacío para JPA. |
| Role(Roles name) | Constructor | public | Inicializa rol con el enum correspondiente. |
| from(String name) | Role (static) | public | Crea un Role a partir del nombre en String, convirtiendo a mayúsculas. |

#### 3. SignUpCommand (Command)

Comando para registrar un nuevo usuario en el sistema.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| email | String | public | Correo electrónico del usuario. No puede ser vacío. |
| password | String | public | Contraseña en texto plano (se hashea en el servicio). No puede ser vacía. |
| firstName | String | public | Nombre del usuario. No puede ser vacío. |
| lastName | String | public | Apellido del usuario. No puede ser vacío. |
| requestedRole | Roles | public | Rol solicitado (ADMIN o CAR_OWNER). No puede ser null. |

> Validaciones en el constructor del record: lanza BadRequestException si algún campo es vacío o null.

#### 4. SignInCommand (Command)

Comando para autenticar un usuario con sus credenciales.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| email | String | public | Correo de acceso. No puede ser vacío. |
| password | String | public | Contraseña provista por el usuario. No puede ser vacía. |

#### 5. Queries

| Query | Atributos principales | Descripción |
|---|---|---|
| GetUserByEmailQuery | email : String | Obtiene un usuario por su correo electrónico. |
| GetAllUsersQuery | (sin atributos) | Obtiene todos los usuarios registrados en el sistema. |

#### 6. UserCommandService (Domain Service)

Maneja comandos relacionados con la gestión de usuarios.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(SignUpCommand command) | void | public | Registra un nuevo usuario: valida que el email no exista, hashea la contraseña, asigna rol y persiste. |
| handle(SignInCommand command) | void | public | Autentica: verifica credenciales, valida que la cuenta esté activa. |

#### 7. UserQueryService (Domain Service)

Maneja consultas relacionadas con usuarios.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetUserByEmailQuery query) | Optional\<User> | public | Obtiene un usuario por su email. |
| handle(GetAllUsersQuery query) | List\<User> | public | Obtiene la lista completa de usuarios. |

#### 8. RoleValidationService (Domain Service)

Servicio de dominio que valida operaciones relacionadas con roles.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| canRequestRole(Roles role) | boolean | public | Valida si un rol puede ser solicitado durante el registro. Retorna true si el rol no es null. |
| getAvailableRolesForRegistration() | Roles[] | public | Retorna todos los roles disponibles para el registro. |

#### 9. Roles (Value Object)

Enumera los distintos roles disponibles en el sistema.

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| ADMIN | Enum | public | Rol de administrador de estacionamiento. Acceso al dashboard web con métricas, gestión de espacios y emergencias. |
| CAR_OWNER | Enum | public | Rol de conductor/propietario de vehículo. Acceso a la app móvil con mapa, pagos, Find My Car y notificaciones. |

> **Nota:** El código actual solo tiene ADMIN. Se debe agregar CAR_OWNER para representar al conductor.

#### 10. Domain Exceptions

| Exception | Extiende | Descripción |
|---|---|---|
| InvalidCredentialsException | UnauthorizedException | Credenciales de email o contraseña incorrectas. Retorna 401. |
| UserAlreadyExistsException | ConflictException | El email ya está registrado en el sistema. Retorna 409. |
| UserNotFoundException | NotFoundException | No se encontró un usuario con el email o ID indicado. Retorna 404. |
| UserAccountDeactivatedException | BusinessRuleException | La cuenta del usuario está desactivada. Retorna 422. |
| RoleNotFoundException | NotFoundException | El rol solicitado no existe en la base de datos. Retorna 404. |

---

### 4.2.7.2. Interface Layer

#### 1. UsersController (REST Controller)

Controlador REST que expone endpoints para registro, autenticación y gestión de usuarios.

| Nombre del método | Ruta base típica | Método HTTP | Descripción |
|---|---|---|---|
| signUp | /api/v1/users/signup | POST | Registra un nuevo usuario. Recibe email, password, firstName, lastName y requestedRole. Retorna 201 Created si exitoso, 409 Conflict si el email ya existe. |
| signIn | /api/v1/users/signin | POST | Autentica un usuario. Retorna JWT token, tipo "Bearer", expiración y datos del usuario. Retorna 401 si credenciales inválidas, 403 si cuenta desactivada. |
| getUserByEmail | /api/v1/users/by-email | GET | Obtiene un usuario por su email (requiere autenticación). |
| getAllUsers | /api/v1/users | GET | Obtiene la lista de todos los usuarios (requiere autenticación). |
| getAvailableRoles | /api/v1/users/available-roles | GET | Obtiene los roles disponibles para registro (endpoint público). |

#### 2. Resources (DTOs)

| Resource | Atributos principales | Descripción |
|---|---|---|
| SignUpResource | email: String (@NotBlank, @Email), password: String (@NotBlank, @Size min=8), firstName: String (@NotBlank, @Size 2-50), lastName: String (@NotBlank, @Size 2-50), requestedRole: Roles (@NotNull) | Datos de registro con validaciones de Bean Validation. |
| SignInResource | email: String, password: String | Credenciales para inicio de sesión. |
| AuthenticationResponseResource | token: String, tokenType: String ("Bearer"), expiresIn: Long (604800 segundos = 7 días), user: UserResource | Respuesta de autenticación exitosa con JWT. |
| UserResource | id: Long, email: String, firstName: String, lastName: String, isVerified: boolean, active: boolean, roles: List\<String>, createdAt: LocalDateTime, updatedAt: LocalDateTime | Representación del usuario sin datos sensibles (sin passwordHash). |

#### 3. Transform (Assemblers)

| Assembler | Entrada | Salida | Descripción |
|---|---|---|---|
| SignUpCommandFromResourceAssembler | SignUpResource | SignUpCommand | Convierte DTO de registro en comando de dominio. |
| SignInCommandFromResourceAssembler | SignInResource | SignInCommand | Convierte DTO de login en comando de dominio. |
| UserResourceFromEntityAssembler | User | UserResource | Convierte entidad User a DTO de respuesta. Mapea roles a lista de strings con nombre del enum. No expone passwordHash. |
| AuthenticationResponseResource.of() | String token, Long expiresIn, UserResource user | AuthenticationResponseResource | Factory method estático que crea la respuesta de autenticación con tokenType="Bearer". |

---

### 4.2.7.3. Application Layer

#### 1. UserCommandServiceImpl (Command Service Implementation)

Implementación del servicio de comandos para registro y autenticación de usuarios.

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| userRepository | UserRepository | private | Repositorio para persistencia de usuarios. |
| roleRepository | RoleRepository | private | Repositorio para acceso a roles. |
| hashingService | HashingService | private | Servicio de hashing de contraseñas (BCrypt). |
| tokenService | TokenService | private | Servicio de generación y validación de JWT. |
| roleValidationService | RoleValidationService | private | Servicio de validación de roles. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(SignUpCommand command) | void | public | Proceso de registro: (1) verifica que el email no exista (UserAlreadyExistsException si existe), (2) valida que el rol pueda ser solicitado, (3) hashea la contraseña con BCrypt, (4) crea entidad User, (5) busca el rol en BD y lo asigna, (6) persiste el usuario. |
| handle(SignInCommand command) | void | public | Proceso de autenticación: (1) busca usuario por email (InvalidCredentialsException si no existe), (2) verifica que la cuenta esté activa (UserAccountDeactivatedException si no), (3) compara contraseña con hash (InvalidCredentialsException si no coincide). |
| generateTokenForUser(User user) | String | public | Genera JWT token para un usuario autenticado. Extrae el rol principal del usuario y lo incluye como claim en el token. |

#### 2. UserQueryServiceImpl (Query Service Implementation)

**Atributos principales:**

| Atributo | Tipo | Visibilidad | Descripción |
|---|---|---|---|
| userRepository | UserRepository | private | Repositorio para acceso de lectura. |

**Métodos principales:**

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handle(GetUserByEmailQuery query) | Optional\<User> | public | Busca un usuario por su email en el repositorio. |
| handle(GetAllUsersQuery query) | List\<User> | public | Obtiene la lista completa de usuarios registrados. |

#### 3. RoleValidationServiceImpl (Application Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| canRequestRole(Roles role) | boolean | public | Valida que el rol no sea null. En el futuro puede extenderse con reglas más complejas. |
| getAvailableRolesForRegistration() | Roles[] | public | Retorna Roles.values() (todos los roles disponibles). |

#### 4. ApplicationReadyEventHandler (Framework Event Handler)

Maneja el evento de inicio de la aplicación para sembrar roles por defecto.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| handleApplicationReady(ApplicationReadyEvent event) | void | public | Al arrancar la aplicación, verifica si cada rol del enum Roles existe en la BD. Si no existe, lo crea y persiste. Esto asegura que ADMIN y CAR_OWNER siempre existan. |

#### 5. HashingService (Outbound Service Port)

Interfaz para hashing de contraseñas.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| encode(CharSequence rawPassword) | String | public | Genera hash BCrypt de la contraseña. |
| matches(CharSequence rawPassword, String encodedPassword) | boolean | public | Verifica si la contraseña cruda coincide con el hash almacenado. |

#### 6. TokenService (Outbound Service Port)

Interfaz para generación y validación de tokens JWT.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| generateToken(Long userId, String userRole) | String | public | Genera un JWT con userId como subject y userRole como claim. Expira en 7 días (configurable). |
| getUserIdFromToken(String token) | Long | public | Extrae el userId del subject del token. |
| validateToken(String token) | boolean | public | Valida la firma, estructura y fecha de expiración del token. |

---

### 4.2.7.4. Infrastructure Layer

#### 1. UserRepository (Repository Interface)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findById(Long id) | Optional\<User> | public | Busca un usuario por su ID. |
| findByEmail(String email) | Optional\<User> | public | Busca un usuario por su correo electrónico. |
| existsByEmail(String email) | boolean | public | Verifica si existe un usuario con el email indicado. |
| save(User user) | User | public | Persiste o actualiza un usuario. |
| findAll() | List\<User> | public | Obtiene todos los usuarios. |

#### 2. RoleRepository (Repository Interface)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| findByName(Roles name) | Optional\<Role> | public | Busca un rol por su nombre (enum). |
| existsByName(Roles name) | boolean | public | Verifica si un rol existe por su nombre. |
| save(Role role) | Role | public | Persiste o actualiza un rol. |

#### 3. WebSecurityConfiguration (Security Config)

Configuración de Spring Security para la API.

| Configuración | Descripción |
|---|---|
| CORS | Permite orígenes de http://localhost:4200 (Angular dashboard). Métodos: GET, POST, PUT, DELETE, PATCH, OPTIONS. |
| CSRF | Deshabilitado (API stateless con JWT). |
| Session Management | STATELESS (sin sesiones HTTP, todo via JWT). |
| Public Endpoints | /api/v1/users/signup, /api/v1/users/signin, /api/v1/users/available-roles, /swagger-ui/**, /v3/api-docs/** |
| Protected Endpoints | Todos los demás requieren JWT válido en header Authorization: Bearer {token}. |
| Authentication Filter | BearerAuthorizationRequestFilter se ejecuta antes de UsernamePasswordAuthenticationFilter. |
| Password Encoder | BCryptPasswordEncoder via BCryptHashingService. |

#### 4. BearerAuthorizationRequestFilter (Security Filter)

Filtro que intercepta todas las peticiones HTTP para validar el JWT.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| doFilterInternal(request, response, chain) | void | protected | Para cada request: (1) si es OPTIONS o endpoint público, permite sin validar. (2) Extrae token del header Authorization. (3) Si tiene token y es válido, extrae userId, carga UserDetails, establece autenticación en SecurityContext. (4) Continúa la cadena de filtros. |

#### 5. TokenServiceImpl (JWT Service)

Implementación de TokenService usando la biblioteca JJWT.

| Configuración | Valor |
|---|---|
| Algoritmo | HMAC-SHA (HS256) |
| Secret | Configurado en application.properties (authorization.jwt.secret) |
| Expiración | 7 días (authorization.jwt.expiration.days) |
| Claims | subject: userId (String), role: userRole (String) |

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| generateToken(Long userId, String userRole) | String | public | Genera JWT con subject=userId.toString(), claim "role"=userRole, issuedAt=now, expiration=now+7days. Firma con HMAC-SHA key. |
| getUserIdFromToken(String token) | Long | public | Parsea el token, extrae subject y lo convierte a Long. |
| validateToken(String token) | boolean | public | Verifica firma y expiración. Lanza JwtException si inválido. |
| getBearerTokenFrom(HttpServletRequest request) | String | public | Extrae el token del header Authorization quitando el prefijo "Bearer ". |

#### 6. HashingServiceImpl (BCrypt Service)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| encode(CharSequence rawPassword) | String | public | Genera hash BCrypt. |
| matches(CharSequence rawPassword, String encodedPassword) | boolean | public | Compara contraseña con hash BCrypt. |

#### 7. UserDetailsServiceImpl (Spring Security UserDetailsService)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| loadUserByUsername(String email) | UserDetails | public | Busca usuario por email y construye UserDetailsImpl con authorities basadas en roles (ROLE_ADMIN, ROLE_CAR_OWNER). |
| loadUserById(Long userId) | UserDetails | public | Busca usuario por ID (usado por el filtro JWT después de extraer userId del token). |

#### 8. UserDetailsImpl (Security Model)

Adaptador que convierte la entidad User a UserDetails de Spring Security.

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| build(User user) | UserDetailsImpl (static) | public | Construye desde entidad User: mapea roles a authorities con prefijo "ROLE_", establece enabled según active. |
| getAuthorities() | Collection\<GrantedAuthority> | public | Retorna las authorities del usuario. |
| getUsername() | String | public | Retorna el email como username. |
| isEnabled() | boolean | public | Retorna el estado active del usuario. |

#### 9. UnauthorizedRequestHandlerEntryPoint (Auth EntryPoint)

| Método | Tipo de Retorno | Visibilidad | Descripción |
|---|---|---|---|
| commence(request, response, authException) | void | public | Responde con 401 Unauthorized y un cuerpo JSON con status, error, message, path y timestamp. |

#### 10. OpenApiConfiguration (Swagger Config)

Configuración de la documentación OpenAPI/Swagger de la API.

| Configuración | Descripción |
|---|---|
| Security Scheme | Bearer JWT (tipo HTTP, scheme "bearer", formato "JWT"). |
| Info | Nombre, descripción y versión de la aplicación desde application.properties. |
| Endpoints Swagger UI | /swagger-ui.html, /swagger-ui/**, /v3/api-docs/** |

---

### 4.2.7.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presentan los diagramas de nivel componente que ilustran la arquitectura de software del contexto de IAM. Se muestra la interacción entre los diferentes componentes, servicios y capas que conforman este bounded context.

> **Diagrama a crear en Structurizr DSL:**



### 4.2.7.6. Bounded Context Software Architecture Code Level Diagrams

#### 4.2.7.6.1. Bounded Context Domain Layer Class Diagrams

El diagrama de clases del Domain Layer del contexto de IAM ilustra las entidades, value objects y servicios que componen este bounded context, reflejando el código ya implementado.

> **Diagrama a crear en LucidChart o PlantUML:**


#### 4.2.7.6.2. Bounded Context Database Design Diagram

El diagrama de diseño de base de datos del contexto de IAM muestra la estructura de las tablas y sus relaciones, generadas automáticamente por JPA/Hibernate a partir de las entidades del dominio.

> **Diagrama a crear en Vertabelo:**

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
