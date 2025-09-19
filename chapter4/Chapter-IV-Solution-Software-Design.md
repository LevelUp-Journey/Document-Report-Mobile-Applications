# Capítulo IV: Solution Software Design

## 4.1. Strategic-Level Domain-Driven Design

El **Strategic-Level Domain-Driven Design** constituye la base fundamental para el desarrollo de la aplicación LevelUpJourney. Este enfoque nos permite identificar y definir los límites de los contextos de dominio, establecer las relaciones entre ellos y crear una arquitectura de software sólida que soporte los objetivos del negocio.

En esta fase estratégica, nos enfocamos en:
- **Comprensión profunda del dominio**: Identificación de los procesos de negocio críticos
- **Definición de bounded contexts**: Establecimiento de límites claros entre diferentes áreas funcionales
- **Modelado de relaciones**: Definición de cómo interactúan los diferentes contextos
- **Arquitectura de alto nivel**: Diseño de la estructura general del sistema

### 4.1.1. EventStorming

El **EventStorming** es una técnica de modelado colaborativo que nos permite explorar y comprender el dominio complejo de LevelUpJourney. Esta técnica facilita la identificación de eventos de dominio, comandos, agregados y bounded contexts a través de sesiones colaborativas con expertos del dominio.

#### 4.1.1.1. Candidate Context Discovery

La **Candidate Context Discovery** es el proceso mediante el cual identificamos los posibles bounded contexts dentro del dominio de LevelUpJourney. Este proceso se basa en el análisis de los eventos, comandos y agregados identificados durante las sesiones de EventStorming.


##### Contextos candidatos identificados:
- **Identity and Access Management (IAM)**: Gestión de usuarios, autenticación y autorización
- **API Gateway**: Enrutamiento, seguridad y gestión de APIs
- **Challenges**: Gestión de desafíos y retos académicos
- **Community**: Interacciones sociales, foros y colaboración
- **Code Runner**: Ejecución y evaluación de código
- **Class Activities**: Gestión de actividades académicas y seguimiento del progreso
- **Analytics**: Análisis de datos y métricas para mejorar el rendimiento y la experiencia del usuario
- **User Profile**: Gestión de información personal del usuario

##### Flows de eventos principales:
- **Registro de usuario**: Flujo desde la creación de cuenta
<img src="../chapter4/assets/domain-event-flows/IAM-flow-1.png" alt="IAM Flow 1" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **Publicacion de un Post**: Creacion de un post y aumento de puntos de actividad al profesor que publica
<img src="../chapter4/assets/domain-event-flows/Community-flow-1.png" alt="Community Flow 1" style="display: block; margin: auto; max-width: 100%; height: auto;"/>


- **Crear Analitica cuando un post es visto**: Cada vez que un post es visto, se crea una nueva analitica
<img src="../chapter4/assets/domain-event-flows/Community-flow-2.png" alt="Community Flow 2" style="display: block; margin: auto; max-width: 100%; height: auto;"/>  

- **Crear un Quiz Activity**: Flujo desde la creacion de un quiz activity
<img src="../chapter4/assets/domain-event-flows/Class-Activities-flow-1.png" alt="Class Activities Flow 1" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **Empezar una sesion de clase en vivo**: Flujo desde el inicio de una sesion en vivo
<img src="../chapter4/assets/domain-event-flows/Class-Activities-flow-2.png" alt="Class Activities Flow 2" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **Un participante ingresa mediante QR a una sesion en vivo**: Flujo desde que un participante ingresa a una sesion en vivo mediante QR
<img src="../chapter4/assets/domain-event-flows/Class-Activities-flow-3.png" alt="Class Activities Flow 3" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **El profesor empieza con las preguntas interactivas**: Flujo desde que el profesor inicia las preguntas interactivas
<img src="../chapter4/assets/domain-event-flows/Class-Activities-flow-4.png" alt="Class Activities Flow 4" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **El estudiante responde a una pregunta interactiva**: Flujo desde que el estudiante responde a una pregunta interactiva
<img src="../chapter4/assets/domain-event-flows/Class-Activities-flow-5.png" alt="Class Activities Flow 5" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **El profesor termina una pregunta interactiva**: Flujo desde que el profesor termina una pregunta interactiva
<img src="../chapter4/assets/domain-event-flows/Class-Activities-flow-6.png" alt="Class Activities Flow 6" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **El profesor termina la sesion en vivo**: Flujo desde que el profesor termina la sesion en vivo
<img src="../chapter4/assets/domain-event-flows/Class-Activities-flow-7.png" alt="Class Activities Flow 7" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **El Estudiante empieza a resolver un challenge**: Flujo desde que el estudiante empieza a resolver un challenge
<img src="../chapter4/assets/domain-event-flows/Challenges-flow-1.png" alt="Challenges Flow 1" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

- **El Estudiante envía su solución a un challenge**: Flujo desde que el estudiante envía su solución a un challenge
<img src="../chapter4/assets/domain-event-flows/Challenges-flow-2.png" alt="Challenges Flow 2" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.1.1.2. Domain Message Flows Modeling

El **Domain Message Flows Modeling** mapea cómo los mensajes (eventos, comandos) fluyen entre los diferentes bounded contexts identificados. Este modelado es crucial para entender las dependencias y patrones de comunicación del sistema.

#### 4.1.1.3. Bounded Context Canvases

Los **Bounded Context Canvases** proporcionan una visión detallada de cada contexto delimitado, documentando sus responsabilidades, interfaces, eventos y relaciones con otros contextos.

- **IAM Bounded Context Canvas**
<img src="../chapter4/assets/canvases/IAM-Canvas.png" alt="IAM Bounded Context Canvas" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
- **Challenges Bounded Context Canvas**
<img src="../chapter4/assets/canvases/Challenges-Canvas.png" alt="Challenges Bounded Context Canvas" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
- **Community Bounded Context Canvas**
<img src="../chapter4/assets/canvases/Community-Canvas.png" alt="Community Bounded Context Canvas" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
- **Code Runner Bounded Context Canvas**
<img src="../chapter4/assets/canvases/CodeRunner-Canvas.png" alt="Code Runner Bounded Context Canvas" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
- **Class Activities Bounded Context Canvas**
<img src="../chapter4/assets/canvases/ClassActivitiesManager-Canvas.png" alt="Class Activities Bounded Context Canvas" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
- **Analytics Bounded Context Canvas**
<img src="../chapter4/assets/canvases/Analytics-Canvas.png" alt="Analytics Bounded Context Canvas" style="display: block; margin: auto; max-width: 100%; height: auto;"/>


### 4.1.2. Context Mapping

El **Context Mapping** define explícitamente las relaciones entre los bounded contexts identificados, estableciendo patrones de integración y clarificando las responsabilidades de cada contexto en las interacciones.

### 4.1.3. Software Architecture

La **Software Architecture** traduce el diseño estratégico en una arquitectura técnica concreta, proporcionando los diagramas y especificaciones necesarios para guiar la implementación del sistema LevelUpJourney.

#### Principios arquitectónicos adoptados:

1. **Separación de responsabilidades**: Cada bounded context tiene responsabilidades claras
2. **Bajo acoplamiento**: Minimización de dependencias entre contextos
3. **Alta cohesión**: Elementos relacionados están agrupados en el mismo contexto
4. **Escalabilidad**: Capacidad de escalar contextos independientemente
5. **Mantenibilidad**: Facilidad para realizar cambios y evolucionar el sistema

#### 4.1.3.1. Software Architecture Context Level Diagrams

Los **diagramas de nivel de contexto** proporcionan una vista de alto nivel del sistema LevelUpJourney, mostrando cómo interactúa con usuarios externos y sistemas externos.

<img src="../chapter4/assets/c4/ContextDiagram.png" alt="C4 Context Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

Identificamos que los usuarios quienes van a interactuar con el sistema son 3.
- Student: Estudiante que participa dentro de la plataforma para mejorar sus habilidades de programación
- Teacher: Profesor que crea contenido para que los estudiantes puedan aprender de manera interactiva y dinamica.
- Admin: Administra la plataforma

Como sistemas externos identificamos:
- Google OAuth Provider: Facilita el inicio de sesión de los usuarios 
- Github OAuth Provider: Facilita el inicio de sesión de los usuarios 

#### 4.1.3.2. Software Architecture Container Level Diagrams

Los **diagramas de nivel de contenedor** descomponen el sistema LevelUpJourney en contenedores de alto nivel, mostrando las principales tecnologías y responsabilidades. Este diagrama ilustra la arquitectura distribuida de microservicios adoptada para garantizar escalabilidad, mantenibilidad y separación de responsabilidades.

<img src="../chapter4/assets/c4/ContainerDiagram.png" alt="C4 Container Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

##### Análisis del Container Diagram

El Container Diagram de LevelUpJourney presenta una arquitectura basada en microservicios que separa las responsabilidades y permite un desarrollo y despliegue independiente de cada componente. La arquitectura se estructura en las siguientes capas y elementos:

**Capa de Presentación:**
- **Landing Page**: Página web estática desarrollada con tecnologías web modernas que sirve como punto de entrada público al sistema, presentando información institucional y facilitando el registro inicial de usuarios.
- **Web App**: Aplicación web principal construida con React que proporciona una interfaz rica e interactiva para estudiantes, profesores y administradores. Utiliza tecnologías modernas del frontend para ofrecer una experiencia de usuario fluida.
- **Mobile App**: Aplicación móvil nativa que extiende las funcionalidades principales de la plataforma a dispositivos móviles, permitiendo el acceso ubicuo a las actividades de aprendizaje.

**Capa de Gateway:**
- **API Gateway**: Actúa como punto de entrada único y centralizado para todas las comunicaciones entre las aplicaciones cliente y los microservicios backend. Implementa funcionalidades transversales como autenticación, autorización, rate limiting, logging y enrutamiento inteligente. Esta centralización simplifica la gestión de políticas de seguridad y mejora la observabilidad del sistema.

**Capa de Microservicios:**
La arquitectura adopta un patrón de microservicios especializados, cada uno con su propia base de datos dedicada (Database per Service pattern):

- **IAM Microservice**: Gestiona la identidad y acceso de usuarios, implementando autenticación segura, autorización basada en roles, y integración con proveedores externos como Google OAuth y GitHub OAuth.
- **Community Microservice**: Facilita las interacciones sociales entre usuarios, publicaciones, comentarios y sistemas de puntuación que fomentan la colaboración.
- **Challenges Microservice**: Administra el catálogo de desafíos de programación, incluyendo su creación, categorización, dificultad y evaluación automática de soluciones.
- **Class Activities Microservice**: Coordina las actividades académicas en tiempo real, como sesiones de clase interactivas, quizzes en vivo, y seguimiento del progreso estudiantil.
- **Analytics Microservice**: Recopila, procesa y analiza métricas de uso y rendimiento, proporcionando insights valiosos para la mejora continua de la plataforma.
- **Code Runner Microservice**: Ejecuta y evalúa código de manera segura en un entorno aislado, soportando múltiples lenguajes de programación y proporcionando retroalimentación inmediata.
- **User Profile Microservice**: Mantiene y gestiona la información personal de los usuarios, preferencias, historial académico y configuraciones personalizadas.

**Decisiones Tecnológicas Principales:**
- **Arquitectura de Microservicios**: Permite escalabilidad independiente, despliegues aislados y uso de tecnologías específicas para cada dominio.
- **API Gateway Pattern**: Centraliza la gestión de APIs y simplifica la comunicación cliente-servidor.
- **Database per Service**: Garantiza la autonomía de datos de cada microservicio y evita acoplamiento entre contextos.
- **Comunicación Asíncrona**: Los microservicios se comunican mediante eventos y mensajería asíncrona para mantener bajo acoplamiento.
- **Tecnologías Modernas**: React para frontend web, aplicaciones móviles nativas, y tecnologías cloud-ready para el backend.

**Patrones de Comunicación:**
Los contenedores se comunican siguiendo patrones establecidos:
- **API REST**: Para comunicación síncrona entre aplicaciones cliente y API Gateway.
- **Event-Driven Architecture**: Para comunicación asíncrona entre microservicios mediante eventos de dominio.
- **Service Discovery**: Para el descubrimiento automático de servicios en el entorno distribuido.
- **Circuit Breaker**: Para manejo de fallos y resiliencia en las comunicaciones entre servicios.

Esta arquitectura asegura que LevelUpJourney pueda escalar eficientemente, mantener alta disponibilidad, y evolucionar de manera independiente en cada uno de sus dominios funcionales.

#### 4.1.3.3. Software Architecture Deployment Diagrams

Los **diagramas de despliegue** muestran cómo los contenedores se mapean a infraestructura física o virtual, incluyendo consideraciones de escalabilidad, disponibilidad y seguridad. Este diagrama visualiza la distribución física del sistema LevelUpJourney, destacando cómo los componentes del software se despliegan sobre la infraestructura en la nube y otros entornos de ejecución.

<img src="../chapter4/assets/deployment/DeploymentDiagram.png" alt="Deployment Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

##### Análisis del Deployment Diagram

El Deployment Diagram de LevelUpJourney presenta una arquitectura cloud-native desplegada en **Microsoft Azure**, diseñada para proporcionar alta disponibilidad, escalabilidad automática y seguridad robusta. La distribución física del sistema se organiza en múltiples capas especializadas que optimizan el rendimiento y la gestión operacional.

**Infraestructura Cloud - Microsoft Azure:**

La solución está completamente desplegada en Microsoft Azure, aprovechando sus servicios administrados para reducir la complejidad operacional y mejorar la confiabilidad del sistema. Esta decisión estratégica permite al equipo enfocarse en el desarrollo de funcionalidades de negocio mientras Azure maneja la infraestructura subyacente.

**Arquitectura de Contenedores - Azure Container Instances (ACI):**

Todos los servicios de aplicación se ejecutan en contenedores Docker desplegados en Azure Container Instances, proporcionando:

- **Aislamiento**: Cada servicio opera en su propio contenedor independiente
- **Portabilidad**: Los contenedores pueden moverse entre entornos sin modificaciones
- **Escalabilidad**: Capacidad de escalar horizontalmente según demanda
- **Gestión simplificada**: Despliegue y actualización automatizada de servicios

**Capa de Presentación (Frontend Tier):**

- **Web Server (Docker)**: Aloja múltiples aplicaciones frontend:
  - **Landing Page (Astro)**: Página estática optimizada para SEO y rendimiento
  - **Web App (Next.js)**: Aplicación web principal con SSR/SPA híbrido
  - **Student & Teacher Portal**: Interfaces especializadas para cada tipo de usuario

- **Mobile API Server (Docker)**: Servidor proxy especializado que gestiona las comunicaciones entre la aplicación móvil Flutter y el API Gateway, optimizando el tráfico móvil y proporcionando caché específico.

**Capa de Gateway:**

- **API Gateway (Spring Boot)**: Punto de entrada centralizado que implementa:
  - Enrutamiento inteligente hacia microservicios
  - Autenticación y autorización centralizadas
  - Rate limiting y throttling
  - Logging y monitoreo centralizado
  - Load balancing hacia servicios backend

**Capa de Microservicios (Microservices Tier):**

La arquitectura despliega múltiples microservicios especializados, cada uno en su propio contenedor:

- **IAM Service**: Gestión de identidad y acceso con integración OAuth
- **User Profile Service**: Administración de perfiles de usuario
- **Challenges Service**: Gestión del catálogo de desafíos
- **Community Service**: Funcionalidades sociales y colaborativas
- **Class Activities Service**: Coordinación de actividades académicas
- **Analytics Service**: Procesamiento y análisis de métricas
- **Code Runner Cluster**: Cluster escalable para ejecución de código con múltiples instancias

**Cluster de Code Runner - Escalabilidad Horizontal:**

El servicio Code Runner está diseñado como un cluster horizontalmente escalable con múltiples instancias (CodeRunner 1, 2, ..., N) implementadas en **Go con framework Gin**. Esta arquitectura permite:

- **Auto-scaling**: Escalado automático basado en carga de trabajo
- **Distribución de carga**: Procesamiento paralelo de ejecuciones de código
- **Aislamiento de seguridad**: Cada instancia ejecuta código en entornos aislados
- **Alta disponibilidad**: Tolerancia a fallos con instancias redundantes

**Capa de Datos - Azure Database Services:**

La capa de datos utiliza servicios administrados de Azure Database para garantizar alta disponibilidad y gestión automática:

- **Azure Database for PostgreSQL**: Para la mayoría de microservicios (IAM, User Profile, Challenges, Class Activities, Code Runner, Analytics)
- **MongoDB**: Para el servicio Community, aprovechando la flexibilidad de documentos para datos sociales

**Consideración de Azure Cosmos DB como Alternativa:**

Como parte de la estrategia de optimización en la nube, se puede considerar **Azure Cosmos DB con API de MongoDB** como una evolución natural del actual deployment de MongoDB. Esta migración ofrecería ventajas significativas:

- **Escalabilidad Global**: Distribución automática de datos a nivel mundial con latencia mínima
- **Alta Disponibilidad**: SLA del 99.999% con replicación automática multi-región
- **Gestión Completamente Administrada**: Eliminación de tareas operacionales como patching, backups y monitoreo
- **Escalado Automático**: Ajuste dinámico de throughput basado en demanda real
- **Compatibilidad Total**: API wire-protocol compatible con MongoDB, permitiendo migración sin cambios de código
- **Seguridad Empresarial**: Cifrado en reposo y en tránsito, integración con Azure Active Directory
- **Costo-Beneficio**: Modelo de pricing por consumo que optimiza costos operacionales

La transición sería transparente para la aplicación, manteniendo todas las funcionalidades existentes mientras se obtienen los beneficios de una plataforma cloud-native completamente administrada.

**Infraestructura de Mensajería:**

- **Apache Kafka**: Implementado en contenedor Docker para comunicación asíncrona entre microservicios, facilitando arquitectura orientada a eventos y desacoplamiento temporal.

**Integraciones Externas:**

- **OAuth Providers**: Integración con GitHub OAuth y Google OAuth para autenticación federada
- **Acceso de Usuarios**: Soporte multi-plataforma (Web, Mobile) con conexiones HTTPS seguras

**Decisiones de Tecnología y Justificación:**

1. **Microsoft Azure**: Plataforma cloud robusta con servicios administrados
2. **Docker + ACI**: Containerización para portabilidad y gestión simplificada
3. **Spring Boot**: Framework Java maduro para microservicios empresariales
4. **Next.js**: Framework React con SSR para rendimiento web optimizado
5. **Flutter**: Framework cross-platform para aplicaciones móviles nativas
6. **PostgreSQL**: Base de datos relacional robusta y confiable
7. **MongoDB**: Base de datos NoSQL para flexibilidad en datos sociales
8. **Apache Kafka**: Sistema de mensajería distribuida para comunicación asíncrona
9. **Go + Gin**: Lenguaje de alto rendimiento para ejecución intensiva de código

**Consideraciones de Seguridad:**

- **HTTPS/TLS**: Todas las comunicaciones externas cifradas
- **OAuth 2.0**: Autenticación federada con proveedores confiables
- **Network Isolation**: Servicios internos aislados del acceso directo externo
- **Container Security**: Imágenes Docker escaneadas y actualizadas regularmente
- **Database Security**: Bases de datos administradas con cifrado en reposo y tránsito

**Escalabilidad y Disponibilidad:**

- **Horizontal Scaling**: Microservicios pueden escalar independientemente
- **Auto-scaling**: Code Runner cluster con escalado automático
- **Load Balancing**: API Gateway distribuye carga entre instancias
- **Database Scaling**: Servicios administrados de Azure con escalado automático
- **Geographic Distribution**: Potencial para despliegue multi-región

##### Posibilidades de Mejora

Para fortalecer y optimizar el deployment actual, se identifican las siguientes oportunidades de mejora:

**1. Mejoras en Alta Disponibilidad:**
- **Multi-Region Deployment**: Implementar despliegue en múltiples regiones de Azure para reducir latencia global y proporcionar tolerancia a fallos geográficos
- **Azure Kubernetes Service (AKS)**: Migrar de ACI a AKS para obtener mayor control sobre orquestación, auto-healing y gestión avanzada de contenedores
- **Database Replicas**: Configurar réplicas de lectura geográficamente distribuidas para mejorar rendimiento y disponibilidad de datos

**2. Optimizaciones de Rendimiento:**
- **Content Delivery Network (CDN)**: Implementar Azure CDN para distribución global de contenido estático y reducción de latencia
- **Caching Layer**: Introducir Azure Redis Cache para caché distribuido y mejora de tiempos de respuesta
- **Database Connection Pooling**: Implementar connection pooling avanzado para optimizar conexiones a bases de datos

**3. Mejoras en Seguridad:**
- **Azure Key Vault**: Centralizar gestión de secretos, certificados y claves de cifrado
- **Web Application Firewall (WAF)**: Implementar WAF para protección contra ataques web comunes
- **Azure Security Center**: Integrar monitoreo de seguridad continuo y detección de amenazas
- **Network Security Groups**: Configurar reglas de firewall granulares entre servicios
- **Private Endpoints**: Implementar endpoints privados para comunicación interna segura

**4. Observabilidad y Monitoreo:**
- **Azure Application Insights**: Implementar APM (Application Performance Monitoring) completo
- **Centralized Logging**: Configurar Azure Log Analytics para agregación centralizada de logs
- **Distributed Tracing**: Implementar trazabilidad distribuida para debugging en microservicios
- **Health Checks**: Configurar health checks avanzados y alertas proactivas

**5. Optimizaciones de Costo:**
- **Azure Reserved Instances**: Utilizar instancias reservadas para reducir costos de compute
- **Spot Instances**: Implementar Spot Instances para cargas de trabajo no críticas
- **Auto-scaling Policies**: Refinar políticas de auto-scaling para optimizar costos vs. rendimiento
- **Resource Tagging**: Implementar tagging comprehensive para gestión de costos por proyecto/entorno

**6. DevOps y CI/CD:**
- **Azure DevOps Pipelines**: Implementar pipelines de CI/CD completamente automatizados
- **GitOps**: Adoptar prácticas GitOps para gestión declarativa de infraestructura
- **Blue-Green Deployment**: Implementar estrategias de despliegue sin downtime
- **Infrastructure as Code**: Migrar toda la infraestructura a Terraform o ARM Templates

**7. Escalabilidad Avanzada:**
- **Event-Driven Autoscaling**: Implementar escalado basado en eventos de Kafka
- **Microservices Mesh**: Considerar Service Mesh (Istio) para comunicación inter-servicios avanzada
- **Serverless Components**: Migrar componentes apropiados a Azure Functions para escalado automático
- **Database Sharding**: Implementar sharding horizontal para bases de datos de alto volumen

**8. Backup y Disaster Recovery:**
- **Automated Backups**: Configurar backups automatizados cross-region
- **Disaster Recovery Plan**: Implementar plan de recuperación ante desastres con RTO/RPO definidos
- **Data Replication**: Configurar replicación asíncrona para continuidad de negocio

Estas mejoras proporcionarían una arquitectura de producción robusta, escalable y enterprise-ready, capaz de soportar el crecimiento futuro de LevelUpJourney mientras mantiene altos estándares de rendimiento, seguridad y disponibilidad.

## 4.2. Tactical-Level Domain-Driven Design

### Introducción al Diseño Táctico

El **Tactical-Level Domain-Driven Design** representa la materialización concreta del diseño estratégico definido anteriormente. En esta sección, profundizamos en la implementación específica de cada bounded context identificado, detallando sus capas arquitectónicas, componentes internos y relaciones. Este nivel táctico se enfoca en los patrones de implementación, la organización del código y la estructura interna de cada contexto delimitado, asegurando que el diseño estratégico se traduzca efectivamente en una arquitectura de software robusta y mantenible.

Para el sistema LevelUpJourney, hemos identificado seis bounded contexts principales que cubren las necesidades fundamentales de la plataforma: **IAM** (Identity and Access Management) para la gestión de identidades y autenticación, **API Gateway** como punto de entrada unificado y gestión de APIs, **Community** para las funcionalidades sociales y de comunidad, **Code Runner** para la ejecución y evaluación de código, **Class Activities** para la gestión de actividades académicas y seguimiento del progreso estudiantil, y **Analytics**.

### 4.2.1. Bounded Context: Challenges
#### 4.2.1.1. Domain Layer

## Challenges

### Entities y Aggregates
- **Challenge**  
  Representa el agregado raíz que contiene la información principal de un reto: su identificador, profesor, nombre, descripción, puntos de experiencia, estado, versiones de código y etiquetas.  
- **CodeVersion**  
  Representa una versión de código asociada a un reto. Incluye el lenguaje, código inicial y pruebas.  
- **CodeVersionTest**  
  Define los casos de prueba que deben ejecutarse para validar la versión de código.  

### Value Objects
- **ChallengeId, TeacherId, CodeVersionId, CodeVersionTestId**: identificadores únicos.  
- **ChallengeTag**: etiqueta asociada al reto (id, nombre, color, icono).  
- **ChallengeStatus**: estado de un reto (`DRAFT`, `PUBLISHED`, `HIDDEN`).  
- **CodeLanguage**: lenguaje de programación (`C_PLUS_PLUS`, `JAVASCRIPT`, `PYTHON`).  

### Commands
- **CreateChallengeCommand, UpdateChallengeCommand, PublishChallengeCommand, StartChallengeCommand, AddCodeVersionCommand, UpdateCodeVersionCommand, AddCodeVersionTestCommand, UpdateCodeVersionTestCommand**  
  Representan acciones de modificación del dominio.  

### Queries
- **GetChallengeByIdQuery, GetPublishedChallengesQuery, GetChallengesByTeacherIdQuery, GetAllChallengeTagsQuery, GetCodeVersionByIdQuery, GetCodeVersionsByChallengeIdQuery**  
  Representan consultas para obtener información del dominio.  

### Domain Services
- **ChallengeCommandService, CodeVersionCommandService, CodeVersionTestCommandService, ChallengeQueryService, CodeVersionQueryService**  
  Definen la lógica de aplicación que orquesta la ejecución de los comandos y queries.  


## Reports

### Entities y Aggregates
- **Report**  
  Representa el reporte de una solución enviada por un estudiante, con métricas como pruebas exitosas, tiempo y memoria utilizada.  

### Value Objects
- **SolutionReportId, SolutionId, StudentId**: identificadores únicos.  

### Commands
- **CreateSolutionReportCommand**  
  Comando para generar un nuevo reporte de solución.  

### Queries
- **GetReportsBySolutionIdQuery**  
  Consulta para obtener los reportes de una solución específica.  


## Solutions

### Entities y Aggregates
- **Solution**  
  Representa la solución enviada por un estudiante a un reto específico. Incluye el reto, versión de código, estudiante y detalles de la solución.  
- **SolutionDetails**  
  Objeto que contiene información sobre intentos, código, último intento y estado de la solución.  

### Value Objects
- **SolutionId, ChallengeId, CodeVersionId, StudentId**: identificadores únicos.  
- **SolutionStatus**: estado de la solución (`SUCCESS`, `FAILED`, `MAX_ATTEMPTS_REACHED`).  

### Commands
- **CreateSolutionCommand, UpdateSolutionCommand, SubmitSolutionCommand**  
  Comandos que permiten crear, actualizar o enviar una solución.  

### Queries
- **GetSolutionByIdQuery, GetSolutionsByStudentIdQuery, GetSolutionsByChallengeIdQuery**  
  Consultas para recuperar información de las soluciones.  

### Domain Services
- **SolutionCommandService, SolutionQueryService**  
  Interfaces que definen la lógica de orquestación entre los comandos y consultas del dominio de soluciones.  


#### 4.2.1.2. Interface Layer

## Challenges

### Controllers
- **ChallengesController**  
  Expone endpoints para crear, actualizar, publicar, iniciar y consultar retos.  
- **CodeVersionsController**  
  Expone endpoints para agregar y actualizar versiones de código, así como para consultarlas.  
- **CodeVersionTestsController**  
  Expone endpoints para agregar y actualizar pruebas de las versiones de código.  

### Resources
- **CreateChallengeResource, UpdateChallengeResource, PublishChallengeResource, StartChallengeResource**: recursos de entrada para acciones sobre retos.  
- **AddCodeVersionResource, UpdateCodeVersionResource**: recursos de entrada para manejar versiones de código.  
- **AddCodeVersionTestResource, UpdateCodeVersionTestResource**: recursos de entrada para manejar pruebas de versiones de código.  
- **GetChallengeByIdResource, GetChallengesByTeacherIdResource, GetCodeVersionByIdResource, GetCodeVersionsByChallengeIdResource**: recursos de entrada para parámetros de consultas.  


## Reports

### Controller
- **SolutionReportsController**  
  Expone endpoints para crear reportes de soluciones y consultar reportes por id de solución.  

### Resources
- **CreateSolutionReportResource**: recurso de entrada para crear un reporte de solución.  
- **GetReportsBySolutionIdResource**: recurso de entrada para consultar reportes asociados a una solución.  


## Solutions

### Controller
- **SolutionsController**  
  Expone endpoints para crear, actualizar, enviar y consultar soluciones.  

### Resources
- **CreateSolutionResource, UpdateSolutionResource, SubmitSolutionResource**: recursos de entrada para manipular soluciones.  
- **GetSolutionByIdResource, GetSolutionsByStudentIdResource, GetSolutionsByChallengeIdResource**: recursos de entrada para consultas de soluciones.  


### Challenges Interface
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesInterfaces.png" alt="Challenges Interface Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Interface
<img src="../chapter4/assets/ddd-layers/challenges/SolutionsInterfaces.png" alt="Solutions Interface Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Interface
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportsInterfaces.png" alt="Solution Reports Interface Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.1.3. Application Layer

En la **Application Layer** se gestionan los flujos de procesos del negocio mediante la definición de **Command Handlers** y **Query Handlers**, los cuales materializan las capacidades del bounded context y orquestan las interacciones con el dominio.  

### Challenges
- **Command Handlers**:  
  - `ChallengeCommandServiceImpl` procesa comandos como `CreateChallengeCommand`, `PublishChallengeCommand`, `StartChallengeCommand`, `UpdateChallengeCommand`.  
  - `CodeVersionCommandServiceImpl` procesa comandos como `AddCodeVersionCommand`, `UpdateCodeVersionCommand`.  
  - `CodeVersionTestCommandServiceImpl` procesa comandos como `AddCodeVersionTestCommand`, `UpdateCodeVersionTestCommand`.  

- **Query Handlers**:  
  - `ChallengeQueryServiceImpl` resuelve consultas como `GetChallengeByIdQuery`, `GetPublishedChallengesQuery`, `GetChallengesByTeacherIdQuery`, `GetAllChallengeTagsQuery`.  
  - `CodeVersionQueryServiceImpl` resuelve consultas como `GetCodeVersionByIdQuery`, `GetCodeVersionsByChallengeIdQuery`.  

### SolutionReports
- **Command Handlers**:  
  - `SolutionReportCommandServiceImpl` procesa el comando `CreateSolutionReportCommand`.  

- **Query Handlers**:  
  - `SolutionReportQueryServiceImpl` resuelve consultas como `GetReportsBySolutionIdQuery`.  

### Solutions
- **Command Handlers**:  
  - `SolutionCommandServiceImpl` procesa comandos como `CreateSolutionCommand`, `UpdateSolutionCommand`, `SubmitSolutionCommand`.  

- **Query Handlers**:  
  - `SolutionQueryServiceImpl` resuelve consultas como `GetSolutionByIdQuery`, `GetSolutionsByStudentIdQuery`, `GetSolutionsByChallengeIdQuery`.  


### Challenges Application
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesApplication.png" alt="Challenges Application Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Application
<img src="../chapter4/assets/ddd-layers/challenges/SolutionsApplication.png" alt="Solutions Application Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Application
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportsApplication.png" alt="Solution Reports Application Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>


#### 4.2.1.4. Infrastructure Layer

En la **Infrastructure Layer** se muestran las clases encargadas de conectar la aplicación con servicios externos, particularmente **bases de datos** y la **implementación de los repositorios** definidos en el **Domain Layer**.  

En los diagramas presentados:  

- Para **Challenges**, se definen repositorios especializados (`ChallengeRepository`, `CodeVersionRepository`, `CodeVersionTestRepository`, `ChallengeTagRepository`) que permiten consultar, guardar o eliminar entidades como `Challenge`, `CodeVersion`, `CodeVersionTest` y `ChallengeTag`. Cada repositorio hereda de `JpaRepository`, lo que asegura las operaciones genéricas (CRUD) y a la vez incorpora consultas específicas del dominio (como `findByTeacherId`, `findPublishedChallenges` o `findByCodeVersionId`).  

- Para **SolutionReports**, el `SolutionReportRepository` implementa operaciones de persistencia y consultas específicas relacionadas con reportes (`Report`), vinculando a entidades del dominio como `SolutionId`, `StudentId` y `SolutionReportId`.  

- Para **Solutions**, el `SolutionRepository` también hereda de `JpaRepository` y administra la persistencia de la entidad `Solution`. Ofrece métodos de búsqueda específicos del dominio, como filtrar por estudiante (`findByStudentId`), desafío (`findByChallengeId`) o estado (`findByStatus`).  


### Challenges Infrastructure
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesInfrastructure.png" alt="Challenges Infrastructure Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Infrastructure
<img src="../chapter4/assets/ddd-layers/challenges/SolutionsInfrastructure.png" alt="Solutions Infrastructure Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Infrastructure
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportsInfrastructure.png" alt="Solution Reports Infrastructure Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.1.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/ChallengesComponents.png" alt="C4 Container Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.1.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.1.6.1. Bounded Context Domain Layer Class Diagrams

### Challenges Domain
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesDomain.png" alt="Challenges Domain Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Domain
<img src="../chapter4/assets/ddd-layers/challenges/SolutionsDomain.png" alt="Solutions Domain Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Domain
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportsDomain.png" alt="Solution Reports Domain Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

##### 4.2.1.6.2. Bounded Context Database Design Diagram

### Challenges Database Diagram
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesDomainDatabaseDiagram.png" alt="C4 Container Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Database Diagram
<img src="../chapter4/assets/ddd-layers/challenges/SolutionDomainDatabaseDiagram.png" alt="C4 Container Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Database Diagram
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportDomainDatabase.png" alt="C4 Container Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
















### 4.2.2. Bounded Context: Class Activities
#### 4.2.2.1. Domain Layer

### Value Objects
En los diagramas se definen múltiples objetos de valor que encapsulan identificadores y propiedades inmutables que representan conceptos centrales del dominio:

- **ActivityId, TeacherId, QuestionId, OptionId, SessionId, ParticipantId, AnswerId, CurrentQuestionId**: encapsulan la identidad de cada entidad del dominio asegurando unicidad.
- **Content**: modela el contenido de una pregunta u opción, compuesto por un tipo (`ContentType`) y un valor de texto o imagen.
- **Enums** como `ContentType`, `DifficultyLevel`, `SessionStatus` y `ParticipantStatus` restringen los valores válidos en el dominio para mantener consistencia.

### Aggregates y Entities
El dominio se organiza alrededor de agregados que representan raíces de consistencia y controlan las reglas de negocio internas:

- **QuizActivity (Aggregate Root)**: representa la actividad de un cuestionario creada por un profesor, con metadatos, preguntas asociadas y control de fechas.
- **Question (Entity)**: entidad que pertenece a un `QuizActivity`, define enunciado, puntaje, límite de tiempo, dificultad y sus opciones.
- **Option (Entity)**: define el contenido de cada opción de respuesta y determina si es correcta o no.
- **LiveSession (Aggregate Root)**: representa una sesión en vivo asociada a una actividad y un profesor, gestiona participantes, estado de la sesión y la pregunta actual.
- **Participant (Entity)**: participante de la sesión en vivo, con nombre, puntaje, estado y respuestas asociadas.
- **Answer (Entity)**: respuesta seleccionada por un participante para una pregunta determinada en la sesión.
- **CurrentQuestion (Entity)**: mantiene la pregunta activa en la sesión en vivo junto con tiempos de inicio y fin.

### Commands y Queries
Se definen **comandos** y **consultas** como objetos de transporte que encapsulan intenciones de modificación o lectura del dominio:

- **Commands**: `CreateQuizActivityCommand`, `AddQuestionCommand`, `AddOptionCommand`, `UpdateQuestionCommand`, `CreateLiveSessionCommand`, `JoinSessionCommand`, `LeaveSessionCommand`, `StartSessionCommand`, `LoadQuestionCommand`, `EndCurrentQuestionCommand`, `SendAnswerCommand`, `CloseSessionCommand`.
- **Queries**: `GetQuizActivityByIdQuery`, `GetQuestionsByActivityIdQuery`, `GetOptionsByQuestionIdQuery`, `GetLiveSessionByIdQuery`, `GetParticipantsBySessionIdQuery`, `GetLeaderboardQuery`, `GetCurrentQuestionQuery`, `GetCurrentQuestionDetailsQuery`.

### Domain Services
Se modelan como interfaces que representan contratos para la ejecución de reglas de negocio relacionadas con comandos y consultas:

- **Command Services**: `QuizActivityCommandService`, `QuestionCommandService`, `OptionCommandService`, `LiveSessionCommandService`.
- **Query Services**: `QuizActivityQueryService`, `QuestionQueryService`, `OptionQueryService`, `LiveSessionQueryService`.

Estas interfaces garantizan separación de responsabilidades y un punto claro de interacción con la lógica del dominio.

### Repositories (Abstracciones)
Aunque en los diagramas no se muestran implementaciones específicas de repositorios, se asume la existencia de **interfaces de Repository** en la capa de dominio para la persistencia de agregados como `QuizActivity` o `LiveSession`. Estas actúan como puertos que serán implementados en la capa de infraestructura.

#### 4.2.2.2. Interface Layer


## QuizActivities

### Controllers
- **QuizActivitiesController**  
  Expone endpoints para crear, actualizar y consultar actividades de tipo cuestionario.  
- **QuestionsController**  
  Expone endpoints para agregar, actualizar y consultar preguntas asociadas a una actividad.  
- **OptionsController**  
  Expone endpoints para agregar, actualizar y consultar opciones asociadas a una pregunta.  

### Resources
- **CreateQuizActivityResource, UpdateQuizActivityResource**: recursos de entrada para crear o actualizar actividades de cuestionario.  
- **AddQuestionResource, UpdateQuestionResource**: recursos de entrada para agregar o actualizar preguntas.  
- **AddOptionResource, UpdateOptionResource**: recursos de entrada para agregar o actualizar opciones de una pregunta.  
- **GetQuizActivityByIdResource, GetQuestionsByActivityIdResource, GetOptionsByQuestionIdResource**: recursos de entrada para parámetros de consultas.  

## LiveSessions

### Controller
- **LiveSessionsController**  
  Expone endpoints para gestionar sesiones en vivo: crear, unirse, salir, iniciar, cargar preguntas, terminar preguntas, enviar respuestas, cerrar sesión y realizar consultas asociadas a la sesión en vivo.  

### Resources
- **CreateLiveSessionResource, JoinSessionResource, LeaveSessionResource, StartSessionResource, LoadQuestionResource, EndCurrentQuestionResource, SendAnswerResource, CloseSessionResource**: recursos de entrada para las acciones de gestión de sesiones en vivo.  
- **GetLiveSessionByIdResource, GetParticipantsBySessionIdResource, GetLeaderboardResource, GetCurrentQuestionResource, GetCurrentQuestionDetailsResource**: recursos de entrada para parámetros de consultas relacionadas con sesiones, participantes, ranking y preguntas actuales.  
- **CurrentQuestionResponse**: recurso de salida que representa la pregunta actual activa en la sesión.  


### Activities Manager Interface
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerInterfaces.png" alt="Activities Manager Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Interface
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerInterfaces.png" alt="Class Activity Session Manager Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.3. Application Layer

### QuizActivity
- **Command Handlers**:  
  - `QuizActivityCommandServiceImpl` procesa el comando `CreateQuizActivityCommand`.  
  - `QuestionCommandServiceImpl` procesa los comandos `AddQuestionCommand`, `UpdateQuestionCommand`.  
  - `OptionCommandServiceImpl` procesa el comando `AddOptionCommand`.  

- **Query Handlers**:  
  - `QuizActivityQueryServiceImpl` resuelve consultas como `GetQuizActivityByIdQuery`.  
  - `QuestionQueryServiceImpl` resuelve consultas como `GetQuestionsByActivityIdQuery`.  
  - `OptionQueryServiceImpl` resuelve consultas como `GetOptionsByQuestionIdQuery`.  

### LiveSession
- **Command Handlers**:  
  - `LiveSessionCommandServiceImpl` procesa comandos como `CreateLiveSessionCommand`, `JoinSessionCommand`, `LeaveSessionCommand`, `StartSessionCommand`, `LoadQuestionCommand`, `EndCurrentQuestionCommand`, `SendAnswerCommand`, `CloseSessionCommand`.  

- **Query Handlers**:  
  - `LiveSessionQueryServiceImpl` resuelve consultas como `GetLiveSessionByIdQuery`, `GetParticipantsBySessionIdQuery`, `GetLeaderboardQuery`, `GetCurrentQuestionQuery`, `GetCurrentQuestionDetailsQuery`.  

### Activities Manager Application
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerApplication.png" alt="Activities Manager Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Application
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerApplication.png" alt="Class Activity Session Manager Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.4. Infrastructure Layer

En los diagramas presentados:  

- Para **QuizActivity**, el `QuizActivityRepository` gestiona la entidad `QuizActivity` y permite consultas específicas por `TeacherId`, búsqueda por título y filtrado por fechas de creación.  
  El `QuestionRepository` administra las entidades `Question`, ofreciendo búsquedas por `ActivityId`, dificultad (`DifficultyLevel`) y orden cronológico, además de permitir eliminación en cascada por actividad.  
  El `OptionRepository` gestiona las entidades `Option`, habilitando búsquedas por `QuestionId`, opciones correctas o en orden de creación, así como eliminación de opciones ligadas a una pregunta.  

- Para **LiveSession**, el `LiveSessionRepository` administra sesiones en vivo (`LiveSession`) y permite consultas por `TeacherId`, `ActivityId` y `SessionStatus`.  
  El `ParticipantRepository` gestiona la entidad `Participant`, ofreciendo consultas por `SessionId`, estado del participante (`ParticipantStatus`), orden por puntaje y búsquedas específicas de un participante dentro de una sesión.  
  El `AnswerRepository` se encarga de las entidades `Answer`, habilitando consultas por `SessionId`, `ParticipantId` y `QuestionId`, así como combinaciones entre ellos, además de la eliminación de respuestas por sesión.  
  El `CurrentQuestionRepository` gestiona la entidad `CurrentQuestion`, con búsquedas por `SessionId`, estado activo e incluso consultas globales por preguntas activas, junto con operaciones de eliminación ligadas a una sesión.  

### Activities Manager Infrastructure
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerInfrastructure.png" alt="Activities Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Infrastructure
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerInfrastructure.png" alt="Class Activity Session Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/ClassActivitiesComponent.png" alt="Class Activity Session Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.2.6.1. Bounded Context Domain Layer Class Diagrams

### Activities Manager Domain
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerDomain.png" alt="Activities Manager Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Domain
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerDomain.png" alt="Class Activity Session Manager Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

##### 4.2.2.6.2. Bounded Context Database Design Diagram
### Activities Manager Database Design
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerDomainDatabase.png" alt="Activities Manager Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Database Design
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerDomainDatabase.png" alt="Class Activity Session Manager Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>











### 4.2.3. Bounded Context: Community
#### 4.2.3.1. Domain Layer

### Value Objects
En este dominio se definen objetos de valor que encapsulan identidades y propiedades inmutables:

- **PostId, CommentId, UserId**: identificadores que aseguran unicidad para publicaciones, comentarios y usuarios.
- **Content**: modela el contenido de un post, permitiendo texto y enlaces a medios.
- **CommentContent**: representa el contenido de un comentario, restringido únicamente a texto (sin medios).
- **Auditable**: objeto de valor que centraliza metadatos de auditoría, como fechas de creación y actualización.

### Aggregates y Entities
El núcleo del dominio se estructura en torno a agregados y entidades que reflejan las reglas de negocio:

- **Post (Aggregate Root)**: representa una publicación realizada por un usuario. Contiene contenido, auditoría, comentarios y reacciones de tipo "Like". Expone comportamientos como agregar comentarios y gestionar likes.
- **Comment (Entity)**: comentario asociado a un `Post`, con su propio autor, contenido, auditoría y reacciones de tipo "Like". Incluye operaciones para editar contenido y manejar likes.
- **Like (Entity)**: expresa la interacción de un usuario con un `Post` o `Comment`, registrando la fecha de creación.

### Commands y Queries
Se definen comandos y consultas que encapsulan intenciones del dominio:

- **Commands**: `CreatePost`, `EditPost`, `DeletePost`, `AddComment`, `EditComment`, `DeleteComment`, `LikePost`, `UnlikePost`, `LikeComment`, `UnlikeComment`.
- **Queries**: `GetPostById`, `GetAllPosts`, `GetCommentsByPostId`, `GetCommentById`, `GetLikesByPostId`, `GetLikesByCommentId`.

### Domain Services
El dominio expone interfaces que representan contratos de servicio para procesar comandos y consultas:

- **Command Services**: `PostCommandService` y `CommentCommandService`, responsables de orquestar la creación, edición, eliminación y reacciones sobre publicaciones y comentarios.
- **Query Services**: `PostQueryService` y `CommentQueryService`, dedicados a la recuperación de publicaciones, comentarios y sus interacciones.

### Repositories (Abstracciones)
Aunque no se visualizan en el diagrama, se infiere la necesidad de **interfaces de repositorios** para la persistencia de agregados como `Post` y entidades relacionadas (`Comment`, `Like`), las cuales serán implementadas en la capa de infraestructura.

#### 4.2.3.2. Interface Layer

## Controllers

### **PostsController**
Encargado de gestionar la interacción con publicaciones. Expone operaciones para:
- Crear, editar y eliminar un post.  
- Dar y quitar "like" a una publicación.  
- Consultar publicaciones individuales o en conjunto, así como obtener los likes asociados.  

### **CommentsController**
Encargado de gestionar la interacción con comentarios. Expone operaciones para:
- Agregar, editar y eliminar un comentario.  
- Dar y quitar "like" a un comentario.  
- Consultar comentarios asociados a un post, obtener un comentario por su ID y listar los likes de un comentario.  

## Resources

Los *resources* representan los datos de entrada o parámetros necesarios para invocar las operaciones de los controladores. Se agrupan en tres tipos:

### a. Post Resources
- **CreatePostResource**: contiene autor y contenido para crear un post.  
- **EditPostResource**: datos para modificar el contenido de un post existente.  
- **DeletePostResource**: identificador del post a eliminar.  
- **LikePostResource / UnlikePostResource**: identificador de usuario para dar o quitar "like" a un post.  

### b. Comment Resources
- **AddCommentResource**: autor y contenido para agregar un comentario.  
- **EditCommentResource**: datos para modificar un comentario existente.  
- **DeleteCommentResource**: identificador del comentario a eliminar.  
- **LikeCommentResource / UnlikeCommentResource**: identificador de usuario para dar o quitar "like" a un comentario.  

### c. Query Resources
- **GetPostByIdResource, GetCommentsByPostIdResource, GetCommentByIdResource**: parámetros de consulta por identificador.  
- **GetLikesByPostIdResource, GetLikesByCommentIdResource**: parámetros de consulta para obtener likes asociados a posts o comentarios.  


## Relación entre Controllers y Resources

Los **controllers** utilizan los **resources** como contratos de entrada para garantizar consistencia en los datos recibidos y en las consultas realizadas. De esta manera, el *Interface Layer* actúa como frontera clara entre el cliente (frontend o consumidor externo) y el núcleo del microservicio.  




### Community Manager Interface
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerInterfaces.png" alt="Community Manager Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.3. Application Layer

### Posts
- **Command Handlers**:  
  - `PostCommandServiceImpl` procesa comandos como `CreatePost`, `EditPost`, `DeletePost`, `LikePost`, `UnlikePost`.  

- **Query Handlers**:  
  - `PostQueryServiceImpl` resuelve consultas como `GetPostById`, `GetAllPosts`, `GetLikesByPostId`.  

### Comments
- **Command Handlers**:  
  - `CommentCommandServiceImpl` procesa comandos como `AddComment`, `EditComment`, `DeleteComment`, `LikeComment`, `UnlikeComment`.  

- **Query Handlers**:  
  - `CommentQueryServiceImpl` resuelve consultas como `GetCommentsByPostId`, `GetCommentById`, `GetLikesByCommentId`.  


### Community Manager Application
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerApplication.png" alt="Community Manager Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.4. Infrastructure Layer

En el diagrama presentado:  

- El `PostRepository` gestiona la entidad `Post` y permite consultas por `UserId` (autor), ordenamiento descendente por fecha de creación y búsquedas de texto en el contenido (`findByContentTextContainingIgnoreCase`).  

- El `CommentRepository` administra la entidad `Comment`, habilitando consultas por `PostId`, orden cronológico ascendente, búsquedas por autor (`UserId`) y la eliminación de comentarios asociados a un `PostId`.  

- El `LikeRepository` gestiona la entidad `Like`, ofreciendo operaciones para validar la existencia de un "like" en relación con `PostId` o `CommentId` y un `UserId`, además de contar reacciones y consultar listas de likes asociados. También permite la eliminación de likes por `PostId` o `CommentId`.

### Community Manager Infrastructure
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerInfrastructure.png" alt="Community Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/CommunityComponents.png" alt="Community Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.3.6.1. Bounded Context Domain Layer Class Diagrams

### Community Manager Domain
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerDomain.png" alt="Community Manager Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

##### 4.2.3.6.2. Bounded Context Database Design Diagram

### Community Manager 

<img src="../chapter4/assets/ddd-layers/community/CommunityManagerDomainDatabase.png" alt="Community Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>











### 4.2.4. Bounded Context: Identity and Access Management (IAM)
#### 4.2.4.1. Domain Layer

### Aggregate Roots y Entities
- **User (Aggregate Root)**:  
  Representa al usuario dentro del sistema, encapsulando email, contraseña y conjunto de roles. Expone comportamientos para crear usuarios, asignar roles y validar credenciales.  
  Métodos notables: `addRole`, `getPasswordStrength`, `getEmailAddress`.

- **Role (Entity)**:  
  Define un rol asociado a un usuario. Contiene un identificador único y un nombre tipado con el enum `Roles`. Expone métodos estáticos para validar, convertir y obtener roles por defecto.

### Value Objects
- **EmailAddress**:  
  Garantiza que el correo electrónico del usuario sea tratado como un valor inmutable y validado. Provee métodos de normalización y de extracción de partes (`localPart`, `domainPart`).

- **Password**:  
  Encapsula la contraseña en un objeto seguro, con lógica para evaluar fortaleza y validar seguridad.

- **TokenPair**:  
  Representa el par de tokens (`accessToken` y `refreshToken`) usados en autenticación y gestión de sesiones.

- **OAuth2UserInfo**:  
  Modela los datos básicos de un usuario autenticado a través de un proveedor externo (OAuth2), como nombre, apellidos, perfil y email.

### Enums
- **Roles**:  
  Enum con roles de negocio (`ROLE_STUDENT`, `ROLE_INSTRUCTOR`, `ROLE_ADMIN`). Facilita restricciones y asegura consistencia en asignación de permisos.

### Commands
Se encapsulan intenciones de cambio de estado en el dominio:
- **SignUpCommand**: para registrar un nuevo usuario con email, password y roles.
- **SignInCommand**: para autenticar un usuario con credenciales.
- **SeedRolesCommand**: inicializa los roles básicos en el sistema.

### Queries
Se definen consultas que permiten recuperar información del dominio:
- **GetAllUsersQuery, GetUserByIdQuery, GetUserByEmail_addressQuery**: consultas de usuarios.  
- **GetAllRolesQuery, GetRoleByNameQuery**: consultas de roles.

### Domain Services (Interfaces)
Interfaces que orquestan lógica de negocio más allá de una sola entidad:

- **UserCommandService**: maneja registro (`SignUpCommand`) y autenticación (`SignInCommand`), retornando usuarios o pares de tokens.  
- **UserQueryService**: expone consultas de recuperación de usuarios por id, email o listados.  
- **RoleCommandService**: administra la inicialización de roles (`SeedRolesCommand`).  
- **RoleQueryService**: permite consultas de roles disponibles y búsqueda por nombre.



#### 4.2.4.2. Interface Layer


## 1. Controllers

### **AuthenticationController**
Expone endpoints para:
- Iniciar sesión con credenciales (signIn).  
- Registrar un nuevo usuario (signUp).  
- Validar un token JWT.  
- Refrescar un token de sesión.  

Se apoya en `UserCommandService`, `UserQueryService`, `BearerTokenService` y `TokenService`.  

### **UsersController**
Expone operaciones para:
- Consultar todos los usuarios registrados.  
- Consultar un usuario específico por ID.  

Depende de `UserQueryService`.  

### **RolesController**
Expone un endpoint para listar todos los roles disponibles en el sistema.  
Depende de `RoleQueryService`.  

### **OAuth2Controller**
Controlador especializado en la autenticación con proveedores externos (ej. Google, GitHub).  
Permite:
- Procesar un inicio de sesión exitoso con OAuth2.  
- Manejar errores de autenticación.  
- Extraer datos de usuario desde proveedores externos.  

Se apoya en `UserCommandService`, `UserQueryService`, `RoleQueryService` y `BearerTokenService`.  

## 2. Resources (DTOs)

Los **resources** representan contratos de entrada/salida en la API REST:

- **SignInResource, SignUpResource**: datos de entrada para autenticación o registro.  
- **UserResource**: datos de salida que representan un usuario (id, username).  
- **AuthenticatedUserResource**: datos de salida para un usuario autenticado (incluye token y refresh token).  
- **RoleResource**: datos de salida que representan un rol.  
- **RefreshTokenResource**: datos de entrada para refrescar un token.  

## 3. Transformers

Los **assemblers** traducen entre *Resources* (DTOs) y el dominio:

- **SignInCommandFromResourceAssembler, SignUpCommandFromResourceAssembler**: convierten recursos en comandos de dominio.  
- **UserResourceFromEntityAssembler, AuthenticatedUserResourceFromEntityAssembler, RoleResourceFromEntityAssembler**: convierten entidades del dominio en recursos de salida (DTOs).  

Esto asegura una separación clara entre el *domain model* y la *interface layer*.  

## 4. ACL (Anti-Corruption Layer)

### **IamContextFacade**
Define un punto de acceso controlado para interactuar con el dominio y servicios externos, encapsulando la lógica necesaria para:  
- Crear usuarios (con o sin roles).  
- Consultar información de usuarios por ID o username.  
- Extraer información de usuarios autenticados con OAuth2 (Google, GitHub, etc.).  

El ACL protege al microservicio de dependencias directas con APIs externas, transformando la información en un formato consistente con el dominio IAM.  

## 5. Dependencias con Servicios Externos

### **Domain Services**
- `UserCommandService`: maneja comandos de autenticación y registro de usuarios.  
- `UserQueryService`: provee consultas sobre usuarios (por id, email, etc.).  
- `RoleQueryService`: maneja consultas de roles.  

### **Infrastructure Services**
- `BearerTokenService`: generación y validación de tokens JWT.  
- `TokenService`: gestión de refresh tokens y validación de los mismos.  

## 6. Relación General

- Los **Controllers** usan **Resources** para definir contratos de entrada/salida.  
- Los **Transformers** convierten recursos en comandos del dominio y entidades en DTOs.  
- El **ACL** actúa como intermediario entre la capa de interfaces y el dominio, evitando acoplamiento con proveedores externos.  
- Los **Services** de dominio e infraestructura aportan las capacidades necesarias para autenticación, registro, validación y consultas de seguridad.  

De esta manera, el *Interface Layer* sirve como frontera clara entre los consumidores externos (clientes o frontends) y el **core del microservicio IAM**.  

### IAM Interface
<img src="../chapter4/assets/ddd-layers/iam/IAMInterfaces.png" alt="IAM Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.3. Application Layer


### Users
- **Command Handlers**:  
  - `UserCommandServiceImpl` procesa comandos como `SignInCommand`, `SignUpCommand`, utilizando `UserRepository`, `HashingService`, `TokenService` y `RoleRepository`.  

- **Query Handlers**:  
  - `UserQueryServiceImpl` resuelve consultas como `GetAllUsersQuery`, `GetUserByIdQuery`, `GetUserByEmail_addressQuery`.  

### Roles
- **Command Handlers**:  
  - `RoleCommandServiceImpl` procesa el comando `SeedRolesCommand` utilizando `RoleRepository`.  

- **Query Handlers**:  
  - `RoleQueryServiceImpl` resuelve consultas como `GetAllRolesQuery`, `GetRoleByNameQuery`.  

### ACL Layer
- **Facade**:  
  - `IamContextFacadeImpl` extiende `IamContextFacade` y expone operaciones de creación y consulta de usuarios, además de integración con OAuth2 (`Google`, `GitHub`).  

### Event Handlers
- **Application Event**:  
  - `ApplicationReadyEventHandler` maneja el evento `ApplicationReadyEvent`, inicializando roles mediante `RoleCommandService`.  

### IAM Application
<img src="../chapter4/assets/ddd-layers/iam/IAMApplication.png" alt="IAM Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.4. Infrastructure Layer


En el diagrama presentado:  

- En la **Persistence Layer**, el `UserRepository` y el `RoleRepository` administran la persistencia de entidades de usuario y roles, permitiendo operaciones de búsqueda y validación por email o nombre de rol.  

- En la **Hashing Layer**, la interfaz `BCryptHashingService` y su implementación `HashingServiceImpl` proporcionan servicios de encriptación y validación de contraseñas utilizando `BCryptPasswordEncoder`.  

- En la **Token Layer**, la interfaz `BearerTokenService` y su implementación `TokenServiceImpl` gestionan la generación, validación y extracción de información de tokens JWT, incluyendo access tokens y refresh tokens.  

- En la **Authorization Layer**, clases como `UserDetailsImpl`, `UserDetailsServiceImpl` y `UsernamePasswordAuthenticationTokenBuilder` integran la autenticación con los repositorios de usuarios. Además, `BearerAuthorizationRequestFilter` y `UnauthorizedRequestHandlerEntryPoint` manejan el filtrado de solicitudes con token y la gestión de accesos no autorizados. La clase `WebSecurityConfiguration` centraliza la configuración de seguridad, integrando servicios de hashing, token y autenticación.  

- En la **OAuth2 Layer**, clases como `OAuth2AuthenticationSuccessHandler` y `OAuth2AuthenticationFailureHandler` gestionan el flujo de autenticación OAuth2 en casos de éxito o fallo, interactuando con servicios de usuario, rol y token. La clase `HttpCookieOAuth2AuthorizationRequestRepository` administra solicitudes OAuth2 mediante cookies, controlando la serialización, almacenamiento y eliminación de datos de autorización.  

### IAM Infrastructure
<img src="../chapter4/assets/ddd-layers/iam/IAMInfrastructure.png" alt="IAM Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/IAMComponents.png" alt="IAM Component Level Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.4.6.1. Bounded Context Domain Layer Class Diagrams

### IAM Domain
<img src="../chapter4/assets/ddd-layers/iam/IAMDomain.png" alt="IAM Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

##### 4.2.4.6.2. Bounded Context Database Design Diagram
### IAM Database Design
<img src="../chapter4/assets/ddd-layers/iam/IAMDomainDatabase.png" alt="IAM Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>






### 4.2.5. Bounded Context: User Profile
#### 4.2.5.1. Domain Layer

### Value Objects
Los objetos de valor garantizan inmutabilidad y consistencia en atributos clave del perfil:

- **PersonName**: agrupa el nombre y apellido de un usuario, expone la operación `getFullName()` para componer el nombre completo.
- **Username**: asegura unicidad y consistencia del identificador público de un perfil.
- **ProfileUrl**: representa la dirección del perfil en formato validado.
- **Badge**: modela insignias asignables a un perfil, con nombre y color distintivo.
- **Experience**: encapsula los puntos de experiencia acumulados por un usuario y provee acceso a su valor.
- **Level**: representa el nivel actual alcanzado en el sistema.
- **Ranking (enum)**: define el estado jerárquico del usuario en categorías progresivas (`BRONZE`, `SILVER`, `GOLD`, `PLATINUM`, `DIAMOND`, `MASTER`).

### Aggregates
- **Profile (Aggregate Root)**:  
  Entidad central que agrupa los atributos del perfil y las operaciones de negocio relacionadas.  
  - Propiedades: `PersonName`, `Username`, `ProfileUrl`, `Experience`, `Level`, `Ranking`, `badges`.  
  - Comportamientos:  
    - `addExperience(Integer points)`: incrementa experiencia.  
    - `setLevel(Integer level)`: actualiza nivel.  
    - `setRanking(Ranking ranking)`: ajusta el ranking según reglas de progresión.  
    - `addBadge(Badge badge)`: añade insignias al perfil.  
  - Constructores especializados permiten crear instancias directamente desde un comando (`CreateProfileCommand`).

### Commands
Representan intenciones de modificar el estado del agregado `Profile`:

- **CreateProfileCommand**: inicializa un nuevo perfil con nombre, apellido y URL.  
- **AddExperienceCommand**: agrega puntos de experiencia a un perfil.  
- **UpdateLevelCommand**: actualiza el nivel alcanzado.  
- **UpdateRankingCommand**: cambia el ranking asignado.  
- **AddBadgeCommand**: añade una insignia al perfil.

### Queries
Encapsulan la lectura de información del dominio:

- **GetAllProfilesQuery**: retorna todos los perfiles registrados.  
- **GetProfileByIdQuery**: busca un perfil por su identificador único.  
- **GetProfileByUsernameQuery**: consulta perfiles por su `Username`.  
- **GetProfilesByRankingQuery**: filtra perfiles por ranking.  
- **GetProfilesByLevelQuery**: filtra perfiles por nivel.  
- **GetProfileBadgesQuery**: obtiene insignias asignadas a un perfil.

### Domain Services
Interfaces que abstraen lógica de negocio transversal y la orquestación de comandos y consultas:

- **ProfileCommandService**:  
  Maneja la creación de perfiles a partir de `CreateProfileCommand`, retornando opcionalmente un `Profile`.  

- **ProfileQueryService**:  
  Permite recuperar perfiles por identificador, nombre de usuario o todos en conjunto.  

- **UsernameGeneratorService**:  
  Servicio especializado en generar identificadores únicos (`username`) para garantizar unicidad y evitar colisiones en la creación de perfiles.


#### 4.2.5.2. Interface Layer


En esta capa se definen los **puntos de entrada** de la aplicación.  
Su propósito es:  
- Recibir peticiones externas (REST API).  
- Transformarlas en **comandos o queries** del dominio.  
- Retornar **Resources (DTOs)** adecuados como respuesta.  


## Controllers

### **ProfilesController**
Controlador REST que expone los endpoints relacionados con la gestión de perfiles.  

**Dependencias:**  
- `ProfileCommandService`  
- `ProfileQueryService`  

**Responsabilidades:**  
- Recibir `Resource` desde el cliente.  
- Usar *Transformers* para convertirlos en **Comandos** o **Queries**.  
- Invocar servicios de dominio para ejecutar la lógica.  
- Retornar `Resource` listos para el cliente.  

**Principales Endpoints:**  
- `createProfile(CreateProfileResource)` → crear un perfil.  
- `getProfileById(UUID)` → obtener perfil por ID.  
- `getAllProfiles()` → listar todos los perfiles.  
- `addExperience(UUID, AddExperienceResource)` → agregar experiencia.  
- `updateLevel(UUID, UpdateLevelResource)` → actualizar nivel.  
- `updateRanking(UUID, UpdateRankingResource)` → actualizar ranking.  
- `addBadge(UUID, AddBadgeResource)` → añadir insignia.  
- `getProfilesByRanking(String)` → buscar perfiles por ranking.  
- `getProfilesByLevel(Integer)` → buscar perfiles por nivel.  
- `getProfileBadges(UUID)` → listar insignias de un perfil.  

## Resources (DTOs)

Clases que representan datos de entrada y salida en la API.  

- **CreateProfileResource** → datos para crear un perfil.  
- **ProfileResource** → datos completos de un perfil (incluye experiencia, nivel, ranking e insignias).  
- **AddExperienceResource** → puntos de experiencia a añadir.  
- **UpdateLevelResource** → nuevo nivel de perfil.  
- **UpdateRankingResource** → ranking actualizado.  
- **AddBadgeResource** → nombre y color de la insignia.  
- **BadgeResource** → datos de una insignia.  

## Transformers

Clases encargadas de convertir entre **Resources (DTOs)** y **Comandos/Entidades de dominio**.  

- `CreateProfileCommandFromResourceAssembler`  
- `ProfileResourceFromEntityAssembler`  
- `AddExperienceCommandFromResourceAssembler`  
- `UpdateLevelCommandFromResourceAssembler`  
- `UpdateRankingCommandFromResourceAssembler`  
- `AddBadgeCommandFromResourceAssembler`  
- `BadgeResourceFromEntityAssembler`  

**Responsabilidad principal:**  
- Garantizar la separación entre la capa de presentación y el dominio, evitando acoplamientos directos.  

### User Profile Interface
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementInterfaces.png" alt="User Profile Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.3. Application Layer

### Profiles
- **Command Handlers**:  
  - `ProfileCommandServiceImpl` procesa comandos como `CreateProfileCommand`, `AddExperienceCommand`, `UpdateLevelCommand`, `UpdateRankingCommand`, `AddBadgeCommand`, utilizando `ProfileRepository` y `UsernameGeneratorService`.  

- **Query Handlers**:  
  - `ProfileQueryServiceImpl` resuelve consultas como `GetProfileByIdQuery`, `GetProfileByUsernameQuery`, `GetAllProfilesQuery`, `GetProfilesByRankingQuery`, `GetProfilesByLevelQuery`, `GetProfileBadgesQuery`.  

### Supporting Domain Services
- **Username Management**:  
  - `UsernameGeneratorServiceImpl` genera nombres de usuario únicos apoyándose en `ProfileRepository`.  

- **Experience Management**:  
  - `ExperienceServiceImpl` calcula niveles, determina rankings y gestiona la adición de experiencia en perfiles.  

- **Badge Management**:  
  - `BadgeServiceImpl` otorga, elimina y valida insignias en perfiles.  

### Outbound Services
- **ACL**:  
  - `ExternalIamService` expone la integración con servicios externos de gestión de identidad y acceso.  

### User Profile Application
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementApplication.png" alt="User Profile Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.4. Infrastructure Layer

En el diagrama presentado:

- El `ProfileRepository` define la interfaz principal para la gestión de perfiles, permitiendo operaciones como búsqueda por `Username`, validaciones de existencia, filtrado por `Ranking` o nivel de experiencia, además de guardar entidades de tipo `Profile`.  

- La implementación `ProfileRepositoryImpl` utiliza las interfaces de Spring Data (`ProfileJpaRepository`, `BadgeJpaRepository`) para interactuar con la base de datos. Esta clase traduce las operaciones del dominio (`Profile`) hacia las entidades JPA (`ProfileJpaEntity`, `BadgeJpaEntity`).  

- Las entidades `ProfileJpaEntity` y `BadgeJpaEntity` representan la persistencia en la base de datos, incluyendo sus atributos básicos y métodos de conversión (`toDomainEntity`, `fromDomainEntity`) para mapear entre las entidades de infraestructura y las del dominio (`Profile`, `Badge`).  

- En la capa de **Spring Data JPA**, las interfaces `ProfileJpaRepository` y `BadgeJpaRepository` extienden de `JpaRepository`, lo que habilita operaciones genéricas de persistencia, además de consultas específicas como `findByUsername`, `findByRanking` o `findByProfileId`.  

- En la capa de **Domain**, se encuentran las entidades y value objects (`Profile`, `Username`, `Badge`, `Experience`, `Level`, `Ranking`) que son utilizadas por los repositorios de infraestructura para mantener la coherencia entre el dominio y la base de datos.  

### User Profile Infrastructure
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementInfrastructure.png" alt="User Profile Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/UserProfileComponents.png" alt="User Profile Component Level Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.5.6.1. Bounded Context Domain Layer Class Diagrams

### User Profile Domain
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementDomain.png" alt="User Profile Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>


##### 4.2.5.6.2. Bounded Context Database Design Diagram
### User Profile Database Design
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementDomainDatabase.png" alt="User Profile Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
