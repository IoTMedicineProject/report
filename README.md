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

### 2.2.2. Registro de entrevistas

## Segmento Objetivo 1

#### **Entrevista 1**
| ![Perfil](./assets/images/interviews/user-icon.png) | **Datos Personales** |
| :--- | :--- |
| **Nombres** | Maria Fernanda |
| **Apellidos** | Esteban Román |
| **Distrito** | Surco |
| **Edad** | 21 años |
| **Enlace** | [🔗 Ver grabación de la entrevista](#) |

**Evidencia**
![Captura de la entrevista 1](./assets/images/interviews/evidencia-1.png)

**Resumen**
Estudiante universitaria que visita centros comerciales como el Jockey Plaza dos veces por semana. Su principal frustración es la pérdida de tiempo (15-20 minutos) buscando estacionamiento y la falta de información real sobre la disponibilidad en los sótanos. Usuario activo de herramientas tecnológicas como Waze y Yape, considera que un sistema de guiado por luces LED y una app con disponibilidad en tiempo real serían determinantes para mejorar su experiencia y reducir el estrés.

---

#### **Entrevista 2**
| ![Perfil](./assets/images/interviews/user-icon.png) | **Datos Personales** |
| :--- | :--- |
| **Nombres** | Freddy Carlos |
| **Apellidos** | Alvarez |
| **Distrito** | Miraflores |
| **Edad** | 22 años |
| **Enlace** | [🔗 Ver grabación de la entrevista](#) |

**Evidencia**
![Captura de la entrevista 2](./assets/images/interviews/evidencia-2.png)

**Resumen**
Usuario frecuente de estacionamientos en centros comerciales que prioriza la seguridad y la eficiencia en el pago. Reporta una alta frustración debido a las largas colas en los cajeros físicos y la dificultad de encontrar espacios en temporadas altas. Valora positivamente la automatización mediante el reconocimiento de placas vehiculares (ALPR) y la posibilidad de realizar pagos digitales a través de la app, lo cual considera una solución necesaria para modernizar el servicio actual.

---

#### **Entrevista 3**
| ![Perfil](./assets/images/interviews/user-icon.png) | **Datos Personales** |
| :--- | :--- |
| **Nombres** | Diego Ignacio |
| **Apellidos** | Ricra Falla |
| **Distrito** | San Borja |
| **Edad** | 24 años |
| **Enlace** | [🔗 Ver grabación de la entrevista](#) |

**Evidencia**
![Captura de la entrevista 3](./assets/images/interviews/evidencia-3.png)

**Resumen**
Estudiante  joven que utiliza el vehículo para movilizarse a reuniones y recados, visitando malls hasta tres veces por semana. Su mayor problema es la desorientación dentro del estacionamiento (olvida la ubicación del vehículo) y la falta de métodos de pago prácticos cuando no cuenta con efectivo. [Se muestra muy interesado en las funciones de reserva de espacios con anticipación y en recibir notificaciones de seguridad en su smartphone para mayor tranquilidad durante su estancia.

### 2.2.3. Análisis de entrevistas

Las entrevistas se realizaron a un total de tres participantes del segmento de conductores en Lima Metropolitana. El objetivo fue entender sus contextos operativos, frustraciones actuales y validar hipótesis sobre la implementación de SpotFinder.

**Segmento:** Conductores
**Total entrevistados:** 3
**Edades:** 21, 22 y 24 años
**Distritos:** Surco, San Borja y Miraflores
**Fechas:** Abril de 2026

**Características objetivas**
* Invierten entre 15 y 20 minutos en encontrar un espacio libre en horas punta: 3/3 (90%)
* Han experimentado bajar a un nivel de estacionamiento solo para descubrir que está lleno: 3/3 (100%)
* Utilizan frecuentemente aplicaciones de billetera digital (Yape/Plin) y navegación (Waze/Maps): 3/3 (100%)
* Realizan el pago del estacionamiento de forma manual en cajas físicas: 3/3 (90%)

**Características subjetivas**
* Encuentran frustrante el tiempo perdido y la ineficiencia de los métodos de pago actuales: 3/3 (100%)
* Valoran positivamente el guiado visual por luces LED para ubicar espacios rápidamente: 3/3 (100%)
* Consideran que una aplicación con disponibilidad en tiempo real reduciría su estrés: 3/3 (100%)
* Manifiestan haber olvidado la ubicación exacta de su vehículo en el estacionamiento: 2/3 (66%)
* Interesados en la reserva anticipada de espacios para eventos o cine: 2/3 (66%)
* Disposición total a adoptar la herramienta si garantiza ahorro de tiempo: 3/3 (100%)

**Conclusión general**
Este análisis refleja una clara necesidad de modernización en la gestión de estacionamientos. La coincidencia del 100% en la frustración por el tiempo de búsqueda y la disposición al uso de soluciones digitales confirma que SpotFinder ataca un punto de dolor crítico. La integración de hardware (LEDs) y software (App de pagos) es la combinación más valorada por los conductores.

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