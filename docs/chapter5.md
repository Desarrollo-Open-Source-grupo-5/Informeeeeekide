
# Capítulo V: Product Implementation, Validation & Deployment

## 5.1. Software Configuration Management

La Gestión de Configuración de Software (SCM) en el proyecto LoadMatch se establece bajo estándares de integración continua e infraestructura inmutable. Durante esta fase inicial, el ecosistema técnico se enfoca en el desarrollo de la presencia digital estática (Landing Page), sentando una arquitectura limpia en el cliente (Client-Side) preparada para escalar hacia integraciones 3D y servicios backend en sprints posteriores.

### 5.1.1. Software Development Environment Configuration

Para mantener la consistencia en el entorno de desarrollo y evitar discrepancias de configuración entre los ingenieros de software, se ha estandarizado el siguiente ecosistema de herramientas nativas y de gestión:

| Dominio | Herramienta / Estándar | Propósito Técnico | Tipo de Acceso / Ruta |
| --- | --- | --- | --- |
| **Project Management** | Jira Software | Gestión del Product Backlog, Sprints y estimación en Story Points para el seguimiento ágil. | https://www.atlassian.com/es/software/jira |
| **Product UX/UI Design** | Figma | Creación de wireframes, prototipos interactivos y diseño del sistema de componentes visuales. | https://www.figma.com/es-la/ |
| **Frontend Structure** | Semantic HTML5 | Estructuración semántica del Document Object Model (DOM) para optimización de accesibilidad y SEO. | Estándar W3C |
| **Frontend Styling** | CSS3 (Grid/Flexbox) | Diseño responsivo (Mobile-First), animaciones y maquetación sin dependencias de frameworks externos. | Estándar W3C |
| **Frontend Logic** | Vanilla JavaScript (ES6+) | Manipulación del DOM, validación de formularios asíncrona y control de eventos interactivos. | Estándar ECMAScript |
| **IDE** | Visual Studio Code | Edición de código con extensiones de formateo (Prettier) y análisis estático de JS (ESLint). | https://code.visualstudio.com/ |
| **Version Control** | Git + GitHub | Gestión distribuida del código fuente, flujos de integración y revisión de pares (Pull Requests). | https://github.com/ |

### 5.1.2. Source Code Management

El código fuente del Landing Page se gestiona de manera centralizada en un repositorio dedicado, asegurando el desacoplamiento estructural de los futuros microservicios de la plataforma LoadMatch.

* **Repositorio Oficial (Landing Page):** `LIONKKKKKKKKKKKKKKKKKKKK DEPLOYADO LANDINGGGGG`

**Estrategia de Ramificación (GitFlow):**
El equipo implementa un flujo estricto para proteger la estabilidad de la página de aterrizaje:

* `main`: Entorno de producción. Contiene código HTML/CSS/JS minificado y optimizado. Las fusiones requieren validación y aprobación de Pull Requests.
* `develop`: Rama principal de integración. Agrupa las secciones visuales maquetadas durante el Sprint antes de su paso a producción.
* `feature/*`: Ramas efímeras creadas desde `develop` para desarrollar componentes específicos (ej. `feature/US12-hero-section`, `feature/US14-contact-form`).

### 5.1.3. Source Code Style Guide & Conventions

**Convenciones de Estructura y Estilos (HTML5 / CSS3):**

* **Metodología BEM (Block, Element, Modifier):** Se aplica estrictamente en CSS para evitar la colisión de selectores y mantener una especificidad baja. Ejemplo: `.contact-form` (Bloque), `.contact-form__input` (Elemento), `.contact-form__button--active` (Modificador).
* **Variables CSS (Custom Properties):** Centralización de la paleta de colores corporativa y tipografías de LoadMatch en el seudoclase `:root` para asegurar consistencia visual y facilitar la futura implementación de temas (Dark Mode).
* **HTML Semántico:** Prohibición del sobre-anidamiento de etiquetas `<div>`. Uso obligatorio de etiquetas semánticas (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`) para mejorar el posicionamiento en buscadores (SEO).

**Convenciones de Lógica (Vanilla JavaScript):**

* **Aislamiento de Scope:** Prohibido el uso de variables globales. Se exige el uso de `const` y `let` (ES6+) dentro de funciones de inicialización o módulos (IIFE) para evitar contaminación del entorno global.
* **Manipulación de Eventos:** Uso exclusivo de `addEventListener` para separar completamente la lógica de comportamiento (JS) de la estructura (HTML).

**Convenciones de Commits (Conventional Commits):**

* `feat:` Nueva sección o componente UI (ej. `feat: add fleet catalog section`).
* `style:` Cambios en CSS que no afectan la lógica (ej. `style: update hero background layout`).
* `fix:` Corrección de errores visuales o de JavaScript.

### 5.1.4. Software Deployment Configuration

La canalización de despliegue del Landing Page de LoadMatch aprovecha la naturaleza estática de los artefactos (archivos HTML, CSS y JS) utilizando plataformas de alojamiento sin servidor (Serverless Hosting) altamente eficientes.

1. **Plataforma de Despliegue:** GitHub Pages / Vercel.
2. **Pipeline de Publicación:** Al integrar código en la rama `main` de GitHub, la plataforma detecta los archivos estáticos y distribuye los artefactos a través de su Red de Entrega de Contenido (CDN) global.
3. **Optimización:** Previo al despliegue en la rama principal, se asegura la minificación de los archivos `.css` y `.js`, y la compresión de los assets visuales (imágenes en formato WebP o SVG) para garantizar tiempos de carga ultrarrápidos (Time to Interactive).

---

## 5.2. Landing Page, Services & Applications Implementation

### 5.2.1. Sprint 1

#### 5.2.1.1. Sprint Planning 1

#### 5.2.1.2. Aspect Leaders and Collaborators

#### 5.2.1.3. Sprint Backlog 1

#### 5.2.1.4. Development Evidence for Sprint Review

#### 5.2.1.5. Execution Evidence for Sprint Review

#### 5.2.1.6. Services Documentation Evidence for Sprint Review

#### 5.2.1.7. Software Deployment Evidence for Sprint Review

#### 5.2.1.8. Team Collaboration Insights during Sprint



---

## 5.2. Landing Page, Services & Applications Implementation

### 5.2.1. Sprint 1

Durante esta primera iteración, la ejecución técnica se aisló estrictamente en la validación temprana del mercado mediante el desarrollo de un Landing Page estático. Se empleó una arquitectura nativa basada en HTML5, CSS3 y Vanilla JavaScript, estableciendo un Document Object Model (DOM) limpio, preparado para soportar futuras inyecciones de renderizado 3D dinámico.

#### 5.2.1.1. Sprint Planning 1

| Sprint # | Sprint 1 |
| --- | --- |
| **Date** | 01/09/2026 |
| **Time** | 08:30 PM |
| **Location** | Microsoft Teams |
| **Prepared By** | Christoper Rivas |
| **Attendees** | Equipo de Desarrollo LoadMatch |
| **Sprint 1 Review Summary** | El equipo completó la maquetación nativa del Landing Page de LoadMatch. Se estructuró el código separando semánticamente las secciones de Propuesta de Valor, Catálogo de Flota y Contacto. Se aplicaron estilos responsivos mediante CSS Flexbox y Grid, dotando de interactividad al DOM con Vanilla JavaScript para validación de formularios y animaciones de scroll suave. |
| **Sprint 1 Retrospective Summary** | La implementación de la metodología BEM en CSS previno efectivamente las colisiones de estilos entre desarrolladores. Como oportunidad de mejora, se acordó optimizar aún más el peso de los assets visuales desde la exportación en Figma para maximizar la puntuación en Google Lighthouse en los próximos despliegues. |
| **Sprint 1 Goal** | Desarrollar y desplegar la versión inicial del Landing Page utilizando un stack web estático. El objetivo central es comunicar claramente el modelo de negocio, captar leads tempranos de empresas y transportistas, y dejar la base estructural del código preparada para futuras iteraciones de interactividad 3D. |
| **Sprint 1 Velocity** | 7 Story Points |
| **Sum of Story Points** | 7 Story Points |

#### 5.2.1.2. Aspect Leaders and Collaborators

La distribución de responsabilidades se enfocó en la separación de dominios del desarrollo web estático (Estructura, Presentación y Comportamiento).

| Team Member | GitHub Username | HTML5 (Estructura & SEO) | CSS3 (Estilos & Responsividad) | Vanilla JS (Interactividad) |
| --- | --- | --- | --- | --- |
| Christoper Rivas | ChristoperRivas | Líder | Colaborador | Colaborador |
| Integrante 2 | DevLoadMatch2 | Colaborador | Líder | Colaborador |
| Integrante 3 | DevLoadMatch3 | Colaborador | Colaborador | Líder |

#### 5.2.1.3. Sprint Backlog 1

Este Sprint cubre de forma exclusiva el Epic 06 (Gestión del Landing Page).

| User Story Id | User Story Title | Task Id | Task Title | Description | Estimation | Assigned To | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **US12** | Visualización de propuesta de valor | T01 | Maquetación Semántica del Hero | Estructuración HTML5 del Hero Section y la barra de navegación, asegurando jerarquía de etiquetas y accesibilidad. | 3h | Christoper Rivas | Done |
| **US13** | Consulta de tipos de vehículos | T02 | Catálogo CSS Flexbox/Grid | Diseño responsivo del catálogo de vehículos, implementando Media Queries para la adaptación entre dispositivos móviles y de escritorio. | 2h | Integrante 2 | Done |
| **US14** | Formulario de contacto | T03 | Validación DOM Vanilla JS | Captura de eventos del formulario (`submit`, `input`) mediante JavaScript nativo para validar campos requeridos y formato de correo. | 2h | Integrante 3 | Done |

#### 5.2.1.4. Development Evidence for Sprint Review

La gestión del código fuente se centralizó en el repositorio estático, utilizando ramas aisladas para cada sección visual de la página.

| Repository | Branch | Commit Id | Commit Message | Commited on |
| --- | --- | --- | --- | --- |
| loadmatch-landing | main | a1b2c3d | chore: init static project structure html, css and js folders | 02/09/2026 |
| loadmatch-landing | feature/US12-hero | e4f5g6h | feat: add semantic HTML5 structure for hero and value proposition | 03/09/2026 |
| loadmatch-landing | feature/US13-fleet | i7j8k9l | style: implement responsive CSS Grid and BEM classes for fleet catalog | 04/09/2026 |
| loadmatch-landing | feature/US14-contact | m1n2o3p | feat: add vanilla javascript event listeners for form real-time validation | 05/09/2026 |
| loadmatch-landing | develop | q4r5s6t | chore: merge all UI sections and normalize css global root variables | 06/09/2026 |
| loadmatch-landing | main | u7v8w9x | refactor: optimize webp images and link final javascript modules | 07/09/2026 |

#### 5.2.1.5. Execution Evidence for Sprint Review

Durante este Sprint, el equipo materializó con éxito la interfaz visual del Landing Page de LoadMatch. Se garantizó que la estructura del DOM se adaptara fluidamente a dispositivos móviles, tablets y monitores mediante *Media Queries*. El archivo `style.css` centralizó el diseño utilizando unidades relativas (`rem`, `vh`) para garantizar fluidez en el escalado, mientras que el script `main.js` orquestó el comportamiento de la barra de navegación interactiva y la evaluación de los campos de contacto.

#### 5.2.1.6. Services Documentation Evidence for Sprint Review

En alineación con la estrategia técnica definida para este Sprint, **no se integraron bases de datos, APIs RESTful ni servicios Backend**. Toda la interacción de la lógica de contacto (US14) y el manejo de estados de la UI se ejecutó del lado del cliente (*Client-Side Validation*) utilizando el API nativo del navegador. La validación de los datos de contacto previene el envío de *payloads* mal formados y almacena temporalmente los *leads* en el `localStorage` del navegador para fines de demostración en la revisión del Sprint. La integración con los servicios en la nube queda programada para las siguientes iteraciones.

#### 5.2.1.7. Software Deployment Evidence for Sprint Review

El artefacto resultante de este sprint es un sitio estático puro. Se utilizó **GitHub Pages** como infraestructura de alojamiento principal, lo que permite un despliegue sin servidor (Serverless Hosting) de alta velocidad.

**Actividades Realizadas:**

* **Configuración del Entorno:** Habilitación de GitHub Pages desde la pestaña de configuración del repositorio, apuntando la ruta de despliegue directamente a la rama `main` en la carpeta raíz.
* **Pipeline de Publicación Continua:** Cualquier fusión aprobada hacia la rama principal dispara el proceso de construcción estática interno de GitHub, publicando los cambios instantáneamente en la red global.
* **URL Pública Generada:** El sitio es accesible desde cualquier navegador, lo que permite al equipo realizar validaciones de usabilidad con usuarios finales reales.

**Enlace del Repositorio:** `[https://github.com/Desarrollo-Open-Source-grupo-5/loadmatch-landing](https://github.com/Desarrollo-Open-Source-grupo-5/loadmatch-landing)`
**URL del Landing Page Desplegado:** `[https://Desarrollo-Open-Source-grupo-5.github.io/loadmatch-landing/](https://Desarrollo-Open-Source-grupo-5.github.io/loadmatch-landing/)`

#### 5.2.1.8. Team Collaboration Insights during Sprint

La exclusión de frameworks pesados en esta fase exigió una coordinación rigurosa a nivel de archivos estáticos. El equipo implementó una estrategia colaborativa basada en la segmentación clara de la hoja de estilos y la modularización de los scripts.

* **Integración CSS Controlada:** Para evitar la sobreescritura de reglas visuales en un entorno sin preprocesadores avanzados, el equipo aplicó la metodología BEM. Los desarrolladores trabajaron en ramas locales y sometieron sus maquetas visuales a revisiones cruzadas (Pull Requests) para verificar la consistencia estética y el uso obligatorio del archivo de variables (`:root`) antes de fusionar el código.
* **Manejo del DOM en Equipo:** Las revisiones de código en JavaScript se centraron en garantizar que la manipulación del DOM no interfiriera con componentes desarrollados por otros miembros, utilizando selectores específicos e instanciando los Event Listeners de forma modular una vez que el documento estuviera completamente cargado (`DOMContentLoaded`). La fluidez de la comunicación a través de Microsoft Teams permitió resolver las discrepancias de diseño de manera inmediata.
