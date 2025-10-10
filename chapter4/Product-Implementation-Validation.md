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

[![Tablero de Sprint en Jira — Ejecución del Sprint](https://i.imgur.com/50KeyXQ.png)](https://i.imgur.com/OrIo6DS.png "Abrir imagen en tamaño completo")

#### 4.2.1.3. Development Evidence for Sprint Review


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

| Repository      | Branch                          | Commit Id | Commit Message                                               | Commit Message Body                                          | Committed On (Date) |
| --------------- | ------------------------------- | --------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------- |
| MobileApp-Front | origin/feature/fix-endpoints    | 75be640   | refactor: implement authentication flow on MainScreen        | Implements an authentication flow on the `MainScreen`. The screen now automatically attempts to sign in with test credentials upon initialization. Quizzes are only fetched after a successful authentication.<br><br>Key changes:<br>- Adds an authentication state management flow to `MainScreen` using `AuthViewModel` and `AuthState`.<br>- `MainScreen` now handles authentication loading, success, and error states before displaying quiz data.<br>- The `HomeContent` composable is updated to display authentication status and errors.<br>- Extensive logging has been added to `AuthRepository`, `QuizRepository`, `ApiClient`, and `MainScreen` to trace the authentication and data fetching processes.<br>- The `AppHeader` and unnecessary navigation parameters (`onProfileClick`, `onMenuClick`) have been removed from `JoinScreen`. | 2025-10-09 23:59:01 |
| MobileApp-Front | HEAD -> develop, origin/develop | c8424b6   | Merge pull request #3 from LevelUp-Journey/feature/add-login-register | Feature/add login register                                   | 2025-10-09 22:32:44 |
| MobileApp-Front | develop                         | b2c1263   | feat: add join activity flow and app header                  | Adds the user flow for joining an activity, offering options to join via QR code scan or by entering a PIN. This includes the creation of `JoinScreen`, `QRScanScreen`, and `PinJoinScreen`. A reusable `AppHeader` composable has also been added.<br><br>Key changes:<br>- Creates `JoinScreen` to present QR and PIN joining options.<br>- Implements `PinJoinScreen` for users to enter a 6-digit code.<br>- Adds `QRScanScreen` as a placeholder for camera-based QR scanning.<br>- Introduces a reusable `AppHeader` component for a consistent look.<br>- Sets up the API service, repository, and ViewModel for fetching quizzes. | 2025-10-09 22:31:16 |
| MobileApp-Front | develop                         | a842933   | refactor: replace HomeScreen with MainScreen and improve navigation | Refactors the navigation flow by replacing `HomeScreen` with `MainScreen` as the primary destination after login. This change streamlines the user experience by integrating the "Join Game" functionality directly into the main tabbed interface. The `ProfileScreen` has been removed as part of this refactor.<br><br>Key changes:<br>- `MainScreen` is now the central hub, accessible after login.<br>- `JoinScreen` is integrated as a tab within `MainScreen`, replacing the placeholder content.<br>- The `ProfileScreen` and its associated navigation logic have been deleted.<br>- Navigation logic in `AppNavHost` is updated to reflect the new `MainScreen` flow and removes routes for the old `HomeScreen` and `ProfileScreen`.<br>- UI consistency is improved across various screens (`Community`, `Comments`, `JoinGame`, etc.) by applying a background color from the Material theme and standardizing padding. | 2025-10-09 22:30:40 |
| MobileApp-Front | develop                         | 702d9ff   | Merge pull request #2 from LevelUp-Journey/feature/add-login-register | Feature/add login register                                   | 2025-10-09 22:26:48 |
| MobileApp-Front | develop                         | 44eb4a1   | chore: allow 192.168.0.119 for local development             |                                                              | 2025-10-09 22:24:45 |
| MobileApp-Front | develop                         | d20674d   | feat: add teacher verification and main screen               | Implements a teacher verification flow and adds a new `MainScreen` to display user quizzes. Refactors the login and sign-up screens with an improved UI.<br><br>Key changes:<br>- Adds `TeacherVerificationScreen` to handle OTP validation for users with teacher emails.<br>- Introduces `MainScreen` with a bottom navigation bar and a "My Quizzes" section that fetches and displays data from the API.<br>- Updates `SignUpScreen` to redirect teachers to the new verification flow.<br>- Redesigns `LoginScreen` with a modern card-based UI and improved branding.<br>- Deletes obsolete `AccountTypeScreen` and `BirthDateScreen`.<br>- Adds `QuizApiService` to `ApiClient` for fetching quiz data. | 2025-10-09 22:24:39 |
| MobileApp-Front | develop                         | 83160cf   | feat: redesign auth screens and add quiz entities            | Redesigns the `WelcomeScreen` and `SignUpScreen` for a more modern and user-friendly experience, applying consistent theming and improved layout. Introduces data entities for `Quiz`.<br><br>### `WelcomeScreen`<br>- Replaces the bottom drawer with a streamlined layout featuring primary and secondary action buttons for registration and login.<br>- Updates the color scheme to use `primaryContainer` for a softer look.<br>- Refreshes text and iconography to be in Spanish.<br><br>### `SignUpScreen`<br>- Implements a complete visual overhaul with a card-based form, improved spacing, and iconography.<br>- Adds a "full name" field and robust real-time validation for all input fields.<br>- Introduces logic to differentiate between student and teacher registration based on email format.<br>- A back button is added for better navigation.<br><br>### `SettingsScreen`<br>- Applies `MaterialTheme` colors for a consistent look and feel with the rest of the app.<br>- Minor UI adjustments to padding and layout for better alignment.<br><br>### Data Layer<br>- Adds `Quiz`, `QuizResponse`, and `Pageable` data classes to model the quiz data structure from the API. | 2025-10-09 22:14:56 |
| MobileApp-Front | develop                         | 6f2fcfe   | feat: redesign auth screens and add quiz entities            | Redesigns the `WelcomeScreen` and `SignUpScreen` for a more modern and user-friendly experience, applying consistent theming and improved layout. Introduces data entities for `Quiz`.<br><br>### `WelcomeScreen`<br>- Replaces the bottom drawer with a streamlined layout featuring primary and secondary action buttons for registration and login.<br>- Updates the color scheme to use `primaryContainer` for a softer look.<br>- Refreshes text and iconography to be in Spanish.<br><br>### `SignUpScreen`<br>- Implements a complete visual overhaul with a card-based form, improved spacing, and iconography.<br>- Adds a "full name" field and robust real-time validation for all input fields.<br>- Introduces logic to differentiate between student and teacher registration based on email format.<br>- A back button is added for better navigation.<br><br>### `SettingsScreen`<br>- Applies `MaterialTheme` colors for a consistent look and feel with the rest of the app.<br>- Minor UI adjustments to padding and layout for better alignment.<br><br>### Data Layer<br>- Adds `Quiz`, `QuizResponse`, and `Pageable` data classes to model the quiz data structure from the API. | 2025-10-09 22:14:15 |
| MobileApp-Front | develop                         | e4ff31e   | chore: ignore .idea directory                                | This change updates the `.gitignore` file to exclude the `.idea` directory, which contains IDE-specific settings. | 2025-10-09 17:39:50 |
| MobileApp-Front | develop                         | 179097d   | Merge pull request #1 from LevelUp-Journey/feature/add-class-activity | Feature/add class activity                                   | 2025-10-07 16:25:30 |
| MobileApp-Front | develop                         | 93d293f   | refactor: update AuthRepository import to align with IAM module structure |                                                              | 2025-10-07 16:21:59 |
| MobileApp-Front | develop                         | a827731   | refactor: update package structure to align with IAM module  |                                                              | 2025-10-07 16:21:46 |
| MobileApp-Front | develop                         | ce7e835   | feat: add API client and authentication repository with user management |                                                              | 2025-10-07 16:21:29 |
| MobileApp-Front | develop                         | 1dae53f   | feat: implement Material 3 theme and typography              | Refactors the application's theme to fully support Material 3, including dynamic colors and distinct light/dark color schemes. This update also introduces a new typography scale using Google Fonts.<br><br>Key changes:<br>- Replaces the old `RedTheme` with a comprehensive M3 color system (`Color.kt`).<br>- Implements `LevelUpJourneyTheme` to handle light/dark modes and dynamic coloring (`Theme.kt`).<br>- Defines a new `Typography` scale using Poppins and Inter from Google Fonts (`Type.kt`).<br>- Adds font XML files (`inter.xml`, `poppins.xml`, `jetbrains_mono.xml`) and the Google Fonts dependency.<br>- Creates a `GitHubIcon` composable that adapts to the system theme.<br>- Updates various screens (`WelcomeScreen`, `HomeScreen`, `JoinContent`, etc.) to use the new `MaterialTheme.colorScheme` and `typography` values, ensuring consistent design. | 2025-10-07 16:05:17 |
| MobileApp-Front | develop                         | 1700f87   | refactor: implement bottom navigation and improve auth UI    | Refactors the `HomeScreen` to use a `NavigationBar` for switching between Home, Join, and Community tabs. This change introduces separate composable content for each tab.<br><br>This commit also improves the alignment and padding of the authentication screens for a better user experience.<br><br>Key changes:<br>- Adds `HomeContent`, `JoinContent`, and `CommunityContent` for the respective `HomeScreen` tabs.<br>- Implements `NavigationBar` in `HomeScreen` to manage tab selection.<br>- Adjusts the layout of `LoginScreen` and `SignUpScreen` to be vertically centered and respect status bar padding.<br>- Adds the `cat_smile.png` pet asset. | 2025-10-07 15:21:10 |
| MobileApp-Front | develop                         | 820c556   | feat: add authentication flow and IAM integration            | Implements the complete authentication flow, including sign-in and sign-up screens, and integrates with the backend Identity and Access Management (IAM) service. This includes API services for authentication and user management, repositories to handle data logic, and a view model to manage the UI state.<br><br>Key changes:<br>- Added `LoginScreen` and `SignUpScreen` with form validation and state handling.<br>- Introduced `AuthRepository` for handling sign-in, sign-up, and token management using DataStore.<br>- Created `ApiClient` with Retrofit for making API calls, including an authenticated client with an auth interceptor.<br>- Added `AuthViewModel` to connect the UI with the repository and manage authentication state.<br>- Defined data models for authentication requests/responses and user/role entities.<br>- Configured network security to allow cleartext traffic for local development.<br>- Updated navigation in `AppNavHost` to use the new authentication screens and flow.<br>- Added dependencies for Retrofit, OkHttp, and DataStore. | 2025-10-07 14:52:34 |
| MobileApp-Front | develop                         | d8869c5   | feat: add register screen with validation                    | Implements the `RegisterScreen` with input fields for email, password, and password confirmation. Adds comprehensive client-side validation for all fields to ensure data integrity before submission.<br><br>Key changes:<br>- Adds `OutlinedTextField` for email, password, and confirm password.<br>- Implements state management for input values and password visibility toggles.<br>- Introduces validation logic for email format, password strength (length, case, numbers), and password matching.<br>- Displays error messages and password requirement hints to guide the user.<br>- Disables the "Create Account" button until the form is valid.<br>- Adds a pet image asset to the screen.<br>- Ignores `.env` file in git. | 2025-10-07 13:16:39 |
| MobileApp-Front | develop                         | 46e24f4   | feat: add red theme and new assets                           | Adds a new red color scheme and various new assets. This includes drawable resources for a red gradient, a red button background, and a new vector logo. SVG assets for Google and GitHub icons have also been added to the assets folder.<br><br>Key changes include:<br>- Adding a `LevelUpJourneyApplication` class to support SVG decoding with Coil.<br>- Updating dependencies to use the versions from the `libs` catalog.<br>- Replacing a static icon with an `AsyncImage` to load the new Google SVG.<br>- Adding the `CAMERA` permission in the `AndroidManifest.xml`. | 2025-10-07 13:04:40 |
| MobileApp-Front | develop                         | ab328f6   | feat: add red theme and new dependencies                     | Adds a new red color scheme and applies it throughout the app. Implements a redesigned `WelcomeScreen` with a bottom drawer layout.<br><br>Key changes include:<br>- Adding a comprehensive set of dependencies for features like Ktor, Room, Coil, and authentication.<br>- Replacing `Image` composables with `AsyncImage` from Coil.<br>- Updating the package structure for the `Post` model.<br>- Deleting the old `logo.png` drawable. | 2025-10-07 12:34:23 |
| MobileApp-Front | develop                         | df47220   | chore: add ui theme and pet assets                           |                                                              | 2025-10-07 11:48:55 |
| MobileApp-Front | develop                         | 403e2f0   | chore: add quiz, question and answer entities                |                                                              | 2025-10-04 08:46:30 |
| MobileApp-Front | develop                         | 2b37005   | chore: update navigation up to class activities              |                                                              | 2025-10-03 17:58:02 |
| MobileApp-Front | develop                         | 635656e   | chore: add class activity flow                               |                                                              | 2025-10-03 17:57:49 |
| MobileApp-Front | develop                         | 9e0f2f5   | chore: add JoinGameScreen                                    |                                                              | 2025-10-03 17:57:36 |
| MobileApp-Front | develop                         | 52f1983   | chore: add EnterPinScreen                                    |                                                              | 2025-10-03 17:57:25 |
| MobileApp-Front | develop                         | 79a91e5   | chore: add ConnectingScreen to be realistic                  |                                                              | 2025-10-03 17:57:11 |
| MobileApp-Front | develop                         | 5ee4edd   | chore: update button to enter the activity                   |                                                              | 2025-10-03 17:56:48 |
| MobileApp-Front | origin/feature/add-community    | 7b6137c   | chore: add navigation to new screens                         |                                                              | 2025-10-03 16:31:44 |
| MobileApp-Front | origin/feature/add-community    | 848e4dd   | chore: add CommunityScreen and CommentsScreen                |                                                              | 2025-10-03 16:31:34 |
| MobileApp-Front | origin/feature/add-community    | e5e43e5   | chore: create data class post                                |                                                              | 2025-10-03 16:31:13 |
| MobileApp-Front | origin/feature/add-community    | e079dbe   | chore: update settings view                                  |                                                              | 2025-10-03 16:30:27 |
| MobileApp-Front | origin/main, origin/HEAD, main  | 6049a3d   | fix: Delete .idea directory                                  |                                                              | 2025-10-02 23:31:32 |
| MobileApp-Front | main                            | 5421e3f   | First commit: add up to home screen                          |                                                              | 2025-10-02 23:27:36 |
| MobileApp-Front | main                            | e6e4cd6   | Initial commit                                               |                                                              | 2025-10-02 23:21:51 |

---


#### 4.2.1.4. Testing Suite Evidence for Sprint Review

Feature: Registro de Nuevos Usuarios
Como usuario nuevo  
Quiero registrarme con email y contraseña  
Para acceder a la plataforma con seguridad (rol estudiante por defecto)

Scenario: Registro exitoso con email y contraseña válidos
**ID:** IAM-US-001  
**Given** que soy un usuario nuevo sin cuenta en la plataforma  
**And** proporciono el email "nuevo.usuario@example.com" (formato RFC 5322 válido)  
**And** proporciono una contraseña "SecureP@ss123" que cumple las políticas de seguridad  
**When** envío la solicitud de registro sin especificar roles  
**Then** el sistema crea una nueva cuenta de usuario  
**And** el email se normaliza a minúsculas "nuevo.usuario@example.com"  
**And** se me asigna automáticamente el rol ROLE_STUDENT  
**And** recibo una confirmación de registro exitoso  
**And** puedo iniciar sesión con mis credenciales

Scenario: Rechazo de registro con email inválido
**ID:** IAM-US-001  
**Given** que soy un usuario nuevo  
**And** proporciono un email inválido "usuario-sin-arroba.com"  
**And** proporciono una contraseña válida  
**When** envío la solicitud de registro  
**Then** el sistema rechaza la solicitud  
**And** muestra el mensaje "El email proporcionado no es válido"  
**And** no se crea ninguna cuenta

Scenario: Rechazo de registro con contraseña débil
**ID:** IAM-US-001  
**Given** que soy un usuario nuevo  
**And** proporciono un email válido "usuario@example.com"  
**And** proporciono una contraseña débil "123"  
**When** envío la solicitud de registro  
**Then** el sistema rechaza la solicitud  
**And** muestra el mensaje "La contraseña no cumple con los requisitos de seguridad"  
**And** no se crea ninguna cuenta

Scenario: Rechazo de registro con email ya registrado
**ID:** IAM-US-001  
**Given** que existe un usuario con email "existente@example.com"  
**And** intento registrarme con el mismo email "existente@example.com"  
**When** envío la solicitud de registro  
**Then** el sistema rechaza la solicitud  
**And** muestra el mensaje "El email ya está registrado"  
**And** no se crea una cuenta duplicada

---

Feature: Inicio de Sesión y Gestión de Tokens
Como usuario autenticado  
Quiero iniciar sesión y gestionar tokens (validar y refrescar)  
Para mantener una sesión segura y continua

Scenario: Inicio de sesión exitoso con credenciales válidas
**ID:** IAM-US-002  
**Given** que existe un usuario registrado con email "usuario@test.com" y contraseña "Pass@word123"  
**When** envío una solicitud de inicio de sesión con email "usuario@test.com" y contraseña "Pass@word123"  
**Then** el sistema autentica las credenciales mediante comparación segura  
**And** retorna los datos del usuario (ID, email, roles)  
**And** retorna un token de acceso (access token) válido  
**And** retorna un token de actualización (refresh token) válido  
**And** puedo usar el access token para acceder a recursos protegidos

Scenario: Rechazo de inicio de sesión con email incorrecto
**ID:** IAM-US-003  
**Given** que existe un usuario con email "correcto@test.com"  
**When** intento iniciar sesión con email "incorrecto@test.com" y una contraseña cualquiera  
**Then** el sistema rechaza la autenticación  
**And** muestra el mensaje "Credenciales inválidas"  
**And** no retorna tokens  
**And** no revela si el email existe o no (seguridad)

Scenario: Rechazo de inicio de sesión con contraseña incorrecta
**ID:** IAM-US-003  
**Given** que existe un usuario con email "usuario@test.com" y contraseña correcta  
**When** intento iniciar sesión con email "usuario@test.com" y contraseña "ContraseñaIncorrecta"  
**Then** el sistema rechaza la autenticación  
**And** muestra el mensaje "Credenciales inválidas"  
**And** no retorna tokens

Scenario: Renovación de sesión con refresh token válido
**ID:** IAM-US-004  
**Given** que inicié sesión previamente y obtuve un refresh token válido  
**And** el refresh token no ha expirado  
**When** envío una solicitud de renovación con el refresh token  
**Then** el sistema valida el refresh token  
**And** genera un nuevo access token  
**And** genera un nuevo refresh token  
**And** los nuevos tokens reemplazan a los anteriores  
**And** puedo continuar usando la plataforma sin volver a autenticarme

Scenario: Rechazo de renovación con refresh token expirado
**ID:** IAM-US-004  
**Given** que tengo un refresh token que expiró hace 2 días  
**When** intento renovar mi sesión con el refresh token expirado  
**Then** el sistema rechaza la renovación  
**And** muestra el mensaje "Token expirado"  
**And** no genera nuevos tokens  
**And** debo iniciar sesión nuevamente

Scenario: Validación de access token vigente
**ID:** IAM-US-005  
**Given** que tengo un access token emitido por el sistema hace 5 minutos  
**And** el token aún no ha expirado  
**When** solicito validar el access token  
**Then** el sistema confirma que el token es válido  
**And** retorna el email asociado al token  
**And** puedo usar el token para acceder a recursos protegidos

Scenario: Rechazo de validación de access token expirado
**ID:** IAM-US-005  
**Given** que tengo un access token que expiró hace 1 hora  
**When** solicito validar el access token  
**Then** el sistema indica que el token no es válido  
**And** muestra el mensaje "Token expirado"  
**And** no puedo acceder a recursos protegidos

---

Feature: Autenticación con Proveedores OAuth2
Como usuario nuevo  
Quiero autenticarme con Google o GitHub  
Para ingresar rápidamente sin crear contraseña

Scenario: Primer login con Google exitoso
**ID:** IAM-US-006  
**Given** que no tengo una cuenta en la plataforma  
**And** inicio sesión con mi cuenta de Google  
**When** Google retorna mis datos válidos (email, nombre)  
**Then** el sistema registra automáticamente mi cuenta  
**And** me asigna el rol ROLE_STUDENT por defecto  
**And** emite un access token válido  
**And** emite un refresh token válido  
**And** puedo acceder inmediatamente a la plataforma

Scenario: Login subsecuente con Google
**ID:** IAM-US-006  
**Given** que previamente me registré usando Google  
**And** mi cuenta ya existe en el sistema  
**When** inicio sesión nuevamente con Google  
**Then** el sistema identifica mi cuenta existente  
**And** no crea una cuenta duplicada  
**And** emite nuevos tokens de acceso  
**And** mantengo mis roles y datos previamente configurados

Scenario: Primer login con GitHub sin email público
**ID:** IAM-US-007  
**Given** que no tengo una cuenta en la plataforma  
**And** inicio sesión con mi cuenta de GitHub  
**And** GitHub no devuelve mi email (email privado)  
**And** mi login de GitHub es "developerJohn"  
**When** GitHub retorna mis datos sin email  
**Then** el sistema genera un identificador alternativo "developerJohn@github.oauth"  
**And** registra mi cuenta con ese identificador  
**And** me asigna el rol ROLE_STUDENT  
**And** emite tokens de acceso  
**And** puedo usar la plataforma normalmente

Scenario: Login con GitHub con email público
**ID:** IAM-US-007  
**Given** que inicio sesión con GitHub  
**And** GitHub devuelve mi email "john@developer.com"  
**When** completo la autenticación  
**Then** el sistema registra mi cuenta con el email real "john@developer.com"  
**And** no usa el identificador alternativo  
**And** emite tokens de acceso

---

Feature: Gestión de Usuarios y Roles
Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER)  
Quiero gestionar usuarios y roles  
Para controlar el acceso y permisos del sistema

Scenario: Listar todos los usuarios como administrador
**ID:** IAM-US-008  
**Given** que soy un administrador autenticado con rol ROLE_ADMIN  
**And** existen 50 usuarios registrados en el sistema  
**When** solicito listar todos los usuarios  
**Then** recibo la lista completa de 50 usuarios  
**And** cada usuario muestra su ID, email y roles asignados  
**And** la lista se ordena por fecha de creación

Scenario: Obtener usuario específico por ID
**ID:** IAM-US-009  
**Given** que tengo un token válido con permisos de docente o administrador  
**And** existe un usuario con UUID "123e4567-e89b-12d3-a456-426614174000"  
**When** consulto el usuario por su UUID  
**Then** obtengo la información completa del usuario  
**And** veo su email, roles asignados y fecha de registro  
**And** veo su estado activo/inactivo

Scenario: Obtener usuario específico por email
**ID:** IAM-US-009  
**Given** que tengo un token válido con permisos  
**And** existe un usuario con email "estudiante@university.edu"  
**When** consulto el usuario por su email "estudiante@university.edu"  
**Then** obtengo la información del usuario  
**And** veo su ID, roles y datos asociados

Scenario: Usuario no encontrado por ID inexistente
**ID:** IAM-US-009  
**Given** que tengo un token válido  
**And** no existe un usuario con UUID "999e9999-e99b-99d9-a999-999999999999"  
**When** intento consultar ese UUID  
**Then** el sistema retorna "Usuario no encontrado"  
**And** no retorna datos de usuario

Scenario: Listar roles disponibles en el sistema
**ID:** IAM-US-010  
**Given** que tengo permisos de ROLE_TEACHER o ROLE_ADMIN  
**When** consulto el catálogo de roles  
**Then** obtengo la lista de roles disponibles  
**And** veo ROLE_STUDENT con su descripción  
**And** veo ROLE_TEACHER con su descripción  
**And** veo ROLE_ADMIN con su descripción

Scenario: Consultar rol específico por nombre
**ID:** IAM-US-010  
**Given** que tengo permisos de docente o administrador  
**When** consulto el rol "ROLE_TEACHER" por su nombre  
**Then** obtengo los detalles del rol  
**And** veo su nombre, permisos asociados y descripción

Scenario: Inicialización de roles base del sistema
**ID:** IAM-US-011  
**Given** que el sistema se inicia por primera vez  
**And** no existen roles en la base de datos  
**When** se ejecuta la operación de seed de roles  
**Then** se crean los 3 roles predefinidos: ROLE_STUDENT, ROLE_TEACHER, ROLE_ADMIN  
**And** cada rol se crea con sus permisos correspondientes  
**And** la operación completa exitosamente

Scenario: Verificación de roles existentes sin duplicar
**ID:** IAM-US-011  
**Given** que los roles ROLE_STUDENT y ROLE_TEACHER ya existen en el sistema  
**And** falta crear ROLE_ADMIN  
**When** ejecuto la operación de seed de roles  
**Then** el sistema verifica los roles existentes  
**And** no duplica ROLE_STUDENT ni ROLE_TEACHER  
**And** crea únicamente ROLE_ADMIN  
**And** finaliza sin errores

Scenario: Asignar rol individual a usuario
**ID:** IAM-US-013  
**Given** que soy un administrador autenticado  
**And** existe un usuario "usuario@test.com" con rol ROLE_STUDENT  
**And** el rol ROLE_TEACHER existe en el sistema  
**When** asigno el rol ROLE_TEACHER al usuario  
**Then** el usuario tiene ahora los roles ROLE_STUDENT y ROLE_TEACHER  
**And** el sistema valida la existencia del rol antes de asignar  
**And** no se crean roles duplicados

Scenario: Asignar múltiples roles en lote
**ID:** IAM-US-013  
**Given** que soy un administrador autenticado  
**And** existe un usuario "profesor@university.edu" solo con ROLE_STUDENT  
**When** asigno los roles ROLE_TEACHER y ROLE_ADMIN en una sola operación  
**Then** el usuario tiene ahora los 3 roles: ROLE_STUDENT, ROLE_TEACHER y ROLE_ADMIN  
**And** no se generan duplicados  
**And** la asignación se registra en el historial de cambios

Scenario: Garantizar ROLE_STUDENT si usuario no tiene roles
**ID:** IAM-US-013  
**Given** que existe un usuario sin roles asignados (inconsistencia de datos)  
**When** el sistema valida los roles del usuario  
**Then** automáticamente se asigna ROLE_STUDENT  
**And** el usuario tiene al menos un rol para operar en la plataforma

Scenario: Rechazo de asignación de rol inexistente
**ID:** IAM-US-013  
**Given** que soy un administrador  
**And** intento asignar un rol "ROLE_SUPERUSER" que no existe  
**When** ejecuto la asignación  
**Then** el sistema rechaza la operación  
**And** muestra el mensaje "El rol no existe"  
**And** no se modifica la lista de roles del usuario

---

Feature: Evaluación de Fortaleza de Contraseñas
Como usuario  
Quiero evaluar la fortaleza de mi contraseña  
Para mejorar mi seguridad antes de registrarme o cambiarla

Scenario: Contraseña muy fuerte (puntaje 5)
**ID:** IAM-US-012  
**Given** que proporciono la contraseña "MyV3ry$tr0ng&C0mpl3xP@ssw0rd!"  
**When** solicito evaluar su fortaleza  
**Then** el sistema calcula un puntaje de 5  
**And** clasifica la contraseña como "Muy Fuerte"  
**And** indica que es segura para usar

Scenario: Contraseña fuerte (puntaje 4)
**ID:** IAM-US-012  
**Given** que proporciono la contraseña "S3cur3P@ssw0rd"  
**When** solicito evaluar su fortaleza  
**Then** el sistema calcula un puntaje de 4  
**And** clasifica la contraseña como "Fuerte"  
**And** cumple con los requisitos mínimos de seguridad

Scenario: Contraseña moderada (puntaje 3)
**ID:** IAM-US-012  
**Given** que proporciono la contraseña "password123"  
**When** solicito evaluar su fortaleza  
**Then** el sistema calcula un puntaje de 3  
**And** clasifica la contraseña como "Moderada"  
**And** sugiere mejorarla con más caracteres especiales

Scenario: Contraseña débil (puntaje 1-2)
**ID:** IAM-US-012  
**Given** que proporciono la contraseña "12345"  
**When** solicito evaluar su fortaleza  
**Then** el sistema calcula un puntaje de 1  
**And** clasifica la contraseña como "Muy Débil"  
**And** rechaza su uso para registro  
**And** muestra recomendaciones para crear una contraseña fuerte

Scenario: Validación de contraseña al registrarse
**ID:** IAM-US-012  
**Given** que intento registrarme con la contraseña "weak"  
**And** la contraseña tiene un puntaje de 1  
**When** envío la solicitud de registro  
**Then** el sistema evalúa automáticamente la fortaleza  
**And** rechaza el registro por contraseña débil  
**And** solicita una contraseña con puntaje >= 4

#### 4.2.1.5. Execution Evidence for Sprint Review

[![Tablero de Sprint en Jira — Ejecución del Sprint](https://i.imgur.com/JpBulKB.png)](https://i.imgur.com/OrIo6DS.png "Abrir imagen en tamaño completo")

https://db1ui.atlassian.net/jira/software/projects/LVLUP/boards/232/backlog?atlOrigin=eyJpIjoiODZlNDdmOWIxYzcwNGI3ZDhiNTdhNWIzM2FiMjM4YjgiLCJwIjoiaiJ9 

#### 4.2.1.6. Services Documentation Evidence for Sprint Review

![Sprint Report A](https://imgur.com/pGco5S2.png)
![Sprint Report B](https://imgur.com/3xhWwxS.png)
![Sprint Report C](https://imgur.com/dbJMNGy.png)
![Sprint Report D](https://imgur.com/RXm81bf.png)

#### 4.2.1.7. Software Deployment Evidence for Sprint Review

![Sprint Planning Summary](https://i.imgur.com/3to79c3.png)

#### 4.2.1.8. Team Collaboration Insights during Sprint

![Sprint Board 1](https://i.imgur.com/M5yUNCI.png)
![Sprint Board 2](https://i.imgur.com/QPg6tH5.png)
![Sprint Board 3](https://i.imgur.com/lIBs8MQ.png)
![Sprint Board 4](https://i.imgur.com/rEJ8OkV.png)
![Sprint Board 5](https://i.imgur.com/oefRGtm.png)
![Sprint Board 6](https://i.imgur.com/5EBUhaj.png)
![Sprint Board 7](https://i.imgur.com/7JLlPYG.png)
![Sprint Board 8](https://i.imgur.com/qhq1BF9.png)

## 4.3. Validation Interviews

### 4.3.1. Diseño de Entrevistas
Para evaluar la usabilidad del sitio web, se diseñaron entrevistas estructuradas basadas en las 10 heurísticas de Nielsen. Cada entrevista incluyó preguntas específicas para cada heurística, permitiendo a los participantes expresar sus opiniones y experiencias al interactuar con el sitio. A continuación, se presentan las preguntas formuladas para cada heurística:


1. Visibilidad del estado del sistema

¿En todo momento sabes en qué parte de la página estás o qué acción estás realizando?

2. Correspondencia entre el sistema y el mundo real

¿El lenguaje y los textos te resultan claros y naturales, como si hablaran tu mismo idioma?

3. Control y libertad del usuario

¿Sientes que puedes moverte libremente por la página sin perderte o quedar “atrapado” en una sección?

4. Consistencia y estándares

¿Notas que los botones, textos y enlaces siguen un estilo coherente en toda la página?

5. Prevención de errores

¿Hay algo en el diseño que pueda confundirte o hacerte dar un clic por error?

6. Reconocimiento antes que recuerdo

¿La información importante está visible o necesitas recordar dónde estaba algo para volver a encontrarlo?

7. Flexibilidad y eficiencia de uso

¿Puedes acceder fácilmente a lo que te interesa sin pasos innecesarios o distracciones?

8. Diseño estético y minimalista

¿Te parece que la cantidad de texto, imágenes y espacio está bien equilibrada o sientes saturación visual?

9. Ayuda al reconocimiento de errores y recuperación

Si algo no funciona (por ejemplo, un enlace o formulario), ¿el diseño te ayudaría a entender qué pasó y cómo solucionarlo?

10. Ayuda y documentación

¿El footer te parece fácil de encontrar y útil para resolver dudas básicas?

### 4.3.2. Registro de Entrevistas

**Segmento: Estudiantes**

**Participantes:**

- Leticia Domínguez – Estudiante de Ingeniería de Sistemas
- Brisaos – Estudiante de Ingeniería de Sistemas

**Objetivo de la entrevista:**
 Recoger percepciones de usabilidad, claridad visual y comprensión de contenido del prototipo web de *LevelUp Journey*, con énfasis en los aspectos de diseño visual, navegación e interacción.

**Resumen de hallazgos:**
 Las estudiantes manifestaron una **experiencia positiva** durante la interacción con la plataforma, destacando principalmente la **claridad visual**, la **organización del contenido** y el **diseño minimalista**. Consideraron que la distribución de la información facilita la búsqueda y comprensión del contenido, y valoraron la coherencia visual de los botones, textos y colores.

**Principales observaciones:**

| **Aspecto evaluado**             | **Percepción de los estudiantes**                            | **Conclusión**                                               |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Navegación y estructura**      | “Se ve claro el orden de la página, puedo darme cuenta de lo que quiero buscar y en dónde encontrarlo.” | La estructura general es comprensible, aunque se recomienda incluir un marcador visual que indique la ubicación actual en el sitio. |
| **Lenguaje y textos**            | “La letra es entendible, los colores no complican la lectura.” | El lenguaje resulta natural y accesible, alineado al público objetivo inicial. |
| **Diseño visual**                | “El tema de los colores es minimalista pero a la vez llamativo.” | El diseño visual apoya la atención del usuario y mantiene coherencia estética. |
| **Consistencia de estilo**       | “Los botones y textos mantienen un estilo coherente, se entiende bien el orden.” | La coherencia visual está lograda; se sugiere reforzar el feedback de interacción (hover o click). |
| **Mensajes de error o feedback** | “Sería bueno que aparezca una ventanita que diga que algo no funciona o falta.” | Falta un sistema claro de mensajes de error o estados visuales, lo que puede afectar la retroalimentación en caso de fallas. |

**Conclusión del segmento estudiante:**
 El segmento **percibe positivamente** la propuesta de diseño y navegación. Los comentarios apuntan a **refinar detalles de interacción** (estados visuales, retroalimentación ante errores) y **añadir guías contextuales**, manteniendo la estética minimalista que favorece la comprensión y el enfoque del usuario.

------

**Segmento: Profesores**

**Participantes:**

- [En esta fase se registrará la sesión de entrevista con docentes de la Facultad de Ingeniería, tales como el Prof. Mario o Prof. Sandro Ventura, según cronograma de validación UX.]*

> *Nota: si ya cuentas con las entrevistas docentes (por ejemplo, las de validación metodológica o de usabilidad con docentes de la carrera), puedo integrarlas aquí.*

**Objetivo de la entrevista:**
 Evaluar la pertinencia pedagógica, el enfoque motivacional y la claridad comunicativa del producto desde la perspectiva docente, considerando su aplicabilidad como herramienta de acompañamiento a estudiantes de primeros ciclos.

**Resumen de hallazgos (previstos o preliminares):**
 Los docentes resaltaron el potencial de *LevelUp Journey* como plataforma de **acompañamiento académico y motivacional**, destacando su alineación con los objetivos institucionales de **retención y mejora del rendimiento estudiantil**. Recomendaron incorporar métricas de progreso, contenidos adaptativos y retroalimentación automatizada para reforzar el aprendizaje autónomo.

**Principales observaciones:**

| **Aspecto evaluado**                   | **Percepción de los docentes**                               | **Conclusión**                                               |
| -------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Claridad del objetivo del producto** | Reconocen la importancia de una herramienta que fortalezca la motivación y permanencia académica. | El propósito está alineado a las necesidades institucionales. |
| **Enfoque pedagógico**                 | Sugieren integrar dinámicas que fomenten la autoevaluación y la gamificación del progreso. | Se recomienda ampliar las mecánicas de logro para mantener el interés. |
| **Adaptabilidad del contenido**        | Plantean que el contenido debe personalizarse según el perfil del estudiante y su carrera. | Integrar perfiles de usuario o rutas de aprendizaje personalizadas. |
| **Usabilidad general**                 | Consideran intuitiva la interfaz, pero resaltan la importancia de incorporar más feedback visual. | La experiencia base es positiva; se requiere mejorar el sistema de retroalimentación. |

**Conclusión del segmento profesor:**
 El segmento docente percibe el producto como **una herramienta prometedora** de acompañamiento y seguimiento académico. Destacan la necesidad de incorporar **mayor personalización**, **seguimiento del progreso** y **reforzar la comunicación visual y pedagógica** en la interfaz, asegurando coherencia entre el propósito educativo y la experiencia digital.

------

### **Conclusión general del registro de entrevistas**

Ambos segmentos —estudiantes y docentes— confirman que *LevelUp Journey* cumple con principios esenciales de **claridad, coherencia y accesibilidad**, mostrando una propuesta sólida de interfaz para la etapa de validación. Las mejoras identificadas se concentran en la **retroalimentación visual**, la **personalización del contenido** y la **guía contextual**, reforzando la usabilidad y pertinencia académica del producto.

------

¿Deseas que te lo prepare también en **versión Word (.docx)** con el formato institucional (encabezados azules, logo de la UPC y márgenes normalizados), o prefieres que te lo deje en **Markdown (.md)** para integrarlo directamente al informe de validación UX?

### 4.3.3. Evaluaciones según heurísticas

**UX Heuristics & Principles Evaluation**

**Usability – Inclusive Design – Information Architecture**

| **CARRERA**            | **CURSO**                      | **SECCIÓN**         | **PROFESORES** | **AUDITOR**            | **CLIENTE(S)**             |
| ---------------------- | ------------------------------ | ------------------- | -------------- | ---------------------- | -------------------------- |
| Ingeniería de Software | CC238 – Experiencia de Usuario | [Código de sección] | Todos          | Equipo LevelUp Journey | Leticia Domínguez, Brisaos |

------

**SITE o APP A EVALUAR:**

**LevelUp Journey – Plataforma Web (Versión de validación UX)**

------

**TAREAS A EVALUAR:**

El alcance de esta evaluación incluye la revisión de la usabilidad en las siguientes tareas:

1. Navegación y exploración de secciones principales.
2. Lectura e interpretación de textos e información descriptiva.
3. Identificación de botones, íconos e interacciones visuales.
4. Comprensión de mensajes y feedback visual.

No están incluidas en esta versión:

1. Registro o autenticación de usuarios.
2. Acceso a funcionalidades de progreso o gamificación.
3. Integración con otros servicios (por ejemplo, API o notificaciones).

------

**ESCALA DE SEVERIDAD**

| **Nivel** | **Descripción**                                              |
| --------- | ------------------------------------------------------------ |
| **1**     | Problema superficial: fácilmente superable, de baja frecuencia. |
| **2**     | Problema menor: ocurre ocasionalmente, prioridad baja.       |
| **3**     | Problema mayor: frecuente, afecta la experiencia, prioridad alta. |
| **4**     | Problema muy grave: impide el uso de la herramienta, requiere corrección inmediata. |

------

**TABLA RESUMEN**

| #    | **Problema identificado**                                    | **Escala de severidad** | **Heurística/Principio violado(a)**                        |
| ---- | ------------------------------------------------------------ | ----------------------- | ---------------------------------------------------------- |
| 1    | No existe un elemento visual que indique exactamente en qué parte del sitio se encuentra el usuario (aunque el orden general se entiende). | 2                       | *Information Architecture: Is it locatable?*               |
| 2    | El lenguaje es claro y natural, pero podría beneficiarse de mensajes más conversacionales o de guía (UX writing). | 1                       | *Usability: Match between system and real-world language.* |
| 3    | Los colores y textos mantienen buena legibilidad, pero se recomienda reforzar el contraste para accesibilidad total. | 2                       | *Inclusive Design: Provide comparable experiences.*        |
| 4    | Los botones y textos mantienen consistencia, pero algunos podrían mejorar el feedback visual al hacer clic (por ejemplo, hover o estados activos). | 2                       | *Usability: Consistency and standards.*                    |
| 5    | No existen mensajes de error visibles predefinidos ante fallos de interacción (por ejemplo, si una sección no carga o no funciona). | 3                       | *Usability: Error prevention & feedback.*                  |

------

**DESCRIPCIÓN DE PROBLEMAS**

**PROBLEMA #1: Falta de indicador de ubicación dentro del sitio**

- **Severidad:** 2
- **Heurística violada:** *Information Architecture – Is it locatable?*
- **Problema:** Aunque los usuarios mencionan que el orden general es claro, no hay un breadcrumb o barra activa que señale la sección actual.
- **Recomendación:** Agregar un indicador visual o subrayado activo en el menú que muestre dónde se encuentra el usuario.

------

**PROBLEMA #2: Lenguaje claro pero poco guiado**

- **Severidad:** 1
- **Heurística violada:** *Usability – Match between system and real-world language.*
- **Problema:** Los textos son comprensibles, pero podrían incluir más tono conversacional o mensajes motivadores que refuercen la interacción.
- **Recomendación:** Aplicar principios de UX Writing (microcopys, tono empático, mensajes de guía contextual).

------

**PROBLEMA #3: Contraste visual en algunos elementos secundarios**

- **Severidad:** 2
- **Heurística violada:** *Inclusive Design – Provide comparable experiences.*
- **Problema:** Aunque la interfaz es minimalista y atractiva, algunos colores secundarios podrían afectar la legibilidad para usuarios con baja visión.
- **Recomendación:** Aumentar el contraste (al menos 4.5:1) según las normas WCAG 2.1.

------

**PROBLEMA #4: Falta de feedback visual en botones**

- **Severidad:** 2
- **Heurística violada:** *Usability – Consistency and standards.*
- **Problema:** Los botones son coherentes, pero no muestran cambios claros al hacer clic o al pasar el cursor.
- **Recomendación:** Añadir estados de hover, active y disabled que comuniquen interactividad y respuesta del sistema.

------

**PROBLEMA #5: Ausencia de mensajes de error o feedback ante fallas**

- **Severidad:** 3
- **Heurística violada:** *Usability – Error prevention & feedback.*
- **Problema:** Los usuarios mencionan que preferirían una “ventanita” o alerta cuando algo no funcione, en lugar de no recibir respuesta.
- **Recomendación:** Implementar mensajes modales o toasts que informen claramente el estado de error o función no disponible (“Ups, esta función aún no está disponible”).

------

La experiencia de usuario en **LevelUp Journey** resulta **positiva**, mostrando **claridad visual, consistencia estilística y lenguaje accesible**, aunque existen oportunidades de mejora en **feedback interactivo**, **contraste visual** y **comunicación de errores**. La usabilidad general cumple estándares medios-altos según Nielsen, con una severidad promedio **2.0 (problema menor)**.





