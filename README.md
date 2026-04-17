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

**IMAGEN**


**Paso 2 — Agrupación de eventos en torno al valor:**
Revisar los aggregates del Event Storming y sus eventos asociados. Agrupar por afinidad y preguntar: "¿Este grupo de eventos genera valor directo al negocio o es un soporte necesario?"

**IMAGEN**

**Paso 3 — Clasificación Core, Supporting, Generic:**
Ubicar cada bounded context en la matriz de dos ejes (Business Differentiation vs Model Complexity).

**IMAGEN**

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


**IMAGEN**


### Resultados
 
Se definieron **8 candidate bounded contexts**, de los cuales:
- **3 Core:** Parking Monitoring, Access Control, Payment Processing
- **4 Supporting:** Analytics & Reporting, Emergency & Safety, Reservation Management, Notification Management
- **1 Generic:** Identity & Access Management

La aplicación de la técnica Start-with-Value permitió asegurar que la atención principal del diseño táctico se concentre en **Parking Monitoring, Access Control y Payment Processing**, dado que allí reside la propuesta de valor diferenciadora de SpotFinder frente a competidores como Apparka, ParkHelp y Quadra.


**IMAGEN**


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
