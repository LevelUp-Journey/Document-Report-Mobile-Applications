# Capítulo IV: Product Implementation & Validation

# 4. Product Implementation & Validation
En esta sección, se detalla el proceso de implementación, verificación, despliegue y validación de la solución. La solución se compone de una Landing Page que presenta el modelo de negocio, una aplicación móvil nativa para la interacción del usuario y servicios RESTful que soportan la lógica de negocio. Los procesos de negocio, tanto los `core` como los de soporte (ej. Autenticación y Autorización), se distribuyen a través de estos componentes.

## 4.1. Software Configuration Management
En esta sección, se establecen las decisiones y convenciones para mantener la consistencia durante todo el ciclo de vida del desarrollo de software. Se incluyen detalles sobre la gestión del código fuente, la configuración del entorno de desarrollo y la configuración del despliegue.

### 4.1.1. Software Development Environment Configuration
A continuación, se especifican las herramientas de software utilizadas por el equipo para colaborar en el ciclo de vida de los productos digitales.

| Herramienta                  | Propósito                                       | Referencia / Descarga                                     |
| ---------------------------- | ----------------------------------------------- | --------------------------------------------------------- |
| **Gestión de Proyectos**     |                                                 |                                                           |
| Jira                         | Gestión de tareas y seguimiento de Sprints      | [atlassian.com/software/jira](https://www.atlassian.com/software/jira) |
| **Diseño UX/UI**             |                                                 |                                                           |
| Figma                        | Diseño de prototipos y experiencia de usuario   | [figma.com](https://figma.com)                            |
| **Desarrollo Backend**       |                                                 |                                                           |
| IntelliJ IDEA Ultimate       | IDE para el desarrollo en Java y Spring Boot    | [jetbrains.com/idea](https://www.jetbrains.com/idea/)     |
| Java (JDK 24)                | Lenguaje de programación para el backend        | [oracle.com/java](https://www.oracle.com/java/)           |
| Spring Boot 3                | Framework para la creación de servicios RESTful | [spring.io/projects/spring-boot](https://spring.io/projects/spring-boot) |
| Maven                        | Gestión de dependencias y construcción del proyecto | [maven.apache.org](https://maven.apache.org)              |
| Docker                       | Contenerización de la aplicación                | [docker.com/get-started](https://www.docker.com/get-started) |
| **Desarrollo Frontend (Landing Page)** |                                     |                                                           |
| Visual Studio Code           | Editor de código para desarrollo web            | [code.visualstudio.com](https://code.visualstudio.com)    |
| Node.js                      | Entorno de ejecución para JavaScript            | [nodejs.org](https://nodejs.org)                          |
| Astro.js                     | Framework para construir la Landing Page        | [astro.build](https://astro.build)                        |
| TypeScript                   | Lenguaje de programación para el frontend       | [typescriptlang.org](https://www.typescriptlang.org)      |
| **Desarrollo Móvil**         |                                                 |                                                           |
| Android Studio               | IDE para el desarrollo de la aplicación Android | [developer.android.com/studio](https://developer.android.com/studio) |
| Kotlin                       | Lenguaje de programación para la app móvil      | [kotlinlang.org](https://kotlinlang.org)                  |
| Jetpack Compose              | Toolkit para la construcción de la UI nativa    | [developer.android.com/jetpack/compose](https://developer.android.com/jetpack/compose) |
| **Pruebas y Calidad**        |                                                 |                                                           |
| Postman                      | Pruebas de API y servicios web                  | [postman.com](https://www.postman.com)                    |
| JUnit 5                      | Framework para pruebas unitarias en Java        | [junit.org/junit5](https://junit.org/junit5)              |
| **Despliegue**               |                                                 |                                                           |
| Azure CLI                    | Interfaz de línea de comandos para Azure        | [docs.microsoft.com/cli/azure](https://docs.microsoft.com/cli/azure) |
| GitHub Actions               | CI/CD para automatización de despliegues        | [github.com/features/actions](https://github.com/features/actions) |

### 4.1.2. Source Code Management
Se utiliza GitHub como plataforma y sistema de control de versiones para gestionar el código fuente de todos los productos.

- **Repositorio de Backend (Web Services):** [https://github.com/LevelUp-Journey](https://github.com/LevelUp-Journey)
- **Repositorio de Frontend (Landing Page):** [https://github.com/LevelUp-Journey/Landing-Page](https://github.com/LevelUp-Journey/Landing-Page)
- **Repositorio de Aplicación Móvil:** [https://github.com/LevelUp-Journey/MobileApp-Front](https://github.com/LevelUp-Journey/MobileApp-Front)

**Workflow de Control de Versiones (GitFlow)**

Se adopta el modelo de branching GitFlow para organizar el trabajo y gestionar las versiones del software.

- **`main`:** Esta rama siempre contiene el código de producción estable. Solo se fusiona desde las ramas `release` y `hotfix`.
- **`develop`:** Es la rama principal de desarrollo. Contiene las últimas funcionalidades desarrolladas y estables. Sirve como base para crear nuevas ramas de `feature`.

**Convenciones de Nomenclatura de Ramas:**

- **Feature Branches:** Se crean a partir de `develop` para trabajar en nuevas funcionalidades.
  - **Formato:** `feature/<nombre-descriptivo-de-la-feature>`
  - **Ejemplo:** `feature/user-authentication`
- **Release Branches:** Se crean a partir de `develop` cuando se prepara una nueva versión de producción. Permiten la preparación final (pruebas, correcciones menores).
  - **Formato:** `release/vX.Y.Z` (siguiendo Semantic Versioning)
  - **Ejemplo:** `release/v1.0.0`
- **Hotfix Branches:** Se crean a partir de `main` para corregir errores críticos en producción.
  - **Formato:** `hotfix/vX.Y.Z`
  - **Ejemplo:** `hotfix/v1.0.1`

**Versionamiento Semántico (Semantic Versioning):**
Todas las releases seguirán el estándar de [Semantic Versioning 2.0.0](https://semver.org/). El formato de versión es `MAJOR.MINOR.PATCH`.

**Convencional Commits:**
Todos los mensajes de commit deben seguir la especificación de [Conventional Commits](https://www.conventionalcommits.org/). Esto mejora la legibilidad del historial y permite automatizar la generación de changelogs.
- **Ejemplo:** `feat: allow users to upload a profile picture`

### 4.1.3. Source Code Style Guide & Coding Conventions
Para asegurar la consistencia y calidad del código, el equipo adopta las siguientes guías de estilo y convenciones. El inglés es el idioma estándar para todo el código y la nomenclatura.

- **Java (Backend):** Se sigue la [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html) junto con las convenciones y el formato de código estándar de [Spring Boot](https://docs.spring.io/spring-boot/docs/current/reference/html/using-spring-boot.html#using-boot-code-style).
- **TypeScript (Landing Page):** Se adhiere a la [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html).
- **Kotlin (Aplicación Móvil):** Se aplican las [convenciones de codificación oficiales de Kotlin](https://kotlinlang.org/docs/coding-conventions.html) y las guías recomendadas para Jetpack Compose.
- **Gherkin (Archivos .feature):** Se utiliza la guía [Gherkin Conventions for Readable Specifications](https://docs.cucumber.io/gherkin/reference/#conventions) para escribir escenarios de prueba claros y comprensibles.

### 4.1.4. Software Deployment Configuration
Esta sección detalla la configuración y los pasos necesarios para el despliegue de cada producto digital de la solución.

**Landing Page (Astro.js):**
1.  **Disparador:** Un `push` o `merge` a la rama `main` en el repositorio de GitHub.
2.  **CI/CD:** Vercel se encarga automáticamente del proceso de CI/CD.
3.  **Build:** Vercel instala las dependencias (`npm install`) y construye el sitio estático (`npm run build`).
4.  **Deploy:** Los archivos estáticos generados se despliegan en **Vercel** para su publicación.

**Backend (Spring Boot Web Services):**
1.  **Disparador:** Un `push` o `merge` a la rama `main`.
2.  **CI/CD:** Un workflow de GitHub Actions se activa.
3.  **Build & Test:** El workflow compila el código, ejecuta las pruebas unitarias y de integración (`mvn clean install`).
4.  **Contenerización:** Se construye una imagen Docker de la aplicación a partir de su Dockerfile.
5.  **Push a Registro:** La imagen Docker se etiqueta y se sube a **Azure Container Registry**.
6.  **Deploy:** Se actualiza el servicio en **Azure Container Apps** para que utilice la nueva imagen del contenedor, completando el despliegue.

**Mobile Application (Jetpack Compose):**
1.  **Disparador:** Creación de una `release` en el repositorio de GitHub.
2.  **CI/CD:** Un workflow de GitHub Actions se activa para construir la aplicación.
3.  **Build & Sign:** El workflow genera un Android App Bundle (`.aab`) firmado para producción.
4.  **Deploy:** El archivo `.aab` se sube a la **Google Play Console**. Desde allí, se gestiona el lanzamiento a través de los diferentes canales (interno, alfa, beta, producción) para su publicación en la Google Play Store.

**Diagrama de Despliegue (C4 Model):**

A continuación, se muestra el diagrama de despliegue que ilustra la infraestructura y la disposición de los componentes de la solución en los diferentes entornos.

![Deployment Diagram](../chapter2/assets/deployment/DeploymentDiagram.png)
## 4.2. Landing Page & Mobile Application Implementation

### 4.2.1. Sprint n

Para este primer sprint, nos enfocaremos en las tareas necesarias para el **desarrollo del backend (70%)** y la **implementación inicial de la Landing Page** de **LevelUp Journey**. El equipo distribuirá las actividades según las áreas técnicas —infraestructura, API, base de datos y diseño visual— con el objetivo de establecer una base sólida para los siguientes incrementos del producto.

#### 4.2.1.1. Sprint Planning n

| **Sprint #**                        | **Sprint 1**                                                 |
| ----------------------------------- | ------------------------------------------------------------ |
| **Sprint Planning Background**      | Durante este primer sprint, el equipo se enfocará en desarrollar la base técnica del sistema (backend) y la interfaz inicial (landing page) que permita validar la propuesta de valor del proyecto **LevelUp Journey**. |
| **Date**                            | 2025-10-10                                                   |
| **Time**                            | 10:30 AM                                                     |
| **Location**                        | Reunión virtual vía Microsoft Teams                          |
| **Prepared By**                     | Mateo Alemán Romano                                          |
| **Attendees (to planning meeting)** | Dante Mateo Aleman Romano / Jonatan Ariel Acuña Corahua / Fabrizio Alessandro Contreras Peralta/ Romina Guadalupe Maita Falckenheiner/ Paolo Alessandro Torres Flores |
| **Sprint Goal & User Stories**      | **Sprint 1 Goal:** Implementar el **backend al 70 %** (autenticación, base de datos y API principal) y desarrollar la **Landing Page** funcional con secciones de presentación y registro para validar la interacción inicial de los usuarios.**Sprint Metric:** Validar endpoints funcionales en entorno local y contar con la Landing desplegada en entorno de prueba. |
| **Sprint 1 Velocity**               | 110 Story Points                                             |
| **Sum of Story Points**             | 95 Story Points                                              |

#### 4.2.1.2. Sprint Backlog n

PONER EL LINK DE JIRA

#### 4.2.1.3. Development Evidence for Sprint Review

# Commit History - LevelUp-Journey/Landing-Page

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited On (Date) |
| ---------- | ------ | --------- | -------------- | ------------------- | ------------------ |
| LevelUp-Journey/Landing-Page | hotfix/2.0.3 | 6abf43e | Refactor Header and Footer components to use Title component; add Title component with logo; update favicon link in index.astro | | 2025-10-01 00:54:16 |
| LevelUp-Journey/Landing-Page | main | 3a939cf | Merge pull request #13 from LevelUp-Journey/hotfix/2.0.2 | feat: Implement language dropdown component and sticky header functio… | 2025-09-30 22:10:18 |
| LevelUp-Journey/Landing-Page | hotfix/2.0.2 | 23ad9bc | feat: Implement language dropdown component and sticky header functionality; update bubble configuration | | 2025-09-30 22:09:53 |
| LevelUp-Journey/Landing-Page | main | 16962ff | Merge pull request #12 from LevelUp-Journey/hotfix/2.0.1 | Hotfix/2.0.1 | 2025-09-30 21:45:27 |
| LevelUp-Journey/Landing-Page | hotfix/2.0.1 | 9c15c74 | feat: Add new SVG icons for C++, Java, JavaScript, and Python; update paths in FloatingLanguages component | | 2025-09-30 21:39:06 |
| LevelUp-Journey/Landing-Page | hotfix/2.0.1 | c5831c0 | Remove obsolete programming language icons (Java, JavaScript, Python, Rust, Swift, TypeScript) and add new SVG icons for C++, Java, JavaScript, and Python with updated designs. | | 2025-09-30 21:33:36 |
| LevelUp-Journey/Landing-Page | main | 7f4865e | Merge pull request #10 from LevelUp-Journey/release2.0.0 | Release2.0.0 | 2025-09-30 21:08:34 |
| LevelUp-Journey/Landing-Page | develop | bac328e | Merge pull request #9 from LevelUp-Journey/feature/add-fix-icons | Feature/add fix icons | 2025-09-30 20:20:38 |
| LevelUp-Journey/Landing-Page | feature/add-fix-icons | 64ec409 | feat: Update footer and header to use anchor tags for logo links; change Section2 background color for consistency | | 2025-09-30 20:19:29 |
| LevelUp-Journey/Landing-Page | feature/add-fix-icons | 5dfd9d7 | feat: Update leaderboard scores for improved ranking accuracy | | 2025-09-30 20:09:41 |
| LevelUp-Journey/Landing-Page | feature/add-fix-icons | db20406 | feat: Implement bubble physics with state management and responsive behavior for floating languages | | 2025-09-30 20:06:35 |
| LevelUp-Journey/Landing-Page | feature/add-fix-icons | a4f27e0 | feat: Replace PNG icons with SVG counterparts and update header for sticky effect | | 2025-09-30 20:00:32 |
| LevelUp-Journey/Landing-Page | develop | 3a80258 | Merge pull request #8 from LevelUp-Journey/main | Merge pull request #7 from LevelUp-Journey/release/1.0.0 | 2025-09-30 19:59:41 |
| LevelUp-Journey/Landing-Page | main | 85dd97d | Merge pull request #7 from LevelUp-Journey/release/1.0.0 | Release/1.0.0 | 2025-09-30 19:03:07 |
| LevelUp-Journey/Landing-Page | release/1.0.0 | ca6468e | Merge pull request #6 from LevelUp-Journey/feature/add-i18n | Feature/add i18n | 2025-09-30 18:49:13 |
| LevelUp-Journey/Landing-Page | feature/add-i18n | 543a4e5 | feat: Refactor FloatingLanguages component to use templates for bubble creation and add state management | | 2025-09-30 18:46:01 |
| LevelUp-Journey/Landing-Page | feature/add-i18n | 98ff982 | feat: Add FloatingLanguages component to Hero section and new programming language icons | - Integrated FloatingLanguages component into the Hero section for enhanced visual appeal.<br>- Added SVG icons for various programming languages: C++, .NET, Go, Java, JavaScript, Python, Rust, Swift, and TypeScript.<br>- Updated LeaderboardCard component to improve user name transition effects.<br>- Minor CSS adjustments in global styles for better layout consistency. | 2025-09-30 18:31:00 |
| LevelUp-Journey/Landing-Page | release/1.0.0 | e1a0c37 | Merge pull request #5 from LevelUp-Journey/feature/add-i18n | Feature/add i18n | 2025-09-30 18:09:39 |
| LevelUp-Journey/Landing-Page | feature/add-i18n | c4116b1 | feat: implement internationalization support with language toggle and translation updates | | 2025-09-30 18:08:38 |
| LevelUp-Journey/Landing-Page | feature/add-i18n | 0f2e517 | chore: add Visual Studio Code setting folder to .gitignore | | 2025-09-30 17:46:14 |
| LevelUp-Journey/Landing-Page | feature/add-i18n | 4fb36b9 | chore: remove unused VSCode configuration files | | 2025-09-30 17:45:29 |
| LevelUp-Journey/Landing-Page | release/1.0.0 | 598a1c9 | Merge pull request #4 from LevelUp-Journey/feature/add-section4 | Feature/add section4 | 2025-09-30 17:42:51 |
| LevelUp-Journey/Landing-Page | feature/add-section4 | 6a69252 | feat: enhance layout and styling consistency across sections and components | | 2025-09-30 17:41:56 |
| LevelUp-Journey/Landing-Page | feature/add-section4 | 90ad613 | feat: add footer, hero section, leaderboard, and additional sections with images | | 2025-09-30 17:25:05 |
| LevelUp-Journey/Landing-Page | release/1.0.0 | 80dd901 | Merge pull request #3 from LevelUp-Journey/feature/add-section-ranks | Feature/add section ranks | 2025-09-30 16:21:03 |
| LevelUp-Journey/Landing-Page | feature/add-section-ranks | f64c227 | feat: import and include Section3 component in index.astro | | 2025-09-30 16:19:07 |
| LevelUp-Journey/Landing-Page | feature/add-section-ranks | 4244cda | feat: add Section3 component with leaderboard and user rankings | | 2025-09-30 16:18:59 |
| LevelUp-Journey/Landing-Page | feature/add-section-ranks | 4e1bd4c | fix: adjust icon size in FeatureCard component | | 2025-09-30 16:18:48 |
| LevelUp-Journey/Landing-Page | feature/add-section-ranks | 756ec65 | feat: add rank images for section 3 (Bronze, Silver, Gold, Platinum, Diamond, Master, GrandMaster) | | 2025-09-30 16:18:25 |
| LevelUp-Journey/Landing-Page | release/1.0.0 | 0debe67 | Merge pull request #2 from LevelUp-Journey/feature/add-section1 | Feature/add section1 | 2025-09-30 15:48:02 |
| LevelUp-Journey/Landing-Page | feature/add-section1 | e70f645 | feat: add Section2 component with feature cards and icons | | 2025-09-30 15:36:35 |
| LevelUp-Journey/Landing-Page | feature/add-section1 | d2bc37d | feat: add Section1 component with email signup form and background image | | 2025-09-30 14:56:23 |
| LevelUp-Journey/Landing-Page | feature/add-section2 | 301729a | feat: add background image for section 1 | | 2025-09-30 14:50:18 |
| LevelUp-Journey/Landing-Page | feature/add-section2 | 08c9e34 | feat: initialize Astro project with Tailwind CSS and create header component | - Added package.json for project configuration and dependencies.<br>- Included global styles with Tailwind CSS setup.<br>- Created Header component with navigation icons.<br>- Developed main index page structure.<br>- Added various asset images for header and main content.<br>- Configured TypeScript settings for the project. | 2025-09-30 14:47:53 |

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited On (Date) |
| ---------- | ------ | --------- | -------------- | ------------------- | ------------------ |
| Microservice-ClassActivities | feature/add-java-version | 07a3536c0926163eace8dba107aecc390ea8440a | chore: Update Java version to 24 in pom.xml |  | 2025-10-06 11:34:34 -0500 |
| Microservice-ClassActivities | develop | 3fec302682a189b8a10e5ad98a68fd5c1ea82ee6 | Merge pull request #3 from LevelUp-Journey/feature/add-documentation | Feature/add documentation | 2025-10-06 11:21:56 -0500 |
| Microservice-ClassActivities | feature/add-documentation | 2c8fc4075e6395c8ff5f98fccffa56dfd18f5601 | refactor: Organize domain model classes into entities and value objects |  | 2025-10-04 08:44:24 -0500 |
| Microservice-ClassActivities | feature/add-documentation | c27337167508c6301f71151161b0569495ded2ec | chore: Remove SpringDoc OpenAPI configuration from application.yml |  | 2025-10-03 02:08:01 -0500 |
| Microservice-ClassActivities | feature/add-documentation | 1fcbcf4cf0520c79ddcad2b1e859fcd65d0904ef | feat: Add comprehensive API documentation for Class Activities microservice |  | 2025-10-03 01:48:29 -0500 |
| Microservice-ClassActivities | feature/add-documentation | 3a2c71eda7c097578ab262cdc1d4c92cce39ef99 | Refactor user ID type from Long to String across multiple DTOs and commands | Updated AddQuestionRequest, CreateQuizRequest, CreateSessionRequest, JoinSessionRequest, SubmitAnswerRequest, UpdateQuestionRequest, UpdateQuizRequest, ParticipantJoinMessage, ParticipantJoinedMessage to use String for user IDs instead of Long. Modified LiveSessionApplicationService methods to accept String user IDs and adjusted related logic. Changed LiveSession domain model to handle String user IDs in events and methods. Updated Quiz management commands and query handlers to reflect the new user ID type. Adjusted ReportsApplicationService to accept String user IDs. Refactored UserId class to support UUID and String formats for user IDs. Cleaned up OpenApiConfig for better clarity and removed unnecessary fields. | 2025-10-03 01:35:05 -0500 |
| Microservice-ClassActivities | develop | 41db8f5c9a44be1405e39b2ed22986bb826627c9 | Merge pull request #2 from LevelUp-Journey/feature/add-role-verification | feat: Implement role validation middleware and security annotations f… | 2025-10-03 01:12:04 -0500 |
| Microservice-ClassActivities | feature/add-role-verification | e8c1bbf3fd74c1e3b2735c03eadc77c4484f858f | feat: Implement role validation middleware and security annotations for quiz management |  | 2025-10-03 01:10:32 -0500 |
| Microservice-ClassActivities | develop | fc9c5b0f875ed1f81c416081914c106c0bfbac12 | Merge pull request #1 from LevelUp-Journey/feature/dependencies-configuration | Feature/dependencies configuration | 2025-10-02 21:18:30 -0500 |
| Microservice-ClassActivities | feature/dependencies-configuration | 785a1e39b6c6c10687a44c05b8778bf474c743a9 | feat: Implement Session Report and Question Result entities with repository and service layers | Added `QuestionResult` entity to track question statistics in a session. Added `SessionReport` entity to aggregate session participation and results. Created `SessionReportRepository` interface for data access operations. Implemented `JpaSessionReportRepository` for JPA-based persistence. Developed `ReportCsvExportService` for exporting session reports to CSV format. Developed `ReportExcelExportService` for exporting session reports to Excel format. Introduced domain event handling with `DomainEvent`, `BaseDomainEvent`, and event publishing infrastructure. Added user role management with `UserRole` enum and `UserId` value object. Configured WebSocket for real-time communication in session activities. Updated application configuration for database and WebSocket settings. | 2025-10-02 15:03:33 -0500 |
| Microservice-ClassActivities | feature/dependencies-configuration | a6e081cb51b91766ad0ecc283c3ab7941e895e5a | chore: add websocket and validation dependencies to pom.xml |  | 2025-10-02 14:08:46 -0500 |
| Microservice-ClassActivities | feature/dependencies-configuration | 8b14ab41e2b647e7fdde5ece094d050b04b119e9 | chore: add initial todo list for application requirements |  | 2025-10-02 14:08:44 -0500 |
| Microservice-ClassActivities | main | aa5d587bb6095e772a95202182b0601862a236a7 | chore: first commit |  | 2025-10-02 08:52:24 -0500 |

# Git Commits History - Microservice-IAM

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited On (Date) |
| ---------- | ------ | --------- | -------------- | ------------------- | ------------------ |
| Microservice-IAM | develop | 3529a89 | Merge pull request #23 from LevelUp-Journey/feature/add-role-to-token | feat: add user object support for JWT token generation | 2025-10-09 01:17:56 |
| Microservice-IAM | feature/add-role-to-token | fed0bd4 | feat: add user object support for JWT token generation | | 2025-10-08 18:29:07 |
| Microservice-IAM | develop | 87fd3a6 | Merge pull request #22 from LevelUp-Journey/feature/add-fix-front | fix: update OAuth2 redirect URIs and CORS allowed origins for local development | 2025-10-08 15:17:44 |
| Microservice-IAM | feature/add-fix-front | cd9603e | fix: update OAuth2 redirect URIs and CORS allowed origins for local development | | 2025-10-08 15:15:34 |
| Microservice-IAM | develop | 6c280c0 | Merge pull request #21 from LevelUp-Journey/feature/add-callbackrender | fix: update OAuth2 redirect URIs to use production URLs | 2025-10-08 14:40:41 |
| Microservice-IAM | feature/add-callbackrender | 7bea4c8 | fix: update OAuth2 redirect URIs to use production URLs | | 2025-10-08 14:39:48 |
| Microservice-IAM | develop | 660888a | Merge pull request #20 from LevelUp-Journey/feature/add-topic-auth-register | feat: add Kafka topic configuration for user registration | 2025-10-08 03:02:01 |
| Microservice-IAM | feature/add-topic-auth-register | 0e99f11 | feat: add Kafka topic configuration for user registration | | 2025-10-08 03:01:34 |
| Microservice-IAM | develop | 563d18f | Merge pull request #19 from LevelUp-Journey/feature/add-kafka-azure | Feature/add kafka azure | 2025-10-08 02:55:14 |
| Microservice-IAM | feature/add-kafka-azure | 4c2efcf | fix: remove default Kafka bootstrap server URL to use environment variable | | 2025-10-08 02:53:15 |
| Microservice-IAM | feature/add-kafka-azure | dbc8a81 | fix: update Kafka bootstrap server URL to use a specific IP address | | 2025-10-08 02:49:17 |
| Microservice-IAM | kafka-azure | 4cebd1c | Merge pull request #18 from LevelUp-Journey/feature/add-fix-ui | feat: add redirect from root path to Swagger UI in WebConfiguration | 2025-10-08 00:54:32 |
| Microservice-IAM | feature/add-fix-ui | feb856e | feat: add redirect from root path to Swagger UI in WebConfiguration | | 2025-10-08 00:53:50 |
| Microservice-IAM | develop | 63ffa41 | Merge pull request #17 from LevelUp-Journey/feature/add-docker-settings | fix: update Dockerfile to use environment variable for port and improve health check configuration | 2025-10-08 00:34:28 |
| Microservice-IAM | feature/add-docker-settings | 7015cd9 | fix: update Dockerfile to use environment variable for port and improve health check configuration | | 2025-10-08 00:33:54 |
| Microservice-IAM | develop | ac8a645 | Merge pull request #16 from LevelUp-Journey/feature/add-kafka-profile | feat: add Kafka dependency and configuration to application properties | 2025-10-08 00:07:31 |
| Microservice-IAM | feature/add-kafka-profile | 4db0650 | feat: add Kafka dependency and configuration to application properties | | 2025-10-08 00:06:46 |
| Microservice-IAM | feature/add-kafka-config | fde1fc9 | Merge pull request #15 from LevelUp-Journey/feature/add-fix-roles | fix: rename ROLE_INSTRUCTOR to ROLE_TEACHER in Roles enum for consistency | 2025-10-06 16:52:31 |
| Microservice-IAM | feature/add-fix-roles | 6a4ca58 | fix: rename ROLE_INSTRUCTOR to ROLE_TEACHER in Roles enum for consistency | | 2025-10-06 16:51:32 |
| Microservice-IAM | develop | c42aaa6 | Merge pull request #14 from LevelUp-Journey/feature/add-security-patterns | Feature/add security patterns | 2025-09-17 19:24:05 |
| Microservice-IAM | feature/add-security-patterns | bcc59b7 | refactor: remove Profiles module and related services, streamline OAuth2 user handling | | 2025-09-16 13:50:41 |
| Microservice-IAM | feature/add-security-patterns | 85e33c0 | feat: implement refresh token functionality and update token handling in authentication flow | | 2025-09-05 12:01:36 |
| Microservice-IAM | develop | e368638 | Merge pull request #13 from LevelUp-Journey/feature/fix-frontend-redirection | feat: add health check endpoint and update OAuth2 redirect URIs | 2025-09-05 04:02:16 |
| Microservice-IAM | feature/fix-frontend-redirection | bbec510 | feat: add health check endpoint and update OAuth2 redirect URIs | | 2025-09-05 04:01:40 |
| Microservice-IAM | develop | c745d03 | Merge pull request #12 from LevelUp-Journey/feature/add-refactor-profiles | Feature/add refactor profiles | 2025-09-05 00:44:19 |
| Microservice-IAM | feature/add-refactor-profiles | 67cce1e | feat: Refactor User model to use value objects for email and password, update related repositories and resources | | 2025-09-04 17:57:34 |
| Microservice-IAM | feature/add-refactor-profiles | ef664cd | feat: Implement OAuth2 user info extraction and profile creation flow | | 2025-09-04 17:21:42 |
| Microservice-IAM | feature/add-refactor-profiles | 8713f3b | feat: Refactor profile creation to remove address fields and include profile URL | | 2025-09-04 16:56:31 |
| Microservice-IAM | feature/add-refactor-BC | 21fea63 | Merge pull request #11 from LevelUp-Journey/feature/add-refactor-BC | Feature/add refactor bc | 2025-09-04 13:43:02 |
| Microservice-IAM | feature/add-refactor-BC | 10a953c | feat: Refactor user authentication to use email_address instead of username across the application | | 2025-09-04 13:41:37 |
| Microservice-IAM | feature/add-refactor-BC | 253899c | Refactor user authentication to use email_address instead of username | Updated User entity to replace username with email_address. Modified UserQueryService to handle GetUserByEmail_addressQuery. Created new GetUserByEmail_addressQuery class. Removed GetUserByUsernameQuery class. Updated SignInCommand and SignUpCommand to use email instead of username. Adjusted UserRepository methods to find users by email_address. Refactored UserDetailsServiceImpl to load user by email_address. Updated OAuth2AuthenticationSuccessHandler to extract and use email_address. Changed Profile entity and related services to use username instead of email. Removed EmailAddress value object and introduced Username value object. Updated application properties for OAuth2 scopes to use email_address. | 2025-09-04 13:09:50 |
| Microservice-IAM | develop | a7b58f4 | Merge pull request #10 from LevelUp-Journey/feature/add-refactor-BC | Feature/add refactor bc | 2025-09-04 12:11:07 |
| Microservice-IAM | feature/add-refactor-BC | 57c38b0 | feat: Enhance OAuth2 authentication flow and user management features | Implement OAuth2 success and failure handlers for improved authentication handling. Add support for OAuth2 login and logout endpoints in AuthenticationController. Introduce HttpCookieOAuth2AuthorizationRequestRepository for managing OAuth2 requests via cookies. Update User and SignUpResource to simplify role management. Modify application properties for clearer OAuth2 redirect URIs. Refactor user resource and command transformation logic to align with new role handling. | 2025-09-04 12:09:47 |
| Microservice-IAM | feature/add-refactor-BC | 96a4594 | feat: Implement Profile Management Features | Added ProfileCommandServiceImpl for handling profile creation commands. Introduced ProfileQueryServiceImpl for querying profiles by ID and email. Created Profile aggregate to encapsulate profile data and behavior. Defined CreateProfileCommand for encapsulating profile creation data. Implemented query models: GetAllProfilesQuery, GetProfileByEmailQuery, and GetProfileByIdQuery. Developed value objects: EmailAddress, PersonName, and StreetAddress for better data encapsulation. Established ProfileRepository for database interactions with profiles. Created ProfilesContextFacade interface for profile-related operations. Developed ProfilesController for RESTful API endpoints for profile management. Added resource classes: CreateProfileResource and ProfileResource for API data transfer. Implemented transformation classes for converting between resources and domain models. Updated AuditableAbstractAggregateRoot and AuditableModel for UUID-based ID generation. Removed unused JPA configuration classes. Enhanced CORS configuration for the application. Updated application properties for JWT authorization configuration. | 2025-09-04 08:19:10 |
| Microservice-IAM | develop | f269d84 | Merge pull request #9 from LevelUp-Journey/feature/add-configuration-for-api-gateway | Feature/add configuration for api gateway | 2025-09-02 18:18:22 |
| Microservice-IAM | feature/add-configuration-for-api-gateway | aead138 | feat: Update OAuth2 redirect URIs to use GATEWAY_URL and add server port configuration | | 2025-09-02 18:17:52 |
| Microservice-IAM | feature/add-configuration-for-api-gateway | c90e25b | feat: Update security configuration to permit access to Swagger/OpenAPI endpoints via authentication path | | 2025-09-02 18:17:47 |
| Microservice-IAM | feature/add-configuration-for-api-gateway | af3ae71 | feat: Implement CommandLineRunner to display dynamic Swagger UI URL based on server port and path | | 2025-09-02 18:17:42 |
| Microservice-IAM | stash | 7c21c34 | WIP on develop: f39c4af Merge pull request #7 from LevelUp-Journey/hotfix/2.0.0 | | 2025-09-02 18:14:05 |
| Microservice-IAM | stash | 7ad8a64 | index on develop: f39c4af Merge pull request #7 from LevelUp-Journey/hotfix/2.0.0 | | 2025-09-02 18:14:05 |
| Microservice-IAM | develop | 87cbeda | Merge pull request #8 from LevelUp-Journey/feature/add-cors | feat: Enhance CORS configuration with dynamic properties for origins, methods, headers, credentials, and max age | 2025-09-02 16:19:41 |
| Microservice-IAM | feature/add-cors | 1e515ac | feat: Enhance CORS configuration with dynamic properties for origins, methods, headers, credentials, and max age | | 2025-09-02 16:18:06 |
| Microservice-IAM | main | f39c4af | Merge pull request #7 from LevelUp-Journey/hotfix/2.0.0 | feat: Add RootController to redirect root path to Swagger UI | 2025-09-01 07:24:59 |
| Microservice-IAM | hotfix/2.0.0 | bcb99b2 | feat: Add RootController to redirect root path to Swagger UI | | 2025-09-01 07:24:30 |
| Microservice-IAM | revert-hotfix-2.0.0 | a188c7d | Revert "Merge pull request #6 from LevelUp-Journey/Hotfix/2.0.0" | This reverts commit c2d16002039207ace63583803943135ec906c75a, reversing changes made to 581de05b96ba6dd12866115d603a2fb36e4ed615. | 2025-08-31 15:50:56 |
| Microservice-IAM | develop | c2d1600 | Merge pull request #6 from LevelUp-Journey/Hotfix/2.0.0 | feat: Remove OAuth2 success handler and add root redirect to Swagger UI | 2025-08-31 15:20:54 |
| Microservice-IAM | Hotfix/2.0.0 | 3f005b5 | feat: Remove OAuth2 success handler and add root redirect to Swagger UI | | 2025-08-31 15:20:32 |
| Microservice-IAM | develop | 581de05 | Merge pull request #5 from LevelUp-Journey/hotfix/1.0.0 | Hotfix/1.0.0 | 2025-08-31 15:09:03 |
| Microservice-IAM | hotfix/1.0.0 | 7e9ad0d | feat: Enable disabling of Swagger default URL in OpenAPI configuration | | 2025-08-31 15:08:45 |
| Microservice-IAM | hotfix/1.0.0 | 159a0dd | feat: Allow public access to the root path in security configuration | | 2025-08-31 15:08:42 |
| Microservice-IAM | develop | e7ae660 | Merge pull request #4 from LevelUp-Journey/release/1.0.0 | Release/1.0.0 | 2025-08-31 14:43:14 |
| Microservice-IAM | release/1.0.0 | 4c90afa | Merge pull request #3 from LevelUp-Journey/feature/add-RoleManagementService | Feature/add role management service | 2025-08-31 14:42:26 |
| Microservice-IAM | feature/add-RoleManagementService | 1d64215 | feat: Add Dockerfile and .dockerignore for containerization; update validation constraints in user-related resources | | 2025-08-31 14:41:01 |
| Microservice-IAM | feature/add-RoleManagementService | 7a8a169 | Refactor IAM and Profile integration for username and profile updates | Updated AccountCommandServiceImpl to handle username sync with Profile context more gracefully, logging warnings instead of throwing exceptions. Enhanced AccountContextualCommandService to check for existing usernames across accounts, excluding the current account. Added new audit method in IamAuditService for external identity updates. Introduced update methods in ExternalIdentity for name and avatar changes. Updated IamAudit to include EXTERNAL_IDENTITY_UPDATED action. Modified OAuth2AuthenticationSuccessHandler and SecurityConfiguration to use new API paths for OAuth2 success and error handling. Added new query method in AccountRepository to check for existing usernames excluding the current account. Refactored ExternalIdentityRepository to use custom queries for fetching external identities. Expanded IamContextFacade to include external identity profile updates. Enhanced AuthenticationController to handle user data retrieval and logout functionality. Removed redundant OAuth2CallbackController and integrated its functionality into AuthenticationController. Updated UserProfileController to sync profile changes with IAM context. Adjusted application properties to reflect new API paths for OAuth2 redirects. | 2025-08-29 12:53:19 |
| Microservice-IAM | feature/add-RoleManagementService | c06cc79 | feat: Refactor account management services and introduce role management | Added AccountContextualCommandService to handle IAM commands with user agent tracking. Introduced RoleManagementService for managing role entities and conversions. Implemented RoleSeederService to seed fixed roles (STUDENT, ADMIN, INSTRUCTOR) at application startup. Updated AccountCommandServiceImpl to utilize RoleManagementService for role handling. Enhanced UserProfileCommandServiceImpl to sync username changes with IAM context. Created ProfileContextFacade and its implementation for communication between IAM and Profile contexts. Refactored Account and Role classes to improve role handling and entity relationships. Updated AuthenticationController to use AccountContextualCommandService for sign-up and sign-in processes. | 2025-08-29 08:53:18 |
| Microservice-IAM | develop | 8c24a7c | Merge pull request #2 from LevelUp-Journey/feature/add-update-user-profile | Feature/add update user profile | 2025-08-28 21:52:05 |
| Microservice-IAM | feature/add-update-user-profile | 0bbe49f | refactor: Remove unused ObjectMapper and error response handling from OAuth2AuthenticationSuccessHandler | | 2025-08-28 21:51:20 |
| Microservice-IAM | feature/add-update-user-profile | bd7c580 | refactor: Update ProfileAudit and UserProfile to use profileId instead of accountId | | 2025-08-28 21:47:19 |
| Microservice-IAM | feature/add-update-user-profile | 713fd89 | feat: Add support for fetching user profiles by username and enhance JWT handling | | 2025-08-28 21:31:32 |
| Microservice-IAM | feature/add-update-user-profile | d6e86e4 | Refactor IAM module | Updated AccountQueryServiceImpl to remove redundant imports. Introduced AuthenticationService for handling account access and role checks. Enhanced IamAuditService with proper service annotation. Modified Account entity to use bi-directional relationships with Credential, ExternalIdentity, and RoleAssignment. Updated constructors in Account, ExternalIdentity, and RoleAssignment to accept Account references instead of AccountId. Refined event classes to include necessary imports and maintain consistency. Adjusted AccountCommandService and AccountQueryService interfaces for better clarity. Improved OAuth2AuthenticationSuccessHandler and JwtTokenService with necessary imports. Enhanced AuthenticationController and UserProfileController with role-based access control. Updated UpdateUserProfileResource to clarify username immutability. Refined AuditableModel to use UUID for id generation. | 2025-08-28 20:42:18 |
| Microservice-IAM | feature/add-update-user-profile | 3adf2e5 | feat: Implement OAuth2 authentication flow with Google and GitHub, including success and error handling | | 2025-08-28 18:52:03 |
| Microservice-IAM | feature/add-update-user-profile | afe10c6 | feat: Update JPA configuration to include Profile package and clean up unused imports | | 2025-08-28 18:13:38 |
| Microservice-IAM | feature/add-update-user-profile | ad7ce5f | feat: Remove OAuth2Controller and implement user profile management | Deleted OAuth2Controller.java as part of the refactoring process. Added CreateUserProfileFromAccountCommand to handle user profile creation from account data. Implemented UserProfileCommandService with methods for creating and updating user profiles. Introduced UserProfileQueryService with methods for querying user profiles by username and role. Created UserProfileController to manage user profile endpoints, including update and retrieval. Added resources and transformers for user profile data handling in REST API. Implemented pagination for user profile queries. Added ProfileAuditRepository for auditing user profile changes. Created events for user profile creation and updates. | 2025-08-28 18:12:23 |
| Microservice-IAM | feature/add-update-user-profile | 9ff4a86 | feat: Implement User Profile Management | Added UserProfileCommandService and UserProfileQueryService for handling user profile commands and queries. Created UserProfile aggregate with fields for account ID, username, name, avatar URL, and roles. Introduced commands for creating and updating user profiles with validation. Developed query models for retrieving user profiles by account ID and ID, as well as fetching all profiles with pagination and search capabilities. Implemented UserProfileRepository with JPA for database interactions. Enhanced application properties for JWT and OAuth2 configurations. Added necessary value objects for encapsulating account ID, avatar URL, display name, public username, and profile ID. Established auditing mechanism for tracking changes in user profiles. | 2025-08-28 15:49:20 |
| Microservice-IAM | feature/add-update-user-profile | 3be4576 | feat: Enhance user management by adding UserAudit entity, updating user profile commands and resources, and implementing profile update functionality | | 2025-08-28 14:25:33 |
| Microservice-IAM | feature/add-update-user-profile | 8557236 | feat: Add UserAuditRepository for tracking user changes and update UserCommandService to handle profile updates | | 2025-08-28 14:25:25 |
| Microservice-IAM | feature/add-update-user-profile | 3ce935c | feat: Refactor OAuth2 callback handling and improve user session management; add UserAuditService for tracking user changes | | 2025-08-28 14:24:58 |
| Microservice-IAM | develop | c9d1426 | Merge pull request #1 from LevelUp-Journey/feature/add-basic-folder-schema | Feature/add basic folder schema | 2025-08-28 09:20:09 |
| Microservice-IAM | feature/add-basic-folder-schema | 8bcfb01 | feat: Remove IP address tracking from UserSession and related repository query | | 2025-08-27 11:40:34 |
| Microservice-IAM | feature/add-basic-folder-schema | 9e0e481 | feat: Refactor user authentication and registration to use email instead of username, add role management, and enhance OAuth2 session handling | | 2025-08-27 11:27:03 |
| Microservice-IAM | feature/add-basic-folder-schema | e1c0a8f | feat: Enhance OAuth2CommandServiceImpl and UserCommandServiceImpl to support GitHub authentication and session management | | 2025-08-27 00:05:49 |
| Microservice-IAM | feature/add-basic-folder-schema | b9f8f23 | feat: Implement GitHub OAuth2 service for user authentication and update Google OAuth2 redirect URI | | 2025-08-27 00:05:45 |
| Microservice-IAM | feature/add-basic-folder-schema | be04d62 | feat: Add UserEmail and UserSession entities with repositories for email management and session tracking | | 2025-08-27 00:05:31 |
| Microservice-IAM | feature/add-basic-folder-schema | 788bfba | feat: Enhance user repository with custom queries for email checks and add UserSessionRepository for session management | | 2025-08-27 00:05:25 |
| Microservice-IAM | feature/add-basic-folder-schema | 0632777 | feat: Add SignUpUserResource and SignUpUserResourceFromEntityAssembler for user registration handling | | 2025-08-27 00:05:18 |
| Microservice-IAM | feature/add-basic-folder-schema | a3b3ec7 | feat: Update OAuth2 configuration section in application.properties for clarity and organization | | 2025-08-26 23:46:42 |
| Microservice-IAM | feature/add-basic-folder-schema | 1853837 | feat: Refactor user registration to remove role handling and update UserDetailsImpl for password management | | 2025-08-26 19:26:25 |
| Microservice-IAM | feature/add-basic-folder-schema | fb0eb10 | feat: Refactor User model to use AuthIdentity and update roles to STUDENT and TEACHER | | 2025-08-26 19:26:14 |
| Microservice-IAM | feature/add-basic-folder-schema | ed665a0 | feat: Update UserCommandServiceImpl and SignUpCommand for local authentication handling and default role assignment | | 2025-08-26 19:25:46 |
| Microservice-IAM | feature/add-basic-folder-schema | 8de2322 | feat: Add OAuth2CommandServiceImpl and AuthIdentity entity for Google OAuth2 integration | | 2025-08-26 19:25:34 |
| Microservice-IAM | feature/add-basic-folder-schema | 0d87048 | feat: Implement OAuth2 authentication flow with Google integration and external identity management | | 2025-08-26 17:46:57 |
| Microservice-IAM | feature/add-basic-folder-schema | 5218248 | feat: Add Google OAuth2 configuration properties | | 2025-08-26 17:46:51 |
| Microservice-IAM | feature/add-basic-folder-schema | 436ebc1 | feat: Add Google OAuth2 integration with user management and external identity handling | | 2025-08-26 17:46:42 |
| Microservice-IAM | feature/add-basic-folder-schema | c792c3b | feat: Implement IAM module with user and role management | Added RoleRepository and UserRepository for database interactions. Created BearerTokenService and TokenServiceImpl for JWT handling. Developed IamContextFacade to manage user creation and retrieval. Implemented AuthenticationController for sign-in and sign-up endpoints. Added RolesController and UsersController for role and user management endpoints. Defined resource classes for API responses: AuthenticatedUserResource, RoleResource, SignInResource, SignUpResource, UserResource. Created transformation classes for converting between domain models and resource representations. Established auditing capabilities with AuditableAbstractAggregateRoot and AuditableModel. Configured OpenAPI documentation and CORS settings for the application. Introduced custom naming strategy for JPA entities to use snake_case with pluralized table names. | 2025-08-26 14:38:43 |
| Microservice-IAM | feature/add-basic-folder-schema | 381b961 | feat: add Spring Security and validation dependencies, and JWT support | | 2025-08-26 14:33:51 |
| Microservice-IAM | feature/add-basic-folder-schema | 7d3a784 | feat: add basic user model and registration command | | 2025-08-26 12:45:06 |
| Microservice-IAM | feature/add-basic-folder-schema | cc51ccd | chore: first commit | | 2025-08-26 12:32:24 |



#### 4.2.1.4. Testing Suite Evidence for Sprint Review

FOTO DEL JIRA

#### 4.2.1.5. Execution Evidence for Sprint Review

fotos de la landing

#### 4.2.1.6. Services Documentation Evidence for Sprint Review

fotos del swagger

#### 4.2.1.7. Software Deployment Evidence for Sprint Review

fotos de renbder y del repo y del dokcer 

#### 4.2.1.8. Team Collaboration Insights during Sprint

fotos de los repos con los networks 

## 4.3. Validation Interviews

### 4.3.1. Diseño de Entrevistas

### 4.3.2. Registro de Entrevistas

### 4.3.3. Evaluaciones según heurísticas
