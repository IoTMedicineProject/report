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
