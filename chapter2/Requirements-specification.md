# 2.4. Requirements specification
## 2.4.1. User Stories.

<div align="justify"


La elaboración de las user stories en esta sección partió de la definición previa de las épicas, que permitieron agrupar los requisitos en bloques funcionales coherentes y alineados con los objetivos del proyecto. Las épicas funcionaron como marcos conceptuales amplios que organizaron las funcionalidades por áreas clave de valor, asegurando que cada conjunto de historias respondiera a una necesidad estratégica concreta identificada en el impact mapping.

A partir de cada épica se redactaron user stories que describen, desde la perspectiva del usuario final, las funcionalidades esperadas y el propósito que persiguen. Estas historias se detallaron con criterios de aceptación claros para definir el comportamiento esperado del sistema y facilitar su validación. Este enfoque permitió transformar objetivos generales en funcionalidades pequeñas, independientes y priorizables, manteniendo la trazabilidad con su épica de origen y con los objetivos de aprendizaje y retención definidos para el proyecto.

De forma complementaria, se definieron technical stories asociadas a las mismas épicas. Estas especifican los componentes técnicos, integraciones, APIs y servicios necesarios para que las user stories puedan implementarse de forma segura y escalable. Así, las user stories representan el valor funcional que recibe el usuario, mientras que las technical stories aseguran la base técnica que lo hace posible, permitiendo planificar y desarrollar el sistema de forma iterativa y coherente.

</div> <br />

<br />






## 2.4.2. Impact Mapping.

<div align="justify"

El presente apartado expone el Impact Mapping, cuyo objetivo es fortalecer el aprendizaje y la permanencia de los estudiantes durante sus primeros ciclos académicos. Esta herramienta permitió vincular de manera sistemática los objetivos estratégicos del proyecto con los comportamientos esperados de sus principales actores, así como con los entregables y funcionalidades necesarios para alcanzarlos.

Para la construcción del mapa, se identificaron dos segmentos clave: los estudiantes de primer ciclo (representados por la persona ficticia Jonatan Velásquez) y los profesores de primeros ciclos (representados por Ariel Maslucan). Ambos segmentos fueron definidos a partir de entrevistas de necesidad (needfinding), donde se exploraron sus motivaciones, dificultades y expectativas frente al uso de la plataforma.

Con base en esta información, se establecieron cinco objetivos estratégicos (Business Goals) medibles y alcanzables:

- Incrementar en un 20 % la tasa de aprobación en cursos introductorios,
- Lograr que el 70 % de estudiantes activos participen al menos una vez por semana en la plataforma,
- Aumentar en 15 % la retención de estudiantes de primero a tercer ciclo,
- Mejorar en 30 % la participación en actividades extracurriculares (Viernes Cultural), y
- Reducir en 25 % la cantidad de tareas no entregadas en cursos introductorios.

Cada uno de estos objetivos se desglosa en el mapa en impactos esperados (impacts) sobre el comportamiento de los estudiantes y profesores; entregables (deliverables) que la plataforma debe implementar para promover dichos cambios; y user stories que especifican, de forma técnica, los requerimientos de cada funcionalidad. De este modo, el Impact Mapping permitió garantizar la coherencia entre las necesidades detectadas en el proceso de investigación y las decisiones de diseño y desarrollo, asegurando que cada funcionalidad propuesta aporte de forma directa y medible al logro de los objetivos del proyecto.

![Impact-Map-1](../chapter2/assets/Impact-Mapping/Impact-Map-1.png)

</div>

## 2.4.3. Product Backlog.

| # Orden | Epic / Story ID | Título                                                       | Descripción                                                  | Story Points |
| ------- | --------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------ |
| 1       | 1 / US01        | Registro de estudiante                                       | Como un estudiante Quiero acceder a la página de Registro Para poder registrarme con mi correo y contraseña | 3            |
| 2       | 1 / US02        | Inicio de sesión de estudiante                               | Como un estudiante Quiero acceder a la página de Inicio de sesión Para poder autenticarme con mi correo y contraseña | 3            |
| 3       | 3 / US03        | Publicación                                                  | Como un profesor Quiero crear una publicación con texto e imágenes Para poder interactuar con mis estudiantes y comunicar eventos | 2            |
| 4       | 3 / US04        | Dar "Me gusta"                                               | Como un estudiante Quiero dar "Me gusta" o "Ya no me gusta" a una publicación de la comunidad Para poder expresar mi opinión y apoyar a los demás | 2            |
| 5       | 3 / US05        | Comentar                                                     | Como un estudiante Quiero escribir un comentario bajo una publicación Para poder participar en la discusión | 1            |
| 6       | 4 / US06        | Panel de Sesión en Vivo                                      | Como un profesor Quiero ver el recuento de estudiantes, la distribución de respuestas y el tiempo de respuesta promedio Para poder monitorear la clase en tiempo real. | 5            |
| 7       | 4 / US07        | Gráfico de Distribución de Respuestas                        | Como un profesor Quiero un gráfico de respuestas (A/B/C/D o números) Para poder identificar rápidamente los conceptos erróneos. | 5            |
| 8       | 4 / US08        | Panel de Tiempo Promedio                                     | Como un profesor Quiero ver el tiempo de respuesta promedio para la pregunta actual Para poder marcar el ritmo de la sesión. | 2            |
| 9       | 5 / US09        | Ver Informe de Resumen de Cuestionario                       | Como un administrador Quiero ver el puntaje promedio, la tasa de participación y el tiempo de respuesta promedio para un cuestionario Para poder evaluar el rendimiento general. | 3            |
| 10      | 5 / US10        | Preguntas Más Difíciles                                      | Como un administrador Quiero una lista de las preguntas más difíciles (tasa de corrección más baja) Para poder detectar conceptos erróneos. | 2            |
| 11      | 6 / US11        | Añadir configuración de perfil a través del Front-end        | Como un estudiante Quiero editar mi perfil (nombre, nombre de usuario, avatar) Para poder personalizar mi experiencia en la plataforma | 1            |
| 12      | 7 / US12        | Añadir progreso para el estudiante a través del Front-end    | Como un estudiante Quiero ver mi nivel, puntos, insignias y racha Para mantenerme motivado y seguir mi crecimiento | 2            |
| 13      | 7 / US13        | Añadir clasificación (leaderboard) a través del Front-end    | Como un estudiante Quiero ver las clasificaciones por alcance (global, clase, desafío) Para poder comparar mi progreso y mantenerme comprometido | 3            |
| 14      | 8 / US14        | Añadir lista unificada de actividades a través del Front-end | Como un estudiante Quiero ver todas mis actividades asignadas en un solo lugar Para poder planificar y priorizar mi tiempo de estudio | 3            |
| 15      | 9 / US15        | Añadir Ver Progreso de la Clase a través del Front-end       | Como un profesor Quiero una visión general del progreso de la clase con métricas clave (finalización, puntaje promedio, entregas tardías) Para poder detectar rápidamente las fortalezas y debilidades de un vistazo. | 2            |
| 16      | 9 / US16        | Ver Progreso del Estudiante (Detalle)                        | Como un profesor Quiero abrir el detalle del progreso de un estudiante Para poder revisar sus actividades completadas/pendientes. | 2            |
| 17      | 9 / US17        | Crear Actividad (Tarea)                                      | Como un profesor Quiero crear una nueva actividad para mi clase Para que los estudiantes puedan ver las instrucciones y una fecha de vencimiento. | 3            |
| 18      | 9 / US18        | Añadir Editar / Cerrar Actividad a través del Front-end      | Como un profesor Quiero editar una actividad existente y opcionalmente cerrar las entregas Para poder corregir detalles y detener el trabajo tardío. | 2            |
| 19      | 10 / US19       | Enviar y ver retroalimentación a través del Front-end        | Como estudiante Quiero ver mi puntaje y una retroalimentación básica justo después de enviar una actividad autocalificable Para saber de inmediato qué hice bien o mal | 2            |
| 20      | 10 / US20       | Consultar retroalimentación de una entrega a través del Front-end | Como estudiante Quiero abrir la retroalimentación de mi entrega Para poder aprender de las explicaciones y de las notas de la rúbrica | 3            |
| 21      | 10 / US21       | Reintentar actividad con nueva retroalimentación             | Como estudiante Quiero volver a intentar una actividad y recibir retroalimentación Para poder mejorar dentro de los intentos permitidos | 1            |
| 22      | 1 / TS01        | Añadir estudiante a través de API RESTful                    | Como Desarrollador quiero añadir un Estudiante a través de la API para que esté disponible para construir funcionalidades para mis aplicaciones. | 3            |
| 23      | 1 / TS02        | Añadir autenticación de estudiante a través de API RESTful   | Como Desarrollador quiero autenticar a un Estudiante a través de la API para que el Estudiante pueda acceder a las funcionalidades protegidas de la aplicación. | 3            |
| 24      | 2 / TS03        | Emisión de Token (Inicio de sesión)                          | Como Desarrollador quiero que la puerta de enlace (gateway) autentique las credenciales y emita tokens para que los servicios posteriores reciban una identidad verificada. | 2            |
| 25      | 3 / TS04        | Publicar a través de API RESTful                             | Como Desarrollador quiero crear una publicación de la comunidad a través de la API para que los profesores puedan publicar contenido validado de forma segura. | 3            |
| 26      | 3 / TS05        | Dar "Me gusta" a través de API                               | Como Desarrollador quiero registrar "Me gusta" y "Ya no me gusta" a través de la API para que las interacciones de los usuarios sean consistentes y seguras. | 1            |
| 27      | 3 / TS06        | Comentar a través de API                                     | Como Desarrollador quiero agregar, validar y almacenar comentarios a través de la API para que los estudiantes puedan interactuar de forma segura bajo las publicaciones. | 2            |
| 28      | 4 / TS07        | API de Ingestión de Eventos                                  | Como Desarrollador quiero ingerir eventos de participación (unirse/responder) para que el agregador pueda calcular métricas en tiempo real. | 2            |
| 29      | 4 / TS08        | API de Transmisión en Tiempo Real                            | Como Desarrollador quiero transmitir instantáneas en vivo a la interfaz de usuario del profesor para que las métricas se actualicen sin sondeo. | 2            |
| 30      | 5 / TS09        | API de Resumen de Cuestionario                               | Como Desarrollador quiero un endpoint para recuperar métricas a nivel de cuestionario para que la UI pueda renderizar el panel de resumen. | 2            |
| 31      | 5 / TS10        | Estadísticas por Pregunta API                                | Como Desarrollador quiero un endpoint para recuperar estadísticas por pregunta para que la UI pueda mostrar las preguntas más difíciles y los detalles. | 2            |
| 32      | 6 / TS11        | Añadir crear perfil a través de API                          | Como Desarrollador quiero crear un perfil de usuario a través de la API para que los nuevos usuarios puedan inicializar su perfil. | 2            |
| 33      | 6 / TS12        | Añadir actualizar perfil a través de API                     | Como Desarrollador quiero actualizar un perfil de usuario existente a través de la API para que los usuarios puedan editar su nombre, nombre de usuario y avatar. | 1            |
| 34      | 7 / TS13        | Añadir progreso a través de API                              | Como Desarrollador quiero devolver el progreso actual (nivel, puntos, insignias, racha) para que el panel del estudiante pueda ser renderizado. | 1            |
| 35      | 7 / TS14        | Añadir clasificación (leaderboard) a través de API           | Como Desarrollador quiero un endpoint de clasificación unificado para que el cliente pueda obtener rangos por alcance y período. | 2            |
| 36      | 8 / TS15        | Añadir lista de actividades del estudiante a través de API   | Como Desarrollador, quiero obtener las actividades de un estudiante a través de la API para que el Front-end pueda mostrarlas en "Mis Actividades". | 3            |
| 37      | 8 / TS16        | Añadir detalles de la actividad a través de API              | Como Desarrollador, quiero recuperar los detalles de la actividad para que los estudiantes puedan ver instrucciones, enlaces y opciones de entrega. | 3            |
| 38      | 9 / TS17        | API de Progreso (a nivel de clase)                           | Como Desarrollador quiero un endpoint para recuperar el progreso de la clase (métricas simples + filas de estudiantes) para que la UI pueda renderizar la vista de progreso. | 3            |
| 39      | 9 / TS18        | API de Creación de Actividad                                 | Como Desarrollador, quiero un endpoint para recuperar la lista de actividades de un solo estudiante en una clase para que la UI pueda mostrar sus detalles. | 3            |
| 40      | 10 / TS19       | API  de Creación de entrega con retroalimentación inmediata  | Como desarrollador Quiero un endpoint que cree una entrega y (si es autocalificable) devuelva retroalimentación inmediata Para que los estudiantes puedan leer los resultados de inmediato | 3            |
| 41      | 10 / TS20       | API de Política de visibilidad de retroalimentación (simple) | Como desarrollador Quiero exponer la política de visibilidad de retroalimentación/soluciones de una actividad Para que los estudiantes sepan qué podrán leer después de enviar su entrega | 2            |
| 42      | 1 / SP01        | WebSocket + OAuth2 para Sesiones en Vivo                     | Como equipo de desarrollo Queremos investigar cómo integrar WebSocket con OAuth2 y JWT Para documentar un método seguro de establecer sesiones en vivo con autenticación válida. | 3            |
| 43      | 2 / SP02        | API Gateway para Autenticación y Rate Limiting               | Como equipo de desarrollo Queremos evaluar el uso de un API Gateway Para definir una estrategia centralizada de autenticación, límites de uso y enrutamiento hacia los microservicios. | 3            |
| 44      | 3 / SP03        | Apache Kafka para Respuestas en Vivo                         | Como equipo de desarrollo Queremos investigar el uso de Apache Kafka para procesar respuestas en tiempo real Para identificar una arquitectura que permita calcular métricas de sesión sin afectar el rendimiento. | 2            |
| 45      | 3 / SP04        | Proveedor PostgreSQL: Aiven                                  | Como equipo de desarrollo Queremos evaluar a Aiven como proveedor de PostgreSQL gestionado Para determinar si cumple con los requisitos de alta disponibilidad, seguridad y respaldos automáticos de nuestra base de datos principal. | 2            |
| 46      | 3 / SP05        | Spring Data Mongo para Social Feed                           | Como equipo de desarrollo Queremos investigar el uso de Spring Data MongoDB Para validar si soporta publicaciones, comentarios y reacciones con el rendimiento y escalabilidad que necesitamos en la parte social. | 1            |
| 47      | 4 / SP06        | Observabilidad en Tiempo Real con OpenTelemetry              | Como equipo de desarrollo Queremos explorar el uso de OpenTelemetry junto con Prometheus y Grafana Para establecer una solución de monitoreo en tiempo real de métricas, trazas y errores que garantice la calidad de servicio. | 5            |
