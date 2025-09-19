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

### 4.2.1. Bounedd Context: Challenges
#### 4.2.1.1. Domain Layer

La **Domain Layer** del bounded context **Challenges** constituye el núcleo conceptual que encapsula las reglas de negocio fundamentales para la gestión de desafíos de programación, soluciones estudiantiles y reportes de evaluación. Esta capa implementa los patrones tácticos de Domain-Driven Design, asegurando que la lógica de dominio permanezca aislada de preocupaciones técnicas e infraestructurales.

**Agregados (Aggregates):**

El dominio se organiza alrededor de tres agregados principales que mantienen la consistencia y encapsulan las reglas de negocio:

**1. Challenge Aggregate:**
- **Challenge**: Entidad raíz que representa un desafío de programación creado por profesores. Contiene información esencial como nombre, descripción, puntos de experiencia, estado de publicación y metadatos temporales.
- **CodeVersion**: Entidad que representa las diferentes versiones de código para distintos lenguajes de programación dentro de un desafío. Mantiene el código inicial y las pruebas asociadas.
- **CodeVersionTest**: Entidad que define las pruebas específicas para cada versión de código, incluyendo entradas, salidas esperadas y validaciones personalizadas.

**2. Solution Aggregate:**
- **Solution**: Entidad raíz que representa el intento de un estudiante por resolver un desafío específico. Mantiene la relación con el desafío, la versión de código seleccionada y los detalles de la solución.
- **SolutionDetails**: Value Object que encapsula los detalles específicos de la solución, incluyendo número de intentos, código fuente, timestamp del último intento y estado actual.

**3. Report Aggregate:**
- **Report**: Entidad que registra los resultados de la evaluación de una solución, incluyendo pruebas exitosas, tiempo de ejecución y memoria utilizada.

**Value Objects:**

Los Value Objects proporcionan tipos seguros y encapsulación de conceptos de dominio:

- **ChallengeId, SolutionId, SolutionReportId**: Identificadores únicos que garantizan type safety
- **TeacherId, StudentId**: Identificadores de actores del sistema
- **CodeVersionId, CodeVersionTestId**: Identificadores para versiones y pruebas
- **ChallengeTag**: Objeto complejo que incluye metadatos de etiquetas (nombre, color, icono)
- **ChallengeStatus**: Enumeración que define estados del ciclo de vida (DRAFT, PUBLISHED, HIDDEN)
- **CodeLanguage**: Enumeración de lenguajes soportados (C_PLUS_PLUS, JAVASCRIPT, PYTHON)
- **SolutionStatus**: Enumeración de estados de solución (SUCCESS, FAILED, MAX_ATTEMPTS_REACHED)

**Commands (Comandos):**

Los comandos representan intenciones de cambio en el sistema y encapsulan las operaciones de escritura:

*Challenge Commands:*
- **CreateChallengeCommand**: Creación de nuevos desafíos por parte de profesores
- **UpdateChallengeCommand**: Modificación de desafíos existentes con campos opcionales
- **PublishChallengeCommand**: Publicación de desafíos para estudiantes
- **StartChallengeCommand**: Inicio de un desafío por parte de estudiantes

*CodeVersion Commands:*
- **AddCodeVersionCommand**: Adición de versiones en nuevos lenguajes
- **UpdateCodeVersionCommand**: Modificación de código base
- **AddCodeVersionTestCommand**: Creación de nuevas pruebas
- **UpdateCodeVersionTestCommand**: Modificación de pruebas existentes

*Solution Commands:*
- **CreateSolutionCommand**: Inicio de resolución de desafío por estudiante
- **UpdateSolutionCommand**: Actualización de progreso de solución
- **SubmitSolutionCommand**: Envío final de solución para evaluación

*Report Commands:*
- **CreateSolutionReportCommand**: Generación de reporte de evaluación

**Queries (Consultas):**

Las queries encapsulan las operaciones de lectura del sistema:

*Challenge Queries:*
- **GetChallengeByIdQuery**: Recuperación de desafío específico
- **GetPublishedChallengesQuery**: Listado de desafíos publicados
- **GetChallengesByTeacherIdQuery**: Desafíos creados por profesor específico
- **GetAllChallengeTagsQuery**: Catálogo de etiquetas disponibles

*CodeVersion Queries:*
- **GetCodeVersionByIdQuery**: Versión específica de código
- **GetCodeVersionsByChallengeIdQuery**: Todas las versiones de un desafío

*Solution Queries:*
- **GetSolutionByIdQuery**: Solución específica
- **GetSolutionsByStudentIdQuery**: Soluciones de un estudiante
- **GetSolutionsByChallengeIdQuery**: Todas las soluciones de un desafío

*Report Queries:*
- **GetReportsBySolutionIdQuery**: Reportes de una solución específica

**Domain Services:**

Los servicios de dominio manejan operaciones que no pertenecen naturalmente a una entidad específica:

- **ChallengeCommandService**: Coordina operaciones complejas de desafíos
- **CodeVersionCommandService**: Gestiona versiones de código y pruebas
- **CodeVersionTestCommandService**: Administra pruebas específicas
- **SolutionCommandService**: Coordina el ciclo de vida de soluciones
- **ChallengeQueryService**: Optimiza consultas complejas de desafíos
- **CodeVersionQueryService**: Proporciona acceso eficiente a versiones
- **SolutionQueryService**: Facilita consultas de soluciones con filtros

**Reglas de Negocio Encapsuladas:**

1. **Integridad de Desafíos**: Un desafío debe tener al menos una versión de código antes de ser publicado
2. **Límite de Intentos**: Las soluciones tienen un máximo de intentos configurable
3. **Versionado**: Cada lenguaje de programación requiere su propia versión con pruebas específicas
4. **Validación de Estados**: Transiciones de estado controladas para desafíos y soluciones
5. **Trazabilidad**: Todos los cambios mantienen metadatos temporales para auditoría

### Challenges Domain
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesDomain.png" alt="Challenges Domain Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Domain
<img src="../chapter4/assets/ddd-layers/challenges/SolutionsDomain.png" alt="Solutions Domain Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Domain
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportsDomain.png" alt="Solution Reports Domain Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.1.2. Interface Layer

La **Interface Layer** del bounded context **Challenges** constituye la capa de presentación que maneja toda la comunicación externa con el sistema de desafíos de programación. Esta capa implementa el patrón MVC y expone APIs REST que permiten a las aplicaciones cliente interactuar con las funcionalidades de creación, gestión y resolución de desafíos académicos.

**Controllers (Controladores REST):**

Los controladores actúan como puntos de entrada HTTP y coordinan las operaciones entre la capa de presentación y la capa de aplicación:

**1. ChallengesController:**
Controlador principal que gestiona el ciclo de vida completo de los desafíos de programación.

*Operaciones de Escritura:*
- **createChallenge(CreateChallengeResource)**: Endpoint POST para crear nuevos desafíos con validación de permisos de profesor
- **updateChallenge(UpdateChallengeResource)**: Endpoint PUT para modificar desafíos existentes con campos opcionales
- **publishChallenge(PublishChallengeResource)**: Endpoint PATCH para publicar desafíos y hacerlos disponibles a estudiantes
- **startChallenge(StartChallengeResource)**: Endpoint POST para que estudiantes inicien la resolución de un desafío

*Operaciones de Lectura:*
- **getChallengeById(GetChallengeByIdResource)**: Endpoint GET para recuperar desafío específico con detalles completos
- **getPublishedChallenges()**: Endpoint GET para listar todos los desafíos publicados disponibles
- **getChallengesByTeacherId(GetChallengesByTeacherIdResource)**: Endpoint GET para desafíos creados por profesor específico
- **getAllChallengeTags()**: Endpoint GET para obtener catálogo de etiquetas disponibles

**2. CodeVersionsController:**
Controlador especializado que gestiona las diferentes versiones de código por lenguaje de programación.

*Operaciones de Gestión:*
- **addCodeVersion(AddCodeVersionResource)**: Endpoint POST para agregar soporte de nuevo lenguaje a desafío existente
- **updateCodeVersion(UpdateCodeVersionResource)**: Endpoint PUT para modificar código base y plantillas

*Operaciones de Consulta:*
- **getCodeVersionById(GetCodeVersionByIdResource)**: Endpoint GET para recuperar versión específica con código inicial
- **getCodeVersionsByChallengeId(GetCodeVersionsByChallengeIdResource)**: Endpoint GET para listar todos los lenguajes soportados

**3. CodeVersionTestsController:**
Controlador que administra las pruebas automatizadas para validación de soluciones.

*Operaciones de Pruebas:*
- **addCodeVersionTest(AddCodeVersionTestResource)**: Endpoint POST para crear nuevas pruebas con casos de validación
- **updateCodeVersionTest(UpdateCodeVersionTestResource)**: Endpoint PUT para modificar pruebas existentes con nuevos casos

**Resource Objects (DTOs):**

Los Resource Objects encapsulan datos de transferencia entre cliente y servidor con validaciones específicas:

*Challenge Resources:*
- **CreateChallengeResource**: Datos para creación (teacherId, name, description, experiencePoints)
- **UpdateChallengeResource**: Datos para modificación con campos opcionales (name?, description?, experiencePoints?, tags?)
- **PublishChallengeResource**: Identificador para publicación (challengeId)
- **StartChallengeResource**: Identificador para inicio de resolución (challengeId)

*CodeVersion Resources:*
- **AddCodeVersionResource**: Especificación de lenguaje (language: CodeLanguage)
- **UpdateCodeVersionResource**: Código actualizado (code: String)

*CodeVersionTest Resources:*
- **AddCodeVersionTestResource**: Caso de prueba completo (input, expectedOutput, customValidationCode, failureMessage)
- **UpdateCodeVersionTestResource**: Modificación de caso existente con mismos campos

*Query Resources:*
- **GetChallengeByIdResource**: Parámetro de consulta (challengeId: UUID)
- **GetChallengesByTeacherIdResource**: Filtro por profesor (teacherId: UUID)
- **GetCodeVersionByIdResource**: Consulta de versión (codeVersionId: UUID)
- **GetCodeVersionsByChallengeIdResource**: Listado por desafío (challengeId: UUID)

**Patrones de Interface Implementados:**

*RESTful Design:*
- Uso consistente de verbos HTTP (GET, POST, PUT, PATCH)
- URIs semánticas que reflejan recursos y jerarquías
- Códigos de estado HTTP apropiados para cada operación
- Versionado de API para compatibilidad futura

*Validation Patterns:*
- Validación de entrada en Resource Objects
- Sanitización de datos antes del procesamiento
- Verificación de permisos por tipo de usuario
- Validación de integridad referencial

*Error Handling:*
- Manejo centralizado de excepciones
- Respuestas de error estructuradas y consistentes
- Logging detallado para debugging y auditoría
- Mapeo de excepciones de dominio a códigos HTTP

*Security Considerations:*
- Autenticación requerida para todas las operaciones
- Autorización basada en roles (profesores vs. estudiantes)
- Validación de propiedad de recursos
- Rate limiting para prevenir abuso

**Mapping y Transformación:**

La capa incluye mappers automáticos que transforman:
- Resource Objects → Domain Commands/Queries
- Domain Objects → Response DTOs
- Excepciones de dominio → HTTP Error Responses
- Parámetros de URL → Value Objects de dominio

**Consideraciones de Performance:**

- Paginación automática para listados grandes
- Caché de respuestas para consultas frecuentes
- Compresión de respuestas para optimizar transferencia
- Lazy loading de relaciones complejas

### Challenges Interface
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesInterfaces.png" alt="Challenges Interface Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Interface
<img src="../chapter4/assets/ddd-layers/challenges/SolutionsInterfaces.png" alt="Solutions Interface Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Interface
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportsInterfaces.png" alt="Solution Reports Interface Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.1.3. Application Layer

La **Application Layer** del bounded context **Challenges** orquesta los flujos de procesos de negocio relacionados con la gestión de desafíos de programación. Esta capa actúa como coordinadora entre la Interface Layer y la Domain Layer, implementando los casos de uso específicos y manejando la lógica de aplicación que no pertenece al dominio puro.

**Command Service Implementations:**

Los Command Services implementan las interfaces definidas en la capa de dominio y coordinan operaciones de escritura:

**1. ChallengeCommandServiceImpl:**
Implementación concreta que maneja todos los comandos relacionados con el ciclo de vida de desafíos.

*Capabilities de Aplicación:*
- **Challenge Creation Workflow**: Coordina la creación de desafíos incluyendo validaciones de permisos, generación de identificadores únicos y persistencia inicial
- **Challenge Publishing Process**: Gestiona el flujo de publicación verificando completitud de datos, validando pruebas mínimas y actualizando estado
- **Challenge Update Orchestration**: Maneja actualizaciones parciales con validación de integridad y notificación de cambios
- **Student Challenge Initiation**: Coordina el inicio de resolución por estudiantes incluyendo verificación de prerrequisitos y registro de intento

*Métodos de Orquestación:*
- **handle(CreateChallengeCommand)**: Valida permisos de profesor, crea instancia de dominio, persiste y publica evento
- **handle(UpdateChallengeCommand)**: Recupera entidad, aplica cambios, valida consistencia y persiste
- **handle(PublishChallengeCommand)**: Verifica completitud, actualiza estado, invalida caché y notifica
- **handle(StartChallengeCommand)**: Valida disponibilidad, registra inicio y actualiza métricas

**2. CodeVersionCommandServiceImpl:**
Servicio especializado que gestiona las versiones de código por lenguaje de programación.

*Capabilities de Aplicación:*
- **Multi-Language Support Management**: Coordina la adición de soporte para nuevos lenguajes con validación de sintaxis
- **Code Template Management**: Gestiona plantillas de código inicial y configuraciones por lenguaje
- **Version Consistency**: Asegura consistencia entre versiones y sincronización de cambios

*Métodos de Coordinación:*
- **handle(AddCodeVersionCommand)**: Valida lenguaje, crea versión, establece código base y persiste
- **handle(UpdateCodeVersionCommand)**: Recupera versión, valida cambios, actualiza código y sincroniza

**3. CodeVersionTestCommandServiceImpl:**
Servicio que administra las pruebas automatizadas para validación de soluciones.

*Capabilities de Aplicación:*
- **Test Case Management**: Coordina creación y modificación de casos de prueba con validación
- **Test Validation Pipeline**: Gestiona validación de casos de prueba antes de la persistencia
- **Test Coverage Analysis**: Analiza cobertura de pruebas y sugiere casos adicionales

*Métodos de Gestión:*
- **handle(AddCodeVersionTestCommand)**: Valida entrada/salida, crea caso de prueba y persiste
- **handle(UpdateCodeVersionTestCommand)**: Recupera caso, aplica cambios y valida consistencia

**Query Service Implementations:**

Los Query Services optimizan las operaciones de lectura y proporcionan vistas especializadas:

**1. ChallengeQueryServiceImpl:**
Implementación que optimiza consultas de desafíos con diferentes filtros y criterios.

*Capabilities de Consulta:*
- **Challenge Discovery**: Facilita descubrimiento de desafíos con filtros avanzados
- **Teacher Dashboard Support**: Proporciona vistas especializadas para gestión de profesores
- **Student Challenge Browser**: Optimiza listados para experiencia de estudiantes
- **Analytics Data Provision**: Genera métricas y estadísticas de uso

*Métodos de Consulta:*
- **handle(GetChallengeByIdQuery)**: Recuperación optimizada con lazy loading de relaciones
- **handle(GetPublishedChallengesQuery)**: Listado con paginación y filtros de disponibilidad
- **handle(GetChallengesByTeacherIdQuery)**: Vista especializada con métricas de profesor
- **handle(GetAllChallengeTagsQuery)**: Catálogo optimizado con contadores de uso

**2. CodeVersionQueryServiceImpl:**
Servicio especializado en consultas de versiones de código con optimizaciones específicas.

*Capabilities de Consulta:*
- **Language-Specific Retrieval**: Recuperación optimizada por lenguaje de programación
- **Code Template Provision**: Proporciona plantillas de código para editores
- **Version Comparison**: Facilita comparación entre versiones de diferentes lenguajes

*Métodos de Consulta:*
- **handle(GetCodeVersionByIdQuery)**: Recuperación con código formateado y metadatos
- **handle(GetCodeVersionsByChallengeIdQuery)**: Listado con información de lenguajes disponibles

**Workflow Orchestration Patterns:**

La capa implementa patrones específicos para coordinar flujos complejos:

*Command Pipeline Pattern:*
- Validación de entrada → Transformación → Ejecución de dominio → Persistencia → Notificación

*Query Optimization Pattern:*
- Cache Check → Database Query → Data Transformation → Response Caching

*Event Publishing Pattern:*
- Domain Operation → Event Generation → Async Publishing → External Notification

**Integration Event Handlers:**

Manejadores que procesan eventos de otros bounded contexts:

*User Management Integration:*
- **UserRegisteredEventHandler**: Procesa registro de nuevos profesores para permisos
- **UserRoleChangedEventHandler**: Actualiza permisos de creación de desafíos

*Analytics Integration:*
- **ChallengeCreatedEventHandler**: Publica métricas de creación para análisis
- **ChallengeCompletedEventHandler**: Registra completitud para estadísticas

**Cross-Cutting Concerns:**

La capa maneja preocupaciones transversales:

*Transaction Management:*
- Transacciones automáticas para operaciones de escritura
- Rollback en caso de errores de dominio o infraestructura

*Caching Strategy:*
- Cache de consultas frecuentes (desafíos publicados, tags)
- Invalidación automática en operaciones de escritura

*Audit and Logging:*
- Logging detallado de todas las operaciones
- Auditoría de cambios para compliance

*Error Handling:*
- Transformación de excepciones de dominio
- Retry automático para errores transitorios

**Performance Considerations:**

*Query Optimization:*
- Uso de índices específicos para consultas frecuentes
- Paginación automática para resultados grandes
- Proyecciones optimizadas para reducir transferencia de datos

*Command Optimization:*
- Batch processing para operaciones múltiples
- Async processing para operaciones no críticas
- Event sourcing para trazabilidad completa

### Challenges Application
<img src="../chapter4/assets/ddd-layers/challenges/ChallengesApplication.png" alt="Challenges Application Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Application
<img src="../chapter4/assets/ddd-layers/challenges/SolutionsApplication.png" alt="Solutions Application Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Solution Report Application
<img src="../chapter4/assets/ddd-layers/challenges/SolutionReportsApplication.png" alt="Solution Reports Application Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.1.4. Infrastructure Layer

La **Infrastructure Layer** del bounded context **Challenges** proporciona implementaciones concretas de las abstracciones definidas en la Domain Layer y gestiona el acceso a recursos externos como bases de datos, sistemas de mensajería y servicios de terceros. Esta capa asegura la persistencia de datos, comunicación inter-servicios y integración con la infraestructura tecnológica subyacente.

**Repository Implementations:**

Las implementaciones de repositorio extienden JpaRepository y proporcionan acceso optimizado a datos:

**1. ChallengeRepository extends JpaRepository<Challenge, UUID>:**
Repositorio principal que gestiona la persistencia de desafíos con consultas especializadas.

*Métodos de Consulta Especializados:*
- **findByTeacherId(teacherId: TeacherId)**: Recupera todos los desafíos creados por un profesor específico con índice optimizado
- **findByStatus(status: ChallengeStatus)**: Filtra desafíos por estado (DRAFT, PUBLISHED, HIDDEN) para diferentes vistas
- **findPublishedChallenges()**: Consulta optimizada que retorna solo desafíos disponibles para estudiantes con eager loading de tags

*Optimizaciones de Performance:*
- Índices compuestos en (teacherId, status) para consultas frecuentes
- Query hints para control de fetch strategies
- Native queries para consultas complejas con agregaciones

**2. CodeVersionRepository extends JpaRepository<CodeVersion, UUID>:**
Repositorio especializado en versiones de código con consultas por lenguaje y desafío.

*Métodos de Acceso Específicos:*
- **findByChallengeId(challengeId: ChallengeId)**: Retorna todas las versiones disponibles para un desafío con lazy loading de tests
- **findByChallengeIdAndLanguage(challengeId, language)**: Búsqueda específica por desafío y lenguaje para editores de código

*Consideraciones de Almacenamiento:*
- CLOB storage para código fuente de gran tamaño
- Compresión automática para versiones históricas
- Versionado de esquemas para backward compatibility

**3. CodeVersionTestRepository extends JpaRepository<CodeVersionTest, UUID>:**
Repositorio que maneja casos de prueba con operaciones batch optimizadas.

*Métodos de Gestión de Pruebas:*
- **findByCodeVersionId(codeVersionId: CodeVersionId)**: Recupera todos los casos de prueba ordenados por secuencia
- **deleteByCodeVersionId(codeVersionId: CodeVersionId)**: Eliminación en cascada optimizada con batch operations

*Optimizaciones de Testing:*
- Bulk operations para creación/actualización de múltiples tests
- Índices en foreign keys para joins eficientes
- Particionamiento por challengeId para escalabilidad

**4. ChallengeTagRepository extends JpaRepository<ChallengeTag, UUID>:**
Repositorio que gestiona etiquetas con validaciones de unicidad.

*Métodos de Validación:*
- **findByName(name: String)**: Búsqueda exacta con case-insensitive matching
- **existsByName(name: String)**: Validación rápida de existencia para prevenir duplicados

*Cache Strategy:*
- Cache L2 habilitado para tags frecuentemente consultados
- Cache de contadores para estadísticas de uso
- Invalidación automática en operaciones de escritura

**Database Configuration:**

*Connection Management:*
- Connection pooling con HikariCP para alta concurrencia
- Read replicas para consultas de solo lectura
- Connection validation y leak detection

*Transaction Configuration:*
- Transacciones declarativas con Spring @Transactional
- Isolation levels específicos por tipo de operación
- Timeout configuration para prevenir deadlocks

*Schema Management:*
- Flyway para versionado de esquemas de base de datos
- Rollback strategies para deployments seguros
- Data migration scripts para cambios de estructura

**External Service Integrations:**

*Code Execution Service Integration:*
- Cliente HTTP para comunicación con Code Runner microservice
- Circuit breaker pattern para manejo de fallos
- Retry logic con exponential backoff
- Request/response serialization optimizada

*Message Broker Implementation:**
- Apache Kafka producer configuration para eventos de dominio
- Topic partitioning por challengeId para escalabilidad
- Schema registry integration para evolución de eventos
- Dead letter queue para manejo de errores

*File Storage Service:*
- Integration con Azure Blob Storage para media assets
- CDN integration para optimización de delivery
- Multipart upload para archivos grandes
- Automatic cleanup de archivos temporales

**Event Publishing Infrastructure:**

*Domain Event Handling:*
- Event bus implementation con Apache Kafka
- Outbox pattern para garantizar delivery de eventos
- Event versioning para backward compatibility
- Monitoring y alertas para event processing failures

*Integration Events:*
- **ChallengeCreatedEvent**: Publicado cuando se crea un nuevo desafío
- **ChallengePublishedEvent**: Notifica disponibilidad para estudiantes
- **SolutionSubmittedEvent**: Enviado al Code Runner para evaluación
- **ChallengeCompletedEvent**: Notifica completitud para analytics

**Caching Infrastructure:**

*Multi-Level Caching:*
- L1 Cache: Hibernate second-level cache para entidades
- L2 Cache: Redis para query results y computed values
- CDN Cache: CloudFlare para assets estáticos

*Cache Strategies:*
- Write-through para datos críticos
- Write-behind para datos no críticos
- Cache-aside para consultas complejas
- Time-based expiration con invalidación manual

**Security Infrastructure:**

*Database Security:*
- Encryption at rest para datos sensibles
- Row-level security para multi-tenancy
- Audit logging para compliance
- Backup encryption y retention policies

*API Security:*
- OAuth2 token validation middleware
- Rate limiting con Redis backing store
- Request sanitization y validation
- CORS configuration para cross-origin requests

**Monitoring and Observability:**

*Metrics Collection:*
- Micrometer integration para application metrics
- Database performance monitoring
- Custom business metrics (challenge creation rate, completion rate)
- Real-time alerting para anomalías

*Distributed Tracing:*
- Spring Cloud Sleuth para request tracing
- Correlation IDs para seguimiento cross-service
- Performance profiling para optimización
- Error tracking y aggregation

**Deployment Infrastructure:**

*Container Configuration:*
- Docker images optimizadas con multi-stage builds
- Health checks para container orchestration
- Resource limits y requests para Kubernetes
- Rolling deployment strategies

*Configuration Management:*
- Spring Cloud Config para external configuration
- Environment-specific property files
- Secret management con Azure Key Vault
- Feature flags para gradual rollouts

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
##### 4.2.1.6.2. Bounded Context Database Design Diagram

### 4.2.2. Bounded Context: Class Activities
#### 4.2.2.1. Domain Layer

La **Domain Layer** del bounded context **Class Activities** gestiona las actividades académicas interactivas, específicamente enfocada en quizzes en tiempo real y sesiones de clase en vivo. Esta capa implementa patrones DDD tácticos para encapsular las reglas de negocio complejas relacionadas con la creación de actividades educativas y la gestión de sesiones colaborativas en tiempo real.

**Agregados (Aggregates):**

El dominio se estructura alrededor de dos agregados principales que manejan diferentes aspectos del ciclo de vida de las actividades:

**1. QuizActivity Aggregate (Activities Manager):**
- **QuizActivity**: Entidad raíz que representa una actividad de quiz creada por profesores. Encapsula la metadata del quiz incluyendo título, descripción opcional y colección de preguntas asociadas.
- **Question**: Entidad que define preguntas individuales dentro del quiz. Incluye contenido multimedia, límites de tiempo, puntuación, nivel de dificultad y configuraciones de presentación.
- **Option**: Entidad que representa las opciones de respuesta para cada pregunta, incluyendo contenido multimedia y marcador de respuesta correcta.

**2. LiveSession Aggregate (Class Activity Session Manager):**
- **LiveSession**: Entidad raíz que gestiona sesiones de quiz en tiempo real. Coordina la participación de estudiantes, el progreso de preguntas y el estado general de la sesión.
- **Participant**: Entidad que representa un estudiante participante en la sesión, manteniendo su estado, puntuación acumulada y respuestas registradas.
- **Answer**: Entidad que registra las respuestas específicas de participantes a preguntas durante la sesión.
- **CurrentQuestion**: Entidad que gestiona la pregunta actualmente activa en la sesión, incluyendo tiempos de inicio/fin y estado de activación.

**Value Objects:**

Los Value Objects aseguran type safety y encapsulan conceptos de dominio importantes:

*Identificadores:*
- **ActivityId, SessionId**: Identificadores únicos para actividades y sesiones
- **TeacherId, ParticipantId**: Identificadores de actores del sistema
- **QuestionId, OptionId, AnswerId**: Identificadores de componentes específicos
- **CurrentQuestionId**: Identificador para preguntas activas en sesiones

*Objetos de Contenido:*
- **Content**: Value Object complejo que encapsula contenido multimedia (texto/imagen) con su tipo correspondiente
- **ContentType**: Enumeración que define tipos de contenido soportados (TEXT, IMAGE)

*Enumeraciones de Estado:*
- **DifficultyLevel**: Niveles de dificultad (EASY, MEDIUM, HARD, NONE)
- **SessionStatus**: Estados del ciclo de vida de sesión (NOT_STARTED, LOADING, OPENED, IN_PROGRESS, CLOSED)
- **ParticipantStatus**: Estados de participación (JOINED, ACTIVE, DISCONNECTED, LEFT)

**Commands (Comandos):**

Los comandos representan intenciones de cambio y operaciones de escritura del sistema:

*QuizActivity Commands:*
- **CreateQuizActivityCommand**: Creación de nueva actividad de quiz por profesores
- **AddQuestionCommand**: Adición de preguntas a actividades existentes con configuraciones completas
- **AddOptionCommand**: Creación de opciones de respuesta para preguntas específicas
- **UpdateQuestionCommand**: Modificación de preguntas existentes incluyendo contenido y configuraciones

*LiveSession Commands:*
- **CreateLiveSessionCommand**: Inicio de nueva sesión en vivo basada en una actividad
- **JoinSessionCommand**: Incorporación de participantes a sesiones activas
- **LeaveSessionCommand**: Retiro de participantes de sesiones
- **StartSessionCommand**: Activación oficial de sesión para comenzar quiz
- **LoadQuestionCommand**: Carga de pregunta específica con tiempos definidos
- **EndCurrentQuestionCommand**: Finalización de pregunta activa
- **SendAnswerCommand**: Registro de respuesta de participante
- **CloseSessionCommand**: Cierre oficial de sesión

**Queries (Consultas):**

Las queries encapsulan operaciones de lectura optimizadas:

*QuizActivity Queries:*
- **GetQuizActivityByIdQuery**: Recuperación de actividad específica
- **GetQuestionsByActivityIdQuery**: Listado de preguntas de una actividad
- **GetOptionsByQuestionIdQuery**: Opciones de respuesta para pregunta específica

*LiveSession Queries:*
- **GetLiveSessionByIdQuery**: Recuperación de sesión específica
- **GetParticipantsBySessionIdQuery**: Listado de participantes activos
- **GetLeaderboardQuery**: Ranking de participantes por puntuación
- **GetCurrentQuestionQuery**: Pregunta actualmente activa
- **GetCurrentQuestionDetailsQuery**: Detalles completos de pregunta activa

**Domain Services:**

Los servicios de dominio coordinan operaciones complejas que trascienden entidades individuales:

*QuizActivity Services:*
- **QuizActivityCommandService**: Gestión del ciclo de vida de actividades
- **QuestionCommandService**: Administración de preguntas y modificaciones
- **OptionCommandService**: Gestión de opciones de respuesta
- **QuizActivityQueryService**: Consultas optimizadas de actividades
- **QuestionQueryService**: Acceso eficiente a preguntas
- **OptionQueryService**: Recuperación de opciones de respuesta

*LiveSession Services:*
- **LiveSessionCommandService**: Coordinación completa de sesiones en tiempo real
- **LiveSessionQueryService**: Consultas especializadas para sesiones activas

**Reglas de Negocio Encapsuladas:**

1. **Integridad de Actividades**: Una actividad debe contener al menos una pregunta con opciones válidas antes de poder generar sesiones
2. **Gestión de Contenido**: El contenido multimedia debe validarse según su tipo (TEXT/IMAGE)
3. **Control de Sesiones**: Solo un profesor puede iniciar y gestionar sesiones de sus propias actividades
4. **Participación Única**: Un participante no puede unirse múltiples veces a la misma sesión
5. **Secuencia de Preguntas**: Las preguntas deben cargarse secuencialmente y solo una puede estar activa por vez
6. **Validación Temporal**: Las respuestas solo son válidas durante el período activo de la pregunta
7. **Puntuación Consistente**: La puntuación se calcula basada en respuestas correctas y tiempo de respuesta
8. **Estados Transicionales**: Los cambios de estado siguen flujos predefinidos sin transiciones inválidas
9. **Persistencia de Respuestas**: Todas las respuestas se registran inmediatamente para garantizar integridad
10. **Límites de Tiempo**: Preguntas con límite de tiempo se cierran automáticamente al vencer

**Patrones de Comunicación en Tiempo Real:**

El dominio está diseñado para soportar comunicación en tiempo real mediante:
- **Event Sourcing**: Para mantener historial completo de sesiones
- **Command Segregation**: Separación clara entre operaciones de lectura y escritura
- **State Management**: Gestión precisa de estados de sesión y participantes
- **Temporal Constraints**: Manejo de restricciones temporales para preguntas

### Activities Manager Domain
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerDomain.png" alt="Activities Manager Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Domain
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerDomain.png" alt="Class Activity Session Manager Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.2. Interface Layer
### Activities Manager Interface
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerInterfaces.png" alt="Activities Manager Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Interface
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerInterfaces.png" alt="Class Activity Session Manager Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.3. Application Layer
### Activities Manager Application
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerApplication.png" alt="Activities Manager Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Application
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerApplication.png" alt="Class Activity Session Manager Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.4. Infrastructure Layer
### Activities Manager Infrastructure
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerInfrastructure.png" alt="Activities Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Infrastructure
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerInfrastructure.png" alt="Class Activity Session Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/ClassActivitiesComponent.png" alt="Class Activity Session Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.2.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.2.6.1. Bounded Context Domain Layer Class Diagrams

##### 4.2.2.6.2. Bounded Context Database Design Diagram
### Activities Manager Database Design
<img src="../chapter4/assets/ddd-layers/class-activities/ActivitiesManagerDomainDatabase.png" alt="Activities Manager Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### Class Activity Session Manager Database Design
<img src="../chapter4/assets/ddd-layers/class-activities/ClassActivitySessionManagerDomainDatabase.png" alt="Class Activity Session Manager Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### 4.2.3. Bounded Context: Community
#### 4.2.3.1. Domain Layer

La **Domain Layer** del bounded context **Community** constituye el núcleo social de la plataforma LevelUpJourney, enfocándose en facilitar la interacción, colaboración y construcción de comunidad entre usuarios. Esta capa encapsula las reglas de negocio relacionadas con la creación de contenido, participación social y sistemas de engagement que fomentan el aprendizaje colaborativo.

**Agregados (Aggregates):**

El dominio se estructura alrededor de un agregado principal que gestiona todas las interacciones sociales:

**1. Post Aggregate (Community Manager):**
- **Post**: Entidad raíz que representa una publicación creada por usuarios en la plataforma. Actúa como el centro de la interacción social, conteniendo contenido multimedia, comentarios asociados y métricas de engagement.
- **Comment**: Entidad que representa respuestas y discusiones vinculadas a publicaciones específicas. Permite crear hilos de conversación y facilita el intercambio de ideas entre usuarios.
- **Like**: Entidad que registra las reacciones positivas de usuarios hacia publicaciones y comentarios, creando métricas de popularidad y engagement.

**Value Objects:**

Los Value Objects proporcionan encapsulación de conceptos de dominio y type safety:

*Identificadores:*
- **PostId**: Identificador único para publicaciones
- **CommentId**: Identificador único para comentarios
- **UserId**: Identificador de usuarios del sistema

*Objetos de Contenido:*
- **Content**: Value Object complejo que encapsula el contenido de publicaciones, incluyendo texto y URLs de medios multimedia (imágenes, videos, documentos)
- **CommentContent**: Value Object especializado para comentarios que permite solo contenido textual, manteniendo las discusiones enfocadas y accesibles

*Objetos de Auditoría:*
- **Auditable**: Value Object que encapsula metadatos temporales para trazabilidad completa, incluyendo timestamps de creación y última modificación

**Commands (Comandos):**

Los comandos representan intenciones de acción social y operaciones de escritura:

*Post Commands:*
- **CreatePost**: Creación de nuevas publicaciones con contenido multimedia
- **EditPost**: Modificación de publicaciones existentes manteniendo historial
- **DeletePost**: Eliminación de publicaciones y contenido asociado

*Comment Commands:*
- **AddComment**: Adición de comentarios a publicaciones específicas
- **EditComment**: Modificación de comentarios existentes
- **DeleteComment**: Eliminación de comentarios individuales

*Engagement Commands:*
- **LikePost**: Registro de reacción positiva hacia publicación
- **UnlikePost**: Retiro de reacción positiva de publicación
- **LikeComment**: Registro de reacción positiva hacia comentario
- **UnlikeComment**: Retiro de reacción positiva de comentario

**Queries (Consultas):**

Las queries encapsulan operaciones de lectura optimizadas para la experiencia social:

*Post Queries:*
- **GetPostById**: Recuperación de publicación específica con metadatos completos
- **GetAllPosts**: Listado de publicaciones con paginación y filtros
- **GetLikesByPostId**: Métricas de engagement para publicación específica

*Comment Queries:*
- **GetCommentsByPostId**: Hilos de comentarios organizados por publicación
- **GetCommentById**: Recuperación de comentario específico
- **GetLikesByCommentId**: Métricas de engagement para comentario específico

**Domain Services:**

Los servicios de dominio coordinan operaciones sociales complejas:

*Content Management Services:*
- **PostCommandService**: Gestión completa del ciclo de vida de publicaciones incluyendo operaciones de engagement
- **CommentCommandService**: Administración de comentarios y sus interacciones sociales

*Query Services:*
- **PostQueryService**: Consultas optimizadas para publicaciones con métricas agregadas
- **CommentQueryService**: Acceso eficiente a comentarios con contexto de conversación

**Reglas de Negocio Encapsuladas:**

1. **Integridad de Contenido**: Las publicaciones deben contener al menos texto o media URLs válidas
2. **Restricciones de Comentarios**: Los comentarios solo pueden contener texto, sin medios multimedia para mantener simplicidad
3. **Unicidad de Likes**: Un usuario puede dar like solo una vez por publicación o comentario
4. **Propiedad de Contenido**: Solo el autor puede editar o eliminar sus propias publicaciones y comentarios
5. **Cascada de Eliminación**: Al eliminar una publicación, se eliminan automáticamente todos los comentarios y likes asociados
6. **Auditoría Completa**: Todas las acciones mantienen timestamps para trazabilidad y análisis temporal
7. **Validación de URLs**: Las URLs de medios deben ser válidas y accesibles antes de la publicación
8. **Límites de Contenido**: Restricciones de longitud para texto y número de media URLs por publicación
9. **Prevención de Spam**: Limitaciones temporales para creación de contenido por usuario
10. **Moderación de Contenido**: Validación automática de contenido apropiado antes de publicación

**Métodos de Dominio Especializados:**

*Post Entity Methods:*
- **addComment(comment)**: Agregación de comentario con validaciones de integridad
- **addLike(userId)**: Registro de like con validación de unicidad
- **removeLike(userId)**: Retiro de like con verificación de existencia

*Comment Entity Methods:*
- **editContent(content)**: Modificación de contenido con preservación de historial
- **addLike(userId)**: Gestión de likes en comentarios
- **removeLike(userId)**: Retiro de likes con consistencia

**Patrones de Engagement Social:**

El dominio implementa patrones específicos para fomentar la participación:
- **Immediate Feedback**: Likes instantáneos para gratificación inmediata
- **Threaded Discussions**: Comentarios organizados jerárquicamente
- **Content Ownership**: Control granular sobre contenido propio
- **Social Validation**: Métricas de engagement visibles
- **Temporal Tracking**: Análisis de patrones de actividad social

**Consideraciones de Escalabilidad:**

- **Denormalización Estratégica**: Contadores de likes pre-calculados para rendimiento
- **Paginación Inteligente**: Queries optimizadas para cargas incrementales
- **Caché de Contenido**: Estrategias de caché para contenido frecuentemente accedido
- **Media Optimization**: Gestión eficiente de URLs y recursos multimedia

### Community Manager Domain
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerDomain.png" alt="Community Manager Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.2. Interface Layer
### Community Manager Interface
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerInterfaces.png" alt="Community Manager Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.3. Application Layer
### Community Manager Application
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerApplication.png" alt="Community Manager Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.4. Infrastructure Layer
### Community Manager Infrastructure
<img src="../chapter4/assets/ddd-layers/community/CommunityManagerInfrastructure.png" alt="Community Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/CommunityComponents.png" alt="Community Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.3.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.3.6.1. Bounded Context Domain Layer Class Diagrams
##### 4.2.3.6.2. Bounded Context Database Design Diagram

### Community Manager 

<img src="../chapter4/assets/ddd-layers/community/CommunityManagerDomainDatabase.png" alt="Community Manager Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

### 4.2.4. Bounded Context: Identity and Access Management (IAM)
#### 4.2.4.1. Domain Layer

La **Domain Layer** del bounded context **Identity and Access Management (IAM)** constituye el núcleo de seguridad y gestión de identidades de la plataforma LevelUpJourney. Esta capa encapsula las reglas de negocio críticas relacionadas con autenticación, autorización, gestión de usuarios y control de acceso, implementando patrones de seguridad robustos y escalables.

**Agregados (Aggregates):**

El dominio se estructura alrededor de un agregado principal que gestiona toda la información de identidad y acceso:

**1. User Aggregate (IAM Manager):**
- **User**: Entidad raíz que representa un usuario autenticado en el sistema. Encapsula credenciales de acceso, información de contacto y roles asignados que determinan los permisos de acceso a diferentes funcionalidades de la plataforma.
- **Role**: Entidad que define los roles disponibles en el sistema, encapsulando permisos y niveles de acceso específicos para diferentes tipos de usuarios.

**Value Objects:**

Los Value Objects proporcionan encapsulación segura de conceptos críticos de seguridad:

*Objetos de Credenciales:*
- **EmailAddress**: Value Object que encapsula direcciones de email con validaciones de formato, normalización y métodos para extraer partes locales y de dominio
- **Password**: Value Object que gestiona contraseñas con validaciones de fortaleza, scoring de seguridad y verificación de políticas de contraseñas
- **TokenPair**: Value Object que encapsula pares de tokens (access/refresh) para autenticación basada en JWT

*Objetos de Integración:*
- **OAuth2UserInfo**: Value Object que encapsula información de usuarios provenientes de proveedores OAuth2 externos (Google, GitHub), facilitando la integración federada

*Enumeraciones de Seguridad:*
- **Roles**: Enumeración que define los roles disponibles en el sistema (ROLE_STUDENT, ROLE_INSTRUCTOR, ROLE_ADMIN)

**Commands (Comandos):**

Los comandos representan intenciones de acción en el sistema de identidad:

*Authentication Commands:*
- **SignUpCommand**: Registro de nuevos usuarios con validación de credenciales y asignación de roles
- **SignInCommand**: Autenticación de usuarios existentes con verificación de credenciales

*System Administration Commands:*
- **SeedRolesCommand**: Inicialización del sistema de roles para bootstrap de la aplicación

**Queries (Consultas):**

Las queries encapsulan operaciones de lectura para gestión de identidades:

*User Management Queries:*
- **GetAllUsersQuery**: Listado completo de usuarios para administración del sistema
- **GetUserByIdQuery**: Recuperación de usuario específico por identificador único
- **GetUserByEmail_addressQuery**: Búsqueda de usuario por dirección de email para autenticación

*Role Management Queries:*
- **GetAllRolesQuery**: Listado de todos los roles disponibles en el sistema
- **GetRoleByNameQuery**: Recuperación de rol específico por nombre para asignaciones

**Domain Services:**

Los servicios de dominio coordinan operaciones complejas de seguridad y gestión de identidades:

*User Management Services:*
- **UserCommandService**: Gestión completa del ciclo de vida de usuarios incluyendo registro, autenticación y generación de tokens
- **UserQueryService**: Consultas optimizadas para recuperación de información de usuarios

*Role Management Services:*
- **RoleCommandService**: Administración de roles del sistema incluyendo inicialización y mantenimiento
- **RoleQueryService**: Consultas especializadas para gestión de roles y permisos

**Métodos de Dominio Especializados:**

*User Entity Methods:*
- **User()**: Constructor por defecto para instanciación básica
- **User(email, password)**: Constructor para creación con credenciales básicas
- **User(email, password, roles)**: Constructor completo con roles asignados
- **addRole(role)**: Adición de rol individual con validaciones de permisos
- **addRoles(roles)**: Asignación múltiple de roles con verificación de consistencia
- **getEmail_address()**: Acceso seguro a dirección de email
- **setEmail_address(email)**: Modificación de email con validaciones
- **getPassword()**: Acceso controlado a contraseña (hash)
- **setPassword(password)**: Actualización de contraseña con políticas de seguridad
- **getPasswordStrength()**: Evaluación de fortaleza de contraseña actual

*Role Entity Methods:*
- **Role()**: Constructor por defecto
- **Role(name)**: Constructor con nombre de rol específico
- **getStringName()**: Representación string del nombre del rol
- **getDefaultRole()**: Método estático para obtener rol por defecto (STUDENT)
- **toRoleFromName(name)**: Conversión desde string a objeto Role
- **validateRoleSet(roles)**: Validación estática de conjuntos de roles

*Value Object Methods:*
- **EmailAddress.normalized()**: Normalización de formato de email
- **EmailAddress.getLocalPart()**: Extracción de parte local del email
- **EmailAddress.getDomainPart()**: Extracción de dominio del email
- **Password.getStrengthScore()**: Cálculo numérico de fortaleza
- **Password.isStrong()**: Verificación booleana de política de contraseñas

**Reglas de Negocio Encapsuladas:**

1. **Unicidad de Email**: Las direcciones de email deben ser únicas en todo el sistema
2. **Políticas de Contraseñas**: Las contraseñas deben cumplir con criterios mínimos de seguridad
3. **Roles por Defecto**: Nuevos usuarios reciben automáticamente el rol STUDENT
4. **Validación de Roles**: Los roles asignados deben existir en el sistema
5. **Normalización de Email**: Los emails se normalizan para evitar duplicados
6. **Gestión de Tokens**: Los tokens tienen tiempos de vida específicos y renovación automática
7. **Integridad de Credenciales**: Las credenciales se validan antes del almacenamiento
8. **Auditoría de Acceso**: Todos los intentos de autenticación se registran
9. **Prevención de Escalación**: Los usuarios no pueden auto-asignarse roles superiores
10. **Consistencia de Roles**: Los conjuntos de roles deben ser lógicamente consistentes

**Patrones de Seguridad Implementados:**

- **Password Hashing**: Hashing seguro de contraseñas con salt
- **JWT Token Management**: Gestión de tokens de acceso y renovación
- **Role-Based Access Control (RBAC)**: Control de acceso basado en roles
- **OAuth2 Integration**: Integración con proveedores externos de identidad
- **Input Validation**: Validación exhaustiva de todas las entradas
- **Secure Storage**: Almacenamiento seguro de credenciales sensibles

**Estrategias de Autenticación:**

- **Local Authentication**: Autenticación tradicional con email/password
- **Federated Authentication**: Integración con Google OAuth y GitHub OAuth
- **Multi-Factor Ready**: Preparado para extensión con autenticación multifactor
- **Session Management**: Gestión segura de sesiones de usuario
- **Token Refresh**: Renovación automática de tokens de acceso

**Consideraciones de Seguridad:**

- **Credential Protection**: Protección de credenciales en tránsito y reposo
- **Brute Force Prevention**: Protección contra ataques de fuerza bruta
- **Account Lockout**: Bloqueo de cuentas por intentos fallidos
- **Audit Trail**: Rastro completo de auditoría para compliance
- **Privacy Compliance**: Cumplimiento con regulaciones de privacidad
- **Secure Communication**: Comunicación cifrada para todas las operaciones

**Integración con OAuth2:**

- **Provider Support**: Soporte para múltiples proveedores OAuth2
- **User Mapping**: Mapeo automático de información de proveedores externos
- **Account Linking**: Vinculación de cuentas locales con identidades externas
- **Fallback Authentication**: Autenticación local como respaldo

### IAM Domain
<img src="../chapter4/assets/ddd-layers/iam/IAMDomain.png" alt="IAM Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.2. Interface Layer
### IAM Interface
<img src="../chapter4/assets/ddd-layers/iam/IAMInterfaces.png" alt="IAM Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.3. Application Layer
### IAM Application
<img src="../chapter4/assets/ddd-layers/iam/IAMApplication.png" alt="IAM Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.4. Infrastructure Layer
### IAM Infrastructure
<img src="../chapter4/assets/ddd-layers/iam/IAMInfrastructure.png" alt="IAM Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/IAMComponents.png" alt="IAM Component Level Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.4.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.4.6.1. Bounded Context Domain Layer Class Diagrams
##### 4.2.4.6.2. Bounded Context Database Design Diagram
### IAM Database Design
<img src="../chapter4/assets/ddd-layers/iam/IAMDomainDatabase.png" alt="IAM Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>






### 4.2.5. Bounded Context: User Profile
#### 4.2.5.1. Domain Layer

La **Domain Layer** del bounded context **User Profile** constituye el núcleo de gestión de identidad y progreso académico de los usuarios en la plataforma LevelUpJourney. Esta capa encapsula las reglas de negocio relacionadas con la representación de perfiles de usuario, sistemas de gamificación, progresión académica y reconocimientos de logros que motivan el engagement continuo en el aprendizaje.

**Agregados (Aggregates):**

El dominio se estructura alrededor de un agregado principal que centraliza toda la información del usuario:

**1. Profile Aggregate (Profile Management):**
- **Profile**: Entidad raíz que representa la identidad completa de un usuario en la plataforma. Encapsula información personal, progreso académico, logros obtenidos y métricas de gamificación que reflejan el journey de aprendizaje del usuario.

**Value Objects:**

Los Value Objects proporcionan encapsulación robusta de conceptos de dominio y garantizan la integridad de datos:

*Objetos de Identidad:*
- **PersonName**: Value Object compuesto que encapsula nombres y apellidos, proporcionando métodos para obtener el nombre completo formateado
- **Username**: Value Object que representa el identificador único del usuario en la plataforma, con validaciones de formato y unicidad
- **ProfileUrl**: Value Object que encapsula URLs de imágenes de perfil con validaciones de formato y accesibilidad

*Objetos de Gamificación:*
- **Experience**: Value Object que encapsula puntos de experiencia acumulados, proporcionando métodos para consulta y validación de rangos
- **Level**: Value Object que representa el nivel académico actual del usuario basado en experiencia acumulada
- **Badge**: Value Object complejo que representa reconocimientos específicos con nombre descriptivo y código de color para visualización
- **Ranking**: Enumeración que define categorías de clasificación jerárquica (BRONZE, SILVER, GOLD, PLATINUM, DIAMOND, MASTER)

**Commands (Comandos):**

Los comandos representan intenciones de modificación del perfil y progreso del usuario:

*Profile Management Commands:*
- **CreateProfileCommand**: Creación de nuevos perfiles de usuario con información personal básica
- **AddExperienceCommand**: Adición de puntos de experiencia por completar actividades académicas
- **UpdateLevelCommand**: Actualización de nivel basada en experiencia acumulada
- **UpdateRankingCommand**: Modificación de ranking según progreso y logros obtenidos
- **AddBadgeCommand**: Otorgamiento de badges por logros específicos o hitos académicos

**Queries (Consultas):**

Las queries encapsulan operaciones de lectura optimizadas para diferentes casos de uso:

*Profile Retrieval Queries:*
- **GetAllProfilesQuery**: Listado completo de perfiles para administración y leaderboards
- **GetProfileByIdQuery**: Recuperación de perfil específico por identificador único
- **GetProfileByUsernameQuery**: Búsqueda de perfil por username para funcionalidades sociales

*Analytics and Filtering Queries:*
- **GetProfilesByRankingQuery**: Filtrado de perfiles por categoría de ranking para competencias
- **GetProfilesByLevelQuery**: Agrupación de usuarios por nivel académico para análisis
- **GetProfileBadgesQuery**: Recuperación de colección de badges para visualización de logros

**Domain Services:**

Los servicios de dominio coordinan operaciones complejas que trascienden entidades individuales:

*Core Management Services:*
- **ProfileCommandService**: Gestión completa del ciclo de vida de perfiles incluyendo creación y modificaciones
- **ProfileQueryService**: Consultas optimizadas con múltiples criterios de búsqueda y filtrado

*Specialized Services:*
- **UsernameGeneratorService**: Generación automática de usernames únicos cuando el usuario no especifica uno personalizado

**Métodos de Dominio Especializados:**

*Profile Entity Methods:*
- **Profile()**: Constructor por defecto para instanciación básica
- **Profile(firstName, lastName, username, profileUrl)**: Constructor parametrizado para creación completa
- **Profile(CreateProfileCommand, username)**: Constructor específico para integración con Command pattern
- **addExperience(points)**: Adición de puntos con validaciones de rangos y triggers de level-up
- **setLevel(level)**: Actualización de nivel con validaciones de progresión lógica
- **setRanking(ranking)**: Modificación de ranking con verificación de prerrequisitos
- **addBadge(badge)**: Incorporación de badge con validación de duplicados y categorías

*Value Object Methods:*
- **PersonName.getFullName()**: Formateo consistente de nombres completos
- **Username.toString()**: Representación string segura de username
- **ProfileUrl.value()**: Acceso validado a URL de perfil
- **Experience.getPoints()**: Consulta segura de puntos de experiencia

**Reglas de Negocio Encapsuladas:**

1. **Unicidad de Username**: Los usernames deben ser únicos en toda la plataforma
2. **Progresión de Niveles**: Los niveles solo pueden incrementarse basado en experiencia acumulada
3. **Consistencia de Ranking**: El ranking debe ser coherente con el nivel y experiencia del usuario
4. **Validación de URLs**: Las URLs de perfil deben ser válidas y accesibles
5. **Límites de Experiencia**: Los puntos de experiencia tienen rangos válidos definidos
6. **Badges Únicos**: Un usuario no puede recibir el mismo badge múltiples veces
7. **Formato de Nombres**: Los nombres deben cumplir con formatos y longitudes específicas
8. **Integridad de Perfil**: Todos los perfiles deben tener información mínima requerida
9. **Auditoría de Cambios**: Todas las modificaciones de perfil mantienen trazabilidad
10. **Validación de Niveles**: Los niveles deben seguir una progresión lógica y matemática

**Patrones de Gamificación:**

El dominio implementa patrones específicos para motivar el engagement:
- **Progressive Disclosure**: Desbloquer características basado en nivel
- **Achievement Systems**: Badges como reconocimiento de logros específicos
- **Leaderboards**: Rankings para competencia sana entre usuarios
- **Experience Points**: Sistema cuantitativo de progreso
- **Level Progression**: Estructura jerárquica clara de advancement
- **Visual Recognition**: Badges y rankings visualmente distintivos

**Estrategias de Validación:**

- **Input Validation**: Validación exhaustiva de todos los datos de entrada
- **Business Rules Enforcement**: Aplicación automática de reglas de negocio
- **Consistency Checks**: Verificación de consistencia entre experience, level y ranking
- **Duplicate Prevention**: Prevención de duplicados en usernames y badges
- **Format Compliance**: Adherencia a formatos específicos para URLs y nombres

**Consideraciones de Performance:**

- **Lazy Loading**: Carga bajo demanda de badges y métricas detalladas
- **Computed Properties**: Cálculo eficiente de levels basado en experience
- **Indexing Strategy**: Índices optimizados para búsquedas por username y ranking
- **Caching Patterns**: Caché de perfiles frecuentemente consultados

### User Profile Domain
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementDomain.png" alt="User Profile Domain" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.2. Interface Layer
### User Profile Interface
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementInterfaces.png" alt="User Profile Interface" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.3. Application Layer
### User Profile Application
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementApplication.png" alt="User Profile Application" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.4. Infrastructure Layer
### User Profile Infrastructure
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementInfrastructure.png" alt="User Profile Infrastructure" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.5. Bounded Context Software Architecture Component Level Diagrams
<img src="../chapter4/assets/c4/UserProfileComponents.png" alt="User Profile Component Level Diagram" style="display: block; margin: auto; max-width: 100%; height: auto;"/>

#### 4.2.5.6. Bounded Context Software Architecture Code Level Diagrams
##### 4.2.5.6.1. Bounded Context Domain Layer Class Diagrams
##### 4.2.5.6.2. Bounded Context Database Design Diagram
### User Profile Database Design
<img src="../chapter4/assets/ddd-layers/user-profile/ProfileManagementDomainDatabase.png" alt="User Profile Database Design" style="display: block; margin: auto; max-width: 100%; height: auto;"/>
