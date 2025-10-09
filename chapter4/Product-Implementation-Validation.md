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

## 4.2. Landing Page & Mobile Application Implementation

### 4.2.1. Sprint n

#### 4.2.1.1. Sprint Planning n

#### 4.2.1.2. Sprint Backlog n

#### 4.2.1.3. Development Evidence for Sprint Review

#### 4.2.1.4. Testing Suite Evidence for Sprint Review

#### 4.2.1.5. Execution Evidence for Sprint Review

#### 4.2.1.6. Services Documentation Evidence for Sprint Review

#### 4.2.1.7. Software Deployment Evidence for Sprint Review

#### 4.2.1.8. Team Collaboration Insights during Sprint

## 4.3. Validation Interviews

### 4.3.1. Diseño de Entrevistas

### 4.3.2. Registro de Entrevistas

### 4.3.3. Evaluaciones según heurísticas