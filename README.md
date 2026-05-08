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

---

<div style="page-break-after: always;">

# Contenido

- [COURSE PROJECT](#course-project)
- [Project Report Collaboration Insights](#project-report-collaboration-insights)
- [Contenido](#contenido)
- [Student Outcome](#student-outcome)
- [Capítulo I: Introducción](#capítulo-i-introducción)
  - [1.1. Startup Profile](#11-startup-profile)
    - [1.1.1. Descripción de la Startup](#111-descripción-de-la-startup)
    - [1.1.2. Perfiles de integrantes del equipo](#112-perfiles-de-integrantes-del-equipo)
  - [1.2. Solution Profile](#12-solution-profile)
    - [1.2.1 Antecedentes y problemática](#121-antecedentes-y-problemática)
    - [1.2.2 Lean UX Process.](#122-lean-ux-process)
      - [1.2.2.1. Lean UX Problem Statements.](#1221-lean-ux-problem-statements)
      - [1.2.2.2. Lean UX Assumptions.](#1222-lean-ux-assumptions)
      - [1.2.2.3. Lean UX Hypothesis Statements.](#1223-lean-ux-hypothesis-statements)
      - [1.2.2.4. Lean UX Canvas.](#1224-lean-ux-canvas)
  - [1.3. Segmentos objetivo.](#13-segmentos-objetivo)
- [Capítulo II: Requirements Elicitation \& Analysis](#capítulo-ii-requirements-elicitation--analysis)
  - [2.1. Competidores.](#21-competidores)
    - [2.1.1. Análisis competitivo.](#211-análisis-competitivo)
    - [2.1.2. Estrategias y tácticas frente a competidores.](#212-estrategias-y-tácticas-frente-a-competidores)
  - [2.2. Entrevistas.](#22-entrevistas)
    - [2.2.1. Diseño de entrevistas.](#221-diseño-de-entrevistas)
    - [2.2.2. Registro de entrevistas.](#222-registro-de-entrevistas)
    - [2.2.3. Análisis de entrevistas.](#223-análisis-de-entrevistas)
  - [2.3. Needfinding.](#23-needfinding)
    - [2.3.1. User Personas.](#231-user-personas)
    - [2.3.2. User Task Matrix.](#232-user-task-matrix)
    - [2.3.3. User Journey Mapping.](#233-user-journey-mapping)
    - [2.3.4. Empathy Mapping.](#234-empathy-mapping)
  - [2.4. Big Picture Event Storming.](#24-big-picture-event-storming)
  - [2.5. Ubiquitous Language.](#25-ubiquitous-language)
- [Capítulo III: Requirements Specification](#capítulo-iii-requirements-specification)
  - [3.1. User Stories.](#31-user-stories)
  - [3.2. Impact Mapping.](#32-impact-mapping)
  - [3.3. Product Backlog.](#33-product-backlog)
- [Capítulo IV: Product Design](#capítulo-iv-product-design)
  - [4.1. Style Guidelines.](#41-style-guidelines)
    - [4.1.1. General Style Guidelines.](#411-general-style-guidelines)
    - [4.1.2. Web Style Guidelines.](#412-web-style-guidelines)
  - [4.2. Information Architecture.](#42-information-architecture)
    - [4.2.1. Organization Systems.](#421-organization-systems)
    - [4.2.2. Labeling Systems.](#422-labeling-systems)
    - [4.2.3. SEO Tags and Meta Tags](#423-seo-tags-and-meta-tags)
    - [4.2.4. Searching Systems.](#424-searching-systems)
    - [4.2.5. Navigation Systems.](#425-navigation-systems)
  - [4.3. Landing Page UI Design.](#43-landing-page-ui-design)
    - [4.3.1. Landing Page Wireframe.](#431-landing-page-wireframe)
    - [4.3.2. Landing Page Mock-up.](#432-landing-page-mock-up)
  - [4.4. Web Applications UX/UI Design.](#44-web-applications-uxui-design)
    - [4.4.1. Web Applications Wireframes.](#441-web-applications-wireframes)
    - [4.4.2. Web Applications Wireflow Diagrams.](#442-web-applications-wireflow-diagrams)
    - [4.4.2. Web Applications Mock-ups.](#442-web-applications-mock-ups)
    - [4.4.3. Web Applications User Flow Diagrams.](#443-web-applications-user-flow-diagrams)
  - [4.5. Web Applications Prototyping.](#45-web-applications-prototyping)
  - [4.6. Domain-Driven Software Architecture.](#46-domain-driven-software-architecture)
    - [4.6.1. Design-Level Event Storming.](#461-design-level-event-storming)
    - [4.6.2. Software Architecture Context Diagram.](#462-software-architecture-context-diagram)
    - [4.6.3. Software Architecture Container Diagrams.](#463-software-architecture-container-diagrams)
    - [4.6.4. Software Architecture Components Diagrams.](#464-software-architecture-components-diagrams)
  - [4.7. Software Object-Oriented Design.](#47-software-object-oriented-design)
    - [4.7.1. Class Diagrams.](#471-class-diagrams)
  - [4.8. Database Design.](#48-database-design)
    - [4.8.1. Database Diagrams.](#481-database-diagrams)
- [Capítulo V: Product Implementation, Validation \& Deployment](#capítulo-v-product-implementation-validation--deployment)
  - [5.1. Software Configuration Management.](#51-software-configuration-management)
    - [5.1.1. Software Development Environment Configuration.](#511-software-development-environment-configuration)
    - [5.1.2. Source Code Management.](#512-source-code-management)
    - [5.1.3. Source Code Style Guide \& Conventions.](#513-source-code-style-guide--conventions)
    - [5.1.4. Software Deployment Configuration.](#514-software-deployment-configuration)
  - [5.2. Landing Page, Services \& Applications Implementation.](#52-landing-page-services--applications-implementation)
    - [5.2.X. Sprint n](#52x-sprint-n)
      - [5.2.X.1. Sprint Planning n.](#52x1-sprint-planning-n)
      - [5.2.X.2. Aspect Leaders and Collaborators.](#52x2-aspect-leaders-and-collaborators)
      - [5.2.X.3. Sprint Backlog n.](#52x3-sprint-backlog-n)
      - [5.2.X.4. Development Evidence for Sprint Review.](#52x4-development-evidence-for-sprint-review)
      - [5.2.X.5. Execution Evidence for Sprint Review.](#52x5-execution-evidence-for-sprint-review)
      - [5.2.X.6. Services Documentation Evidence for Sprint Review.](#52x6-services-documentation-evidence-for-sprint-review)
      - [5.2.X.7. Software Deployment Evidence for Sprint Review.](#52x7-software-deployment-evidence-for-sprint-review)
      - [5.2.X.8. Team Collaboration Insights during Sprint.](#52x8-team-collaboration-insights-during-sprint)
  - [5.3. Validation Interviews.](#53-validation-interviews)
    - [5.3.1. Diseño de Entrevistas.](#531-diseño-de-entrevistas)
    - [5.3.2. Registro de Entrevistas.](#532-registro-de-entrevistas)
    - [5.3.3. Evaluaciones según heurísticas.](#533-evaluaciones-según-heurísticas)
  - [5.4. Video About-the-Product.](#54-video-about-the-product)
- [Conclusiones](#conclusiones)
  - [Conclusiones y recomendaciones.](#conclusiones-y-recomendaciones)
  - [Video About-the-Team.](#video-about-the-team)
- [Bibliografía](#bibliografía)
- [Anexos](#anexos)
  
</div>

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

# Capítulo V: Solution UI/UX Design

## 5.1. Style Guidelines

En esta sección, se establecen los cimientos del **Design System** de SpotFinder. El objetivo es centralizar los *Design Tokens* (variables de diseño) y componentes UI en un repositorio de uso común, garantizando la consistencia visual y de interacción a través de un ecosistema multiplataforma (Web, Mobile y Hardware IoT). Esta estandarización reduce la fricción cognitiva del usuario, acelera el flujo de desarrollo en el frontend y asegura que las decisiones de diseño sean escalables y mantenibles a largo plazo, alineándose con los principios heurísticos de usabilidad y la metodología Lean UX.

### 5.1.1. General Style Guidelines

Esta subsección documenta las decisiones estructurales fundamentales: color, tipografía, espaciado y *UX Writing*. Las decisiones están sustentadas en la reducción de la carga cognitiva (*cognitive load*) del usuario, especialmente en contextos de alta demanda de atención (como la conducción vehicular).

**A. Branding y Paleta de Colores (Color Tokens)**
La identidad cromática se ha extraído estrictamente de los valores hexadecimales del imagotipo de SpotFinder. Se ha construido un sistema de colores accesible (cumpliendo con el ratio de contraste WCAG 2.1 AA/AAA) que guía la atención del usuario mediante jerarquía visual.

* **Brand Colors (Identidad Principal):**
    * **Action Blue (`#1A82FF`):** Color interactivo primario. Aplicado de forma exclusiva a elementos accionables de alta prioridad (*Primary Buttons*, *Floating Action Buttons*, *Active Tabs*) y enlaces. Representa la fiabilidad del flujo de software y guía al usuario hacia la conversión.
    * **Highlight Orange (`#FF9100`):** Color de acento (*Accent*). Reservado para focalizar la atención en micro-interacciones críticas o datos relevantes que rompen el patrón de lectura, como la ubicación exacta del vehículo en el módulo "Find My Car", notificaciones *push* de pago o *badges* de estado.
    * **Deep Black (`#000000`):** Color ancla y estructural. Empleado en tipografía de alto énfasis (*Headers*), bordes divisorios y como base absoluta para la superficie del *Dark Mode* de la aplicación móvil (evitando el deslumbramiento y la fatiga visual del conductor en entornos con baja iluminación como estacionamientos techados).
* **Semantic Colors (Feedback y Hardware):**
    * **Success/Available (`#10B981`):** Feedback positivo en la UI (pagos procesados, *snackbars* de éxito) e indicador IoT del LED en estado `AVAILABLE`.
    * **Error/Occupied (`#EF4444`):** Feedback de error en formularios, estados de emergencia y correlación directa con el indicador IoT del LED en estado `OCCUPIED`.

**B. Tipografía (Typographic Scale)**
Se ha definido un sistema tipográfico basado en la fuente **Inter**, optimizada para interfaces de usuario por su alta legibilidad (altura de la "x" pronunciada y kerning equilibrado) tanto en *displays* móviles como en paneles de datos (Web).
* **Display & Headings:** Uso en pesos *Bold* (700) y *SemiBold* (600) para lectura rápida de números de espacios, contadores de tiempo y títulos de sección.
* **Body & UI Text:** Peso *Regular* (400) para lectura prolongada y *Medium* (500) para etiquetas de botones. El tamaño base (*Body 1*) es de 16px (1rem) con un interlineado (*line-height*) del 150% para maximizar la legibilidad en pantallas de alto contraste.

**C. Spacing & Grid System**
Para asegurar una estructura armónica y modular, se implementa una **grilla espacial basada en 8pt** (*8-point grid system*).
* Márgenes y *paddings* operan en incrementos de 8 (8px, 16px, 24px, 32px), creando un ritmo visual predecible.
* Los iconos y elementos modulares se construyen en cajas delimitadas de 24x24px o 32x32px para mantener simetría a nivel de píxel (*pixel-perfect*).

**D. Tone of Communication y UX Writing**
El lenguaje (*microcopy*) de SpotFinder está diseñado bajo la premisa funcional:
* **Formal/Casual:** *Casual, directo y conciso.* (Ej. "Espacio A-12 libre" en lugar de "Le informamos que el espacio A-12 se encuentra disponible").
* **Entusiasta/Sereno:** *Estrictamente Sereno y de Control.* El sistema debe mitigar la ansiedad inherente a la búsqueda de estacionamiento y el procesamiento de pagos, ofreciendo instrucciones unívocas, mensajes de error constructivos y retroalimentación clara de los estados del sistema.


### 5.1.2. Web, Mobile and IoT Style Guidelines

Aquí se detalla la aplicación del sistema de diseño en los diferentes puntos de contacto (*touchpoints*) del usuario, adaptando los patrones de interacción a las limitaciones y *affordances* de cada dispositivo.

**A. Web Style Guidelines (Admin Dashboard & Landing Page)**
* **Grid Responsive:** Se emplea una grilla fluida de 12 columnas. En el área del *Dashboard*, el diseño se optimiza para grandes resoluciones (Desktop), priorizando la visualización de alta densidad de datos.
* **Data Visualization UI:** El panel de administración utiliza *Data Tables* con interactividad de *hover* (cambio de estado en la fila usando un matiz sutil del Action Blue `#1A82FF` al 10% de opacidad) para no saturar la vista. Las tarjetas de métricas (*Metric Cards*) utilizan elevación (*drop-shadow* de 2dp a 4dp) para generar jerarquía en el eje Z frente a un fondo neutro.
* **Navegación:** Un *Sidebar Navigation* anclado a la izquierda para cambiar de módulos rápidamente, manteniendo los filtros y herramientas de búsqueda siempre visibles y accesibles en la parte superior (*Top Bar*).

**B. Mobile Style Guidelines (App Conductor)**
La interfaz móvil está rigurosamente diseñada para escenarios de movilidad (uso a una mano y atención dividida).
* **Ergonomía Táctil (Thumb Zone):** Todo elemento accionable primario (CTAs) posee un área táctil mínima (*Touch Target*) de **48x48 dp** (estándar de accesibilidad de Apple HIG y Material Design). Las acciones críticas se sitúan en el tercio inferior de la pantalla para fácil acceso del pulgar.
* **Dark Mode por Defecto:** Al interactuar primariamente dentro del habitáculo del vehículo y en zonas de parqueo, el fondo Negro absoluto (`#000000`) se usa como base, mejorando el contraste de los textos en blanco y los acentos Naranja (`#FF9100`), además de optimizar el consumo de batería en pantallas OLED.
* **Retroalimentación Háptica (Haptic Feedback):** Las micro-interacciones clave, como la validación de un pago o la confirmación de la apertura de barrera (ALPR), se acompañan de una vibración háptica del dispositivo, confirmando al usuario el éxito de la operación sin depender exclusivamente de la lectura visual.

**C. IoT Style Guidelines (Interfaz Física de Hardware)**
El diseño en IoT trasciende la pantalla para convertirse en un diseño espacial o "Zero-UI" (interfaz de fricción cero), donde el entorno físico es el que comunica el estado.
* **Affordance Visual (Sensores y LEDs):** La comunicación es binaria y directa. La luz Verde (`#10B981`) comunica permisibilidad (espacio libre), mientras que la luz Roja (`#EF4444`) comunica restricción (espacio ocupado).
* **Alertas Cognitivas (Protocolo de Emergencia):** En un estado crítico (detección de gas MQ-2), el patrón lumínico cambia a parpadeo estroboscópico rojo, una señal universal de alarma diseñada para capturar inmediatamente el sistema visual periférico del conductor y detonar la acción de evacuación.
* **Interacción Invisible (ALPR):** En los puntos de acceso, el usuario no interactúa con tótems o botones físicos. La interacción se basa en la presencia física (la cámara detecta la placa y el Edge Server acciona el relé de la barrera). El diseño delega la interfaz gráfica al móvil (notificación *push*) y mantiene la interfaz física orientada puramente al flujo ininterrumpido del vehículo.

### 5.2. Information Architecture

La Arquitectura de Información (IA) de SpotFinder está diseñada para optimizar la carga cognitiva de los usuarios y garantizar la escalabilidad del código. Se estructuró bajo la premisa de *Zero-Friction* para los conductores en movilidad (App Móvil) y *Maximum Observability* para los operadores (App Web). A continuación, se detallan los sistemas que rigen la organización, el etiquetado, el posicionamiento (SEO/ASO) y la navegación del ecosistema.

### 5.2.1. Organization Systems

La organización del contenido dicta cómo se estructuran los módulos a nivel de desarrollo (Lazy Loading en Angular y GoRouter en Flutter).

**A. Landing Page (Web Estática)**
* **Jerárquica (Visual Hierarchy):** La estructura es vertical (*Top-Down*), ordenada por relevancia para la conversión B2B: Propuesta de valor (*Hero*) → Funcionalidades (*Features*) → Proceso operativo (*How It Works*) → Ventaja competitiva (*Admin Dashboard*) → Precios (*Pricing*) → Credibilidad (*Testimonials/FAQ*) → Acción (*Contact*).
* **Secuencial (Step-by-step):** La sección "How It Works" guía al visitante de forma lineal por el *Core Flow*: `1. Detección ALPR` → `2. Guiado LED` → `3. Pago Digital` → `4. Salida Automática`.
* **Matricial (Bento Grid):** La sección "Features" organiza las capacidades en celdas asimétricas, priorizando visualmente el renderizado del mapa en tiempo real frente a funciones complementarias.

**B. App Web (Dashboard Administrativo - Angular)**
* **Jerárquica (Shell Pattern):** El *layout* utiliza un patrón *App Shell* de Angular: `Sidebar (Navegación Primaria)` > `Top Bar (Contexto Global/Búsqueda)` > `Router Outlet (Contenido Dinámico)` > `Widgets/Data Tables`. El mapa de ocupación en vivo ocupa el cuadrante superior izquierdo, siendo el primer punto de fijación visual.
* **Por Tópicos (Feature Modules):** El menú lateral define los módulos de carga diferida (*Lazy-loaded modules*): *Monitoreo*, *Analítica*, *Finanzas*, *Seguridad* (Protocolos de Emergencia) y *Configuración*.
* **Matricial y Cronológico:** Los paneles de *Analytics* cruzan múltiples KPIs (ingresos vs. ocupación) en cuadrículas simultáneas, mientras que el *Log* de eventos (ingresos/salidas/alertas del sensor MQ-2) se organiza en orden cronológico inverso estricto.

**C. App Móvil (Conductores - Flutter)**
* **Por Tópicos (Bottom Nav):** La experiencia raíz se divide en 4 pilares de navegación (*IndexedStack* en Flutter para mantener el estado): `Map` (ubicación), `My Stay` (sesión activa), `Pay` (transacciones) y `Profile` (gestión de cuenta y vehículos).
* **Secuencial (Checkout Flow):** El proceso de pago es un túnel cerrado sin distracciones: `Revisar Estancia` → `Seleccionar Método (Yape/Tarjeta)` → `Validar Gateway (Culqi)` → `Emitir Recibo Digital`.
* **Por Audiencia:** La arquitectura condicional utiliza *Feature Flags* vinculados al JWT del usuario para habilitar o destruir vistas de servicios Premium (ej. pase Google Wallet).


### 5.2.2. Labeling Systems

El sistema de etiquetado (Microcopy) está centralizado en archivos de internacionalización (i18n) para asegurar consistencia. Las etiquetas son concisas (máximo 2 palabras), descriptivas y evitan la jerga de ingeniería.

**A. Landing Page Labels (Conversión)**
| Etiqueta | Componente | Propósito / Destino |
| :--- | :--- | :--- |
| **Get Started** | Primary CTA | Inicia el embudo de captación / Formulario de registro B2B. |
| **Book a Demo** | Secondary CTA | Despliega modal de calendario (ej. Calendly) para agendar pruebas. |
| **Dashboard** | Nav Link | Ancla explicativa sobre el panel de control administrativo. |
| **Hardware** | Nav Link | Detalla la infraestructura IoT (Edge Server, ALPR, Sensores). |

**B. App Web Labels (Dashboard Operativo)**
| Etiqueta | Componente | Propósito / Destino |
| :--- | :--- | :--- |
| **Live Map** | Sidebar Item | Renderizado de ocupación mediante WebSockets (`AVAILABLE`/`OCCUPIED`). |
| **Occupancy** | Metric Card | KPI porcentual de la Tasa de Ocupación actual e histórica. |
| **OOS** | Status Badge | "Out of Service" - Etiqueta roja/naranja para espacio inhabilitado manualmente. |
| **Heatmap** | Tab Link | Representación térmica de las zonas con mayor rotación vehicular. |

**C. App Móvil Labels (Conductor)**
| Etiqueta | Componente | Propósito / Destino |
| :--- | :--- | :--- |
| **My Stay** | Bottom Nav | Vista del tiempo transcurrido, costo acumulado dinámico y código asignado. |
| **Find My Car** | Action Button | Localiza el vehículo enlazado a la sesión (evita términos técnicos como *Vehicle Locator*). |
| **Garage** | Profile Item | CRUD para gestionar múltiples placas vinculadas a una sola cuenta. |


### 5.2.3. SEO Tags and Meta Tags

El ecosistema requiere estrategias distintas: indexación agresiva para la Landing Page, ofuscación total para el Dashboard Administrativo y optimización de tienda para la App Móvil.

**A. Web Meta Tags: Landing Page (Public Marketing Site)**
Orientado a la indexación de motores de búsqueda (SEO) y correcta previsualización en redes sociales (Open Graph / Twitter Cards).
```html
<title>SpotFinder | Advanced IoT Parking Systems for Malls</title>
<meta name="title" content="SpotFinder | Advanced IoT Parking Systems">
<meta name="description" content="Transform your parking facility with real-time IoT monitoring, ALPR entry automation, and advanced analytics. Reduce congestion and increase revenue up to 15%.">
<meta name="keywords" content="smart parking, IoT parking system, ALPR, parking management, shopping mall parking, SpotFinder Peru">
<meta name="author" content="SpotFinder Team">
<link rel="canonical" href="[https://spotfinder.com](https://spotfinder.com)">

<meta property="og:type" content="website">
<meta property="og:url" content="[https://spotfinder.com/](https://spotfinder.com/)">
<meta property="og:title" content="SpotFinder | Advanced IoT Parking Systems">
<meta property="og:description" content="Real-time parking intelligence for shopping malls and commercial facilities.">
<meta property="og:image" content="[https://spotfinder.com/assets/og-image.png](https://spotfinder.com/assets/og-image.png)">

<meta property="twitter:card" content="summary_large_image">
<meta property="twitter:url" content="[https://spotfinder.com/](https://spotfinder.com/)">
<meta property="twitter:title" content="SpotFinder | Advanced IoT Parking Systems">
```
**B. Web Meta Tags: App Web / Admin Dashboard (Private SPA)**

Orientado a la seguridad y privacidad. Al ser un portal administrativo, los motores de búsqueda no deben indexar estas rutas ni cachear contenido sensible.

```html
<title>SpotFinder Dashboard</title>
<meta name="robots" content="noindex, nofollow, noarchive, nosnippet">
<meta name="googlebot" content="noindex, nofollow">

<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Expires" content="0">

<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
```

**C. ASO Elements (Mobile App Store Optimization)**

Metadatos estructurados para el algoritmo de búsqueda de Google Play Store y Apple App Store.

* **App Title:** `SpotFinder – Smart Parking & Find My Car` *(Combina el brand con la función más buscada).*
* **App Subtitle (iOS):** `IoT Parking, Pay & Locate`
* **App Keywords (Ocultas):** `smart parking, find my car, parking payment, ALPR, IoT parking, contactless payment, SpotFinder, Yape, mall parking.`
* **App Description:** *SpotFinder revolutionizes your parking experience. Find available spaces in real-time, pay digitally via Culqi or Yape without queues, and never lose your car again with our "Find My Car" locator. Receive instant push notifications for your sessions and enjoy premium services like Google Wallet passes. Built for leading shopping malls powered by advanced IoT technology.*

#### 5.2.4. Searching Systems & Navigation (Core Flows)

Para garantizar que el usuario encuentre los datos sin esfuerzo, se implementan los siguientes patrones de búsqueda y enrutamiento funcional:

* **Búsqueda Global (Dashboard Web):** Uso de un *Omnibox* en el Top Bar que permite al administrador realizar consultas transversales (búsqueda por número de placa `ABC-123`, ID de espacio `A-12` o ID de transacción de pasarela). Los resultados redirigen dinámicamente al módulo correspondiente.
* **Deep Linking (App Móvil):** La navegación de la app soporta enlaces profundos manejados por Firebase Cloud Messaging (FCM). Al tocar una notificación de "Pago Pendiente", la arquitectura de navegación enruta al usuario saltando el menú principal, llevándolo directamente a la pantalla `Checkout_Screen`.


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
