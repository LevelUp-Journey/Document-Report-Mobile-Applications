# Capítulo III: Requirements specification
## 3.1. To-Be Scenario Mapping.

<div align="justify"

- **Segmento Objetivo 1: Estudiantes**

Para el estudiante, el TO-BE introduce un ciclo de práctica con editor embebido, validación automática y retroalimentación instantánea. Además, los sistemas de progreso, rankings e insignias convierten el aprendizaje en un proceso motivador y continuo, en lugar de depender exclusivamente de las notas finales. El resultado es una experiencia más clara, dinámica y atractiva, que fomenta tanto la autonomía como la constancia en el estudio.

<img src="https://i.imgur.com/UPDYumb.png" alt="TOBE1"/>

- **Segmento Objetivo 2: Profesores**

Para el docente, la plataforma centraliza la gestión de retos y automatiza la retroalimentación inicial. Esto le permite dedicar menos tiempo a tareas repetitivas y más a la orientación pedagógica. Los dashboards con métricas de avance facilitan la detección temprana de estudiantes en riesgo y reducen la carga administrativa. La proyección TO-BE ofrece, en consecuencia, una experiencia más sostenible, eficiente y alineada con las necesidades académicas.

<img src="https://i.imgur.com/AiK7wYp.png" alt="TOBE1"/>

</div>

## 3.2. User Stories.

Historias de Usuario
<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US01</td>
<td>Estudiante</td>
<td>1</td>
<td>IAM</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Registro de estudiante</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero acceder a la página de Registro para poder registrarme con mi correo y contraseña.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: El usuario abre la página de Registro</b><br>Dado que el usuario no está autenticado<br>Cuando el usuario navega a la página de "Registro"<br>Entonces el sistema muestra el formulario de registro<br>Y el usuario puede registrarse</li>
<li><b>Escenario: El usuario se registra exitosamente</b><br>Dado que la página de Registro está visible<br>Cuando el usuario ingresa una entrada válida y procede al registro<br>Entonces el sistema valida la entrada<br>Y el sistema redirige al usuario a la página de Inicio de sesión</li>
<li><b>Escenario: Campo de entrada vacío</b><br>Dado que la página de Registro está visible<br>Cuando el usuario deja un campo de entrada vacío y procede al registro<br>Entonces el sistema muestra un mensaje de error</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US02</td>
<td>Estudiante</td>
<td>1</td>
<td>IAM</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Inicio de sesión de estudiante</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero acceder a la página de Inicio de sesión para poder autenticarme con mi correo y contraseña.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: El estudiante abre la página de Inicio de sesión</b><br>Dado que el estudiante no está autenticado<br>Cuando el estudiante navega a la página de "Inicio de sesión"<br>Entonces el sistema muestra el formulario de autenticación<br>Y el estudiante puede iniciar sesión</li>
<li><b>Escenario: El estudiante inicia sesión exitosamente</b><br>Dado que la página de Inicio de sesión está visible<br>Cuando el estudiante ingresa credenciales válidas<br>Entonces el sistema valida la entrada<br>Y el estudiante accede a la plataforma</li>
<li><b>Escenario: Entrada vacía</b><br>Dado que la página de Inicio de sesión está visible<br>Cuando el estudiante envía sin completar un campo requerido<br>Entonces el sistema muestra un mensaje de error</li>
<li><b>Escenario: Credenciales incorrectas</b><br>Dado que la página de Inicio de sesión está visible<br>Cuando el estudiante ingresa credenciales inválidas<br>Entonces el sistema muestra un mensaje de error<br>Y el estudiante permanece en la página de Inicio de sesión</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US03</td>
<td>Profesor</td>
<td>3</td>
<td>Community</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Crear, editar y eliminar una publicación</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero crear una publicación con texto e imágenes para poder interactuar con mis estudiantes y comunicar eventos.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: El profesor abre la página de Crear publicación</b><br>Dado que el profesor está autenticado<br>Cuando el profesor navega a "Comunidad > Nueva publicación"<br>Entonces el sistema muestra un formulario con: área de texto, entrada de imagen opcional, sección de vista previa y opción de publicar (deshabilitada hasta que sea válida).</li>
<li><b>Escenario: El profesor crea una publicación solo de texto exitosamente</b><br>Dado que el formulario "Nueva publicación" está visible<br>Cuando el profesor ingresa texto válido y no se proporciona ninguna imagen<br>Entonces el sistema publica la publicación<br>Y muestra un mensaje de éxito<br>Y la nueva publicación aparece en el feed de la comunidad</li>
<li><b>Escenario: Editar una publicación exitosamente</b><br>Dado que el profesor está autenticado y el profesor tiene una publicación existente<br>Cuando el profesor edita la publicación con cambios válidos<br>Entonces el sistema actualiza la publicación<br>Y la versión actualizada se muestra en el feed de la comunidad<br>Y se muestra un mensaje de confirmación</li>
<li><b>Escenario: Eliminar una publicación exitosamente</b><br>Dado que el profesor está autenticado y el profesor tiene una publicación existente<br>Cuando el profesor elimina la publicación<br>Entonces el sistema la elimina del feed de la comunidad<br>Y se muestra un mensaje de confirmación</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US04</td>
<td>Estudiante</td>
<td>3</td>
<td>Community</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Dar "Me gusta" a una publicación</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero dar "Me gusta" o "Ya no me gusta" a una publicación de la comunidad para poder expresar mi opinión y apoyar a los demás.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Dar "Me gusta" a una publicación exitosamente</b><br>Dado que el estudiante está autenticado y el feed de la comunidad está visible<br>Cuando el estudiante da "Me gusta" a una publicación<br>Entonces la opción cambia a "Ya no me gusta"<br>Y el contador de "Me gusta" aumenta en 1<br>Y se muestra un mensaje de confirmación</li>
<li><b>Escenario: Ya no me gusta una publicación exitosamente</b><br>Dado que el estudiante ya ha dado "Me gusta" a una publicación<br>Cuando el estudiante ya no da "Me gusta" a la publicación<br>Entonces la opción cambia de nuevo a "Me gusta"<br>Y el contador de "Me gusta" disminuye en 1<br>Y se muestra un mensaje de confirmación</li>
<li><b>Escenario: Prevenir múltiples envíos</b><br>Dado que el estudiante intenta dar "Me gusta" a una publicación repetidamente<br>Entonces el sistema procesa solo una acción<br>Y el contador refleja un solo "Me gusta"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US05</td>
<td>Estudiante</td>
<td>3</td>
<td>Community</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Comentar una publicación</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero escribir un comentario bajo una publicación para poder participar en la discusión.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Añadir comentario válido</b><br>Dado que el estudiante está autenticado y la vista de detalles de la publicación está abierta<br>Cuando el estudiante ingresa texto entre 3 y 500 caracteres<br>Entonces el comentario se muestra bajo la publicación<br>Y se muestra un mensaje de confirmación</li>
<li><b>Escenario: Comentario vacío</b><br>Dado que la vista de detalles de la publicación está abierta<br>Cuando el estudiante envía sin ingresar texto<br>Entonces el sistema muestra un error "El comentario no puede estar vacío"</li>
<li><b>Escenario: Comentario demasiado largo</b><br>Dado que la vista de detalles de la publicación está abierta<br>Cuando el estudiante ingresa más de 500 caracteres<br>Entonces el sistema muestra un error "El comentario no debe exceder los 500 caracteres"</li>
<li><b>Escenario: Caracteres no admitidos en el comentario</b><br>Dado que la vista de detalles de la publicación está abierta<br>Cuando el estudiante ingresa texto con caracteres no admitidos<br>Entonces el sistema muestra un error "Se detectaron caracteres no admitidos"<br>Y el comentario no se publica</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US06</td>
<td>Profesor</td>
<td>4</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Panel de Sesión en Vivo</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero ver el recuento de estudiantes, la distribución de respuestas y el tiempo de respuesta promedio para poder monitorear la clase en tiempo real.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Ver métricas en vivo para una sesión</b><br>Dado que estoy asignado a la clase "cls_CS101_2025_2" y la sesión "ses_01A" está activa<br>Cuando abro "Análisis en vivo"<br>Entonces veo el recuento de estudiantes, total de respuestas, tiempo de respuesta promedio en ms<br>Y veo la distribución de respuestas para la pregunta actual</li>
<li><b>Escenario: Aún no hay respuestas</b><br>Dado que la sesión "ses_01A" está activa con cero respuestas<br>Cuando abro "Análisis en vivo"<br>Entonces veo "Esperando respuestas..." y el recuento de estudiantes</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US07</td>
<td>Profesor</td>
<td>4</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Gráfico de Distribución de Respuestas</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero un gráfico de respuestas (A/B/C/D o números) para poder identificar rápidamente los conceptos erróneos.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Mostrar distribución categórica</b><br>Dado que la pregunta actual es de opción múltiple<br>Cuando llegan las respuestas<br>Entonces el gráfico muestra los recuentos por opción (A, B, C, D)</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US08</td>
<td>Profesor</td>
<td>4</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Panel de Tiempo Promedio</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero ver el tiempo de respuesta promedio para la pregunta actual para poder marcar el ritmo de la sesión.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Mostrar tiempo de respuesta promedio</b><br>Dado que las respuestas incluyen el tiempo<br>Cuando veo "Tiempo"<br>Entonces veo el tiempo de respuesta promedio en ms para la pregunta actual</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US09</td>
<td>Administrador</td>
<td>5</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Ver Informe de Resumen de Cuestionario</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un administrador, quiero ver el puntaje promedio, la tasa de participación y el tiempo de respuesta promedio para un cuestionario para poder evaluar el rendimiento general.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Ver resumen de cuestionario</b><br>Dado que soy un administrador y el cuestionario "quiz_1001" tiene entregas calificadas<br>Cuando abro "Informes de cuestionario" para quiz_1001<br>Entonces veo avgScore, participationRate, averageResponseTimeMs<br>Y los filtros de rango de tiempo y clase aplicados son visibles</li>
<li><b>Escenario: No hay datos en el rango</b><br>Dado que no hay entregas calificadas en el rango de fechas seleccionado<br>Cuando veo el informe<br>Entonces veo "No hay datos para el rango seleccionado"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US10</td>
<td>Administrador</td>
<td>5</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Preguntas Más Difíciles</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un administrador, quiero una lista de las preguntas más difíciles (tasa de corrección más baja) para poder detectar conceptos erróneos.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Listar las preguntas más difíciles</b><br>Dado que quiz_1001 tiene resultados a nivel de pregunta<br>Cuando abro "Preguntas más difíciles"<br>Entonces veo una tabla con questionId, correctnessRate, attempts, avgTimeMs<br>Y la tabla está ordenada de forma ascendente por correctnessRate</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US11</td>
<td>Estudiante</td>
<td>6</td>
<td>User Profile</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir configuración de perfil a través del Front-end</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero editar mi perfil (nombre, nombre de usuario, avatar) para poder personalizar mi experiencia en la plataforma.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Abrir Configuración de perfil</b><br>Dado que el estudiante está autenticado<br>Cuando el estudiante navega a "Cuenta > Perfil"<br>Entonces el sistema muestra un formulario con: Nombre completo (requerido), Nombre de usuario (requerido), URL del avatar (opcional, solo http/https), Institución (requerido) y opción de guardar (deshabilitada hasta que sea válida).</li>
<li><b>Escenario: Actualizar nombre completo exitosamente</b><br>Dado que el formulario de Perfil está visible<br>Cuando el estudiante ingresa un nombre válido de 3 a 80 caracteres (conjunto de caracteres latinos)<br>Entonces el sistema actualiza el perfil<br>Y el encabezado refleja el nuevo nombre<br>Y se muestra un mensaje de confirmación</li>
<li><b>Escenario: Actualizar nombre de usuario exitosamente</b><br>Dado que el formulario de Perfil está visible<br>Cuando el estudiante ingresa un nombre de usuario válido y disponible (3-24, letras/números/guiones bajos, comienza con letra)<br>Entonces el perfil se actualiza con el nuevo nombre de usuario<br>Y se muestra un mensaje de confirmación</li>
<li><b>Escenario: Nombre de usuario ya tomado</b><br>Dado que el formulario de Perfil está visible<br>Cuando el estudiante ingresa un nombre de usuario que ya existe<br>Entonces el sistema muestra un error "El nombre de usuario ya está tomado"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US12</td>
<td>Estudiante</td>
<td>7</td>
<td>User Profile</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Ver progreso del estudiante a través del Front-end</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero ver mi nivel, puntos, insignias y racha para mantenerme motivado y seguir mi crecimiento.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Abrir el Panel de progreso</b><br>Dado que el estudiante está autenticado<br>Cuando el estudiante navega a "Progreso"<br>Entonces el sistema muestra: nivel actual con barra de progreso al siguiente nivel, puntos totales y puntos semanales, las últimas 5 insignias con información sobre herramientas, racha actual y más larga y enlaces para ver todas las insignias y el historial.</li>
<li><b>Escenario: Ver historial de puntos (últimos 30 días)</b><br>Dado que la página de Progreso está visible<br>Cuando el estudiante selecciona la opción de los últimos 30 días<br>Entonces un gráfico de líneas diario muestra los puntos ganados por día<br>Y al pasar el mouse se muestra la fecha y los puntos</li>
<li><b>Escenario: Estado vacío para nuevos estudiantes</b><br>Dado que el estudiante no tiene puntos ni insignias<br>Cuando se muestra la página de Progreso<br>Entonces el sistema muestra un estado vacío alentador con consejos para empezar desafíos</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US13</td>
<td>Estudiante</td>
<td>7</td>
<td>User Profile</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Ver clasificación (leaderboard)</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero ver las clasificaciones por alcance (global, clase, desafío) para poder comparar mi progreso y mantenerme comprometido.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Ver clasificación Global (Histórico)</b><br>Dado que el estudiante está autenticado<br>Cuando el estudiante abre "Clasificaciones" y selecciona el alcance "Global" y el período "Todos"<br>Entonces el sistema muestra una tabla paginada con: Puesto #, Nombre de usuario, Nivel, Puntos y mi fila resaltada (incluso si no está en la página actual).</li>
<li><b>Escenario: Ver clasificación de Clase (semanal) con membresía</b><br>Dado que el estudiante está inscrito en la clase "CS-101"<br>Cuando el estudiante selecciona el alcance "Clase" y la clase "CS-101" y el período "Semanal"<br>Entonces la tabla muestra a los mejores estudiantes de esa clase esta semana<br>Y los empates se resuelven por: 1) Nivel más alto y 2) Marca de tiempo de logro más temprana</li>
<li><b>Escenario: Ver clasificación de Desafío (este desafío)</b><br>Dado que el estudiante abre los detalles de un desafío<br>Cuando el estudiante cambia a la pestaña "Clasificación"<br>Entonces la tabla muestra el puesto solo para este desafío<br>Y solo aparecen los estudiantes con una entrega válida</li>
<li><b>Escenario: Filtros y paginación</b><br>Dado que la clasificación está visible<br>Cuando el estudiante cambia el período a "Mensual" y la página a 2<br>Entonces la tabla se actualiza con los resultados correctos</li>
<li><b>Escenario: Privacidad y visibilidad</b><br>Dado que algunos estudiantes tienen la privacidad configurada para “ocultar nombre”<br>Cuando se renderiza la clasificación<br>Entonces esas entradas muestran nombres enmascarados (ej. "Student-****")<br>Y mi propia entrada siempre es totalmente visible para mí</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US14</td>
<td>Estudiante</td>
<td>8</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Lista unificada de actividades</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un estudiante, quiero ver todas mis actividades asignadas en un solo lugar para poder planificar y priorizar mi tiempo de estudio.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Abrir "Mis Actividades"</b><br>Dado que el estudiante está autenticado<br>Cuando el estudiante navega a "Clase > Mis Actividades"<br>Entonces el sistema muestra una lista paginada con columnas: Título, Tipo (Desafío/Cuestionario/Laboratorio/Asignación), Clase (ej. CS-101), Fecha de vencimiento (hora local), Tiempo estimado (minutos) y Estado (Asignado/En progreso/Entregado/Calificado/Vencido).</li>
<li><b>Escenario: Filtrar y ordenar actividades</b><br>Dado que la lista de actividades está visible<br>Cuando el estudiante filtra por Estado=Asignado y Fecha de vencimiento=Esta semana<br>Y ordena por Fecha de vencimiento de forma ascendente<br>Entonces la lista se actualiza en consecuencia</li>
<li><b>Escenario: Buscar por palabra clave</b><br>Dado que la lista de actividades está visible<br>Cuando el estudiante busca "Arreglos C++"<br>Entonces solo se muestran las actividades cuyo título o descripción contiene el término</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US15</td>
<td>Profesor</td>
<td>9</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Ver Progreso de la Clase</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero una visión general del progreso de la clase con métricas clave (finalización, puntaje promedio, entregas tardías) para poder detectar rápidamente las fortalezas y debilidades de un vistazo.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Ver progreso de una clase</b><br>Dado que estoy asignado a la clase "cls_CS101_2025_2"<br>Cuando abro "Progreso de la clase"<br>Entonces veo completionRate y avgScore para la clase<br>Y una tabla de estudiantes con % de finalización y lastSubmissionAt</li>
<li><b>Escenario: Aún no hay datos</b><br>Dado que la clase no tiene actividades<br>Cuando abro "Progreso de la clase"<br>Entonces veo el mensaje "Aún no hay actividades"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US16</td>
<td>Profesor</td>
<td>9</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Ver Progreso del Estudiante (Detalle)</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero abrir el detalle del progreso de un estudiante para poder revisar sus actividades completadas/pendientes.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Abrir detalle del estudiante</b><br>Dado que estoy en "Progreso de la clase"<br>Cuando selecciono al estudiante "std_01R"<br>Entonces veo su lista de actividades con título, estado, dueAt, puntaje</li>
<li><b>Escenario: Estudiante sin entregas</b><br>Dado que el estudiante "std_01R" no tiene entregas<br>Cuando abro su detalle<br>Entonces veo "Aún no hay entregas"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US17</td>
<td>Profesor</td>
<td>9</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Crear Actividad (Tarea)</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero crear una nueva actividad para mi clase para que los estudiantes puedan ver las instrucciones y una fecha de vencimiento.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Crear una tarea básica</b><br>Dado que estoy asignado a "cls_CS101_2025_2"<br>Cuando creo una actividad con título, descripción y dueAt<br>Entonces la actividad aparece en la lista de actividades de la clase con el estado "BORRADOR"</li>
<li><b>Escenario: Publicar la actividad</b><br>Dado que una actividad está en "BORRADOR"<br>Cuando la publico<br>Entonces los estudiantes de la clase pueden verla en sus actividades</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US18</td>
<td>Profesor</td>
<td>9</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Editar / Cerrar Actividad</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como un profesor, quiero editar una actividad existente y opcionalmente cerrar las entregas para poder corregir detalles y detener el trabajo tardío.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Editar título y fecha de vencimiento</b><br>Dado que la actividad está en "BORRADOR"<br>Cuando actualizo el título y la dueAt<br>Entonces los cambios se guardan</li>
<li><b>Escenario: Cerrar entregas</b><br>Dado que la actividad está "PUBLICADA"<br>Cuando configuro "acceptSubmissions" en falso<br>Entonces los estudiantes ya no pueden entregar</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US19</td>
<td>Estudiante</td>
<td>10</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Enviar y ver retroalimentación</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como estudiante, quiero ver mi puntaje y una retroalimentación básica justo después de enviar una actividad autocalificable para saber de inmediato qué hice bien o mal.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Retroalimentación inmediata tras el envío</b><br>Dado que la actividad "act_QZ1" está PUBLICADA y es autocalificable<br>Y estoy matriculado en la clase "cls_CS101_2025_2"<br>Cuando envío mis respuestas<br>Entonces veo mi puntaje y la corrección por ítem<br>Y veo una breve explicación para cada ítem incorrecto (si está permitido)</li>
<li><b>Escenario: Política de retroalimentación oculta las soluciones</b><br>Dado que showSolutions=false<br>Cuando envío mis respuestas<br>Entonces solo veo mi puntaje<br>Y veo el mensaje "Las soluciones están ocultas para esta actividad"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US20</td>
<td>Estudiante</td>
<td>10</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Consultar retroalimentación de una entrega</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como estudiante, quiero abrir la retroalimentación de mi entrega para poder aprender de las explicaciones y de las notas de la rúbrica.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Abrir retroalimentación</b><br>Dado que tengo una entrega exitosa para "act_QZ1"<br>Cuando abro "Ver retroalimentación"<br>Entonces veo los resultados pregunta por pregunta, las explicaciones (si están permitidas) y el puntaje total</li>
<li><b>Escenario: Actividad no autocalificable</b><br>Dado que el tipo de actividad es TAREA (calificación manual)<br>Cuando envío mi entrega<br>Entonces veo "Entrega recibida retroalimentación pendiente"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>US21</td>
<td>Estudiante</td>
<td>10</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Reintentar actividad con nueva retroalimentación</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como estudiante, quiero volver a intentar una actividad y recibir retroalimentación para poder mejorar dentro de los intentos permitidos.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Reintentar dentro de los intentos permitidos</b><br>Dado que la actividad "act_QZ1" permite múltiples intentos (maxAttempts = 3)<br>Y ya he enviado una vez<br>Cuando hago clic en "Reintentar actividad"<br>Entonces puedo enviar un nuevo intento<br>Y el intento anterior sigue visible como "Intento 1"</li>
<li><b>Escenario: Retroalimentación actualizada después de reintentar</b><br>Dado que he enviado un segundo intento para "act_QZ1"<br>Cuando se completa la calificación manual o automática<br>Entonces veo el puntaje actualizado y la retroalimentación por ítem del Intento 2<br>Y puedo compararla con la retroalimentación del Intento 1</li>
<li><b>Escenario: No hay más intentos disponibles</b><br>Dado que la actividad "act_QZ1" tiene maxAttempts = 3<br>Y ya he enviado 3 intentos<br>Cuando intento hacer clic en "Reintentar actividad"<br>Entonces veo el mensaje "No se permiten más intentos para esta actividad"<br>Y el botón "Reintentar actividad" aparece deshabilitado</li>
</ul>
</td>
</tr>
</table>

Historias Técnicas
<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS01</td>
<td>Desarrollador</td>
<td>1</td>
<td>IAM</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir estudiante a través de API RESTful</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero añadir un Estudiante a través de la API para que esté disponible para construir funcionalidades para mis aplicaciones.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Añadir estudiante con correo único</b><br>Dado que el endpoint /api/v1/authentication/sign-up está disponible<br>Cuando se envía una solicitud POST con valores para correo, contraseña y nombre<br>Y el correo no existe en la base de datos<br>Entonces se recibe una respuesta con Estado 201<br>Y un Recurso de Estudiante se incluye en el Cuerpo de la Respuesta con: un nuevo ID generado, valores registrados para correo y nombre, rol: STUDENT<br>Y la contraseña se almacena con hash de BCrypt</li>
<li><b>Escenario: Añadir estudiante con correo existente</b><br>Dado que el endpoint /api/v1/authentication/sign-up está disponible<br>Cuando se envía una solicitud POST con valores para correo, contraseña y nombre<br>Y un Recurso de Estudiante con el mismo correo ya está almacenado<br>Entonces se recibe una respuesta con Estado 400<br>Y un mensaje se incluye en el Cuerpo de la Respuesta: Usuario con correo student@example.com ya existe</li>
<li><b>Escenario: Formato de correo inválido</b><br>Dado que el endpoint /api/v1/authentication/sign-up está disponible<br>Cuando se envía una solicitud POST con un correo formateado incorrectamente (ej. invalid-email)<br>Entonces se recibe una respuesta con Estado 400<br>Y un mensaje se incluye: Formato de correo inválido</li>
<li><b>Escenario: Faltan campos requeridos</b><br>Dado que el endpoint /api/v1/authentication/sign-up está disponible<br>Cuando se envía una solicitud POST sin correo o contraseña<br>Entonces se recibe una respuesta con Estado 400<br>Y un mensaje se incluye: La dirección de correo y la contraseña son requeridas</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS02</td>
<td>Desarrollador</td>
<td>1</td>
<td>IAM</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir autenticación de estudiante a través de API RESTful</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero autenticar a un Estudiante a través de la API para que el Estudiante pueda acceder a las funcionalidades protegidas de la aplicación.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Autenticación exitosa con credenciales válidas</b><br>Dado que el endpoint /api/v1/authentication/sign-in está disponible<br>Cuando se envía una solicitud POST con valores para correo y contraseña: correo: &quot;student@example.com&quot;, contraseña: &quot;correctPassword123&quot;<br>Y las credenciales son válidas en la base de datos<br>Entonces se recibe una respuesta con Estado 200 (OK)<br>Y un Recurso de Usuario Autenticado se incluye en el Cuerpo de la Respuesta con: id: &quot;uuid-generado&quot;, email_address: &quot;student@example.com&quot;, token: &quot;jwt-token-aqui&quot;, roles: [&quot;ROLE_STUDENT&quot;]<br>Y el token JWT es válido por 1 hora (según la configuración)</li>
<li><b>Escenario: Autenticación fallida con credenciales incorrectas</b><br>Dado que el endpoint /api/v1/authentication/sign-in está disponible<br>Cuando se envía una solicitud POST con credenciales incorrectas: correo: &quot;student@example.com&quot;, contraseña: &quot;wrongPassword&quot;<br>Entonces se recibe una respuesta con Estado 401 (No autorizado)<br>Y un mensaje se incluye en el Cuerpo de la Respuesta: "Correo o contraseña inválidos"</li>
<li><b>Escenario: Autenticación con usuario no existente</b><br>Dado que el endpoint /api/v1/authentication/sign-in está disponible<br>Cuando se envía una solicitud POST con un correo que no existe: correo: &quot;nonexistent@example.com&quot;, contraseña: &quot;anyPassword123&quot;<br>Entonces se recibe una respuesta con Estado 401 (No autorizado)<br>Y un mensaje se incluye en el Cuerpo de la Respuesta: "Correo o contraseña inválidos"</li>
<li><b>Escenario: Formato de correo inválido</b><br>Dado que el endpoint /api/v1/authentication/sign-in está disponible<br>Cuando se envía una solicitud POST con un correo mal formateado: correo: &quot;invalid-email-format&quot;, contraseña: &quot;validPassword123&quot;<br>Entonces se recibe una respuesta con Estado 400 (Solicitud incorrecta)<br>Y un mensaje se incluye: "Formato de correo inválido"</li>
<li><b>Escenario: Faltan campos requeridos</b><br>Dado que el endpoint /api/v1/authentication/sign-in está disponible<br>Cuando se envía una solicitud POST sin correo o contraseña<br>Entonces se recibe una respuesta con Estado 400 (Solicitud incorrecta)<br>Y un mensaje se incluye: "La dirección de correo y la contraseña son requeridas"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS03</td>
<td>Desarrollador</td>
<td>2</td>
<td>API Gateway</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Emisión de Token (Inicio de sesión)</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero que la puerta de enlace (gateway) autentique las credenciales y emita tokens para que los servicios posteriores reciban una identidad verificada.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Emitir tokens con credenciales válidas</b><br>Dado que el usuario existe y el hash de la contraseña coincide<br>Cuando POST /auth/login con cuerpo válido<br>Entonces 200 con accessToken (JWT) y refreshToken</li>
<li><b>Escenario: Rechazar credenciales inválidas</b><br>Cuando POST /auth/login con contraseña incorrecta<br>Entonces 401 con título "Unauthorized"</li>
<li><b>Escenario: Forzar bloqueo</b><br>Dado 5 intentos fallidos en 10 minutos<br>Cuando POST /auth/login<br>Entonces 423 con título "Account Locked"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS04</td>
<td>Desarrollador</td>
<td>3</td>
<td>Community</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Publicar a través de API RESTful</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero crear una publicación de la comunidad a través de la API para que los profesores puedan publicar contenido validado de forma segura.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Crear publicación con texto válido y una URL de imagen</b><br>Dado que el endpoint /api/v1/community/posts está disponible<br>Y el solicitante tiene ROLE_PROFESSOR<br>Cuando se envía una solicitud POST con: texto: "Nos vemos en el taller del viernes. Material en el enlace.", imágenes: [&quot;https://cdn.example.com/materiales/banner.png&quot;]<br>Entonces se devuelve 201<br>Y un Recurso de Publicación con un id generado es devuelto<br>Y la URL de la imagen se almacena como un campo URL en la base de datos<br>Y un evento de auditoría community.post.created es registrado</li>
<li><b>Escenario: Crear publicación solo de texto</b><br>Dado que el endpoint está disponible<br>Y el solicitante tiene ROLE_PROFESSOR<br>Cuando se envía una solicitud POST con: texto: "Recordatorio: entrega del reto 2 el domingo 23:59.", imágenes: []<br>Entonces se devuelve 201<br>Y la publicación no contiene imágenes<br>Y un evento de auditoría community.post.created es registrado</li>
<li><b>Escenario: Rechazar URL de imagen no HTTP/HTTPS</b><br>Dado que el endpoint está disponible<br>Y el solicitante tiene ROLE_PROFESSOR<br>Cuando se envía una solicitud POST con: texto: "Adjunto imagen del diagrama.", imágenes: [&quot;ftp://example.com/diagram.jpg&quot;]<br>Entonces se devuelve 400<br>Y el mensaje incluye "La URL de la imagen debe usar HTTP o HTTPS"</li>
<li><b>Escenario: Actualizar publicación con nuevo texto y URL de imagen</b><br>Dado que el endpoint /api/v1/community/posts/{id} está disponible<br>Y el solicitante tiene ROLE_PROFESSOR<br>Y el solicitante es dueño de la publicación<br>Cuando se envía una solicitud PUT con: texto: "Actualización: el taller se movió al sábado.", imágenes: [&quot;https://cdn.example.com/materiales/updated-banner.png&quot;]<br>Entonces se devuelve 200<br>Y el Recurso de Publicación refleja el nuevo texto y la URL de la imagen<br>Y un evento de auditoría community.post.updated es registrado</li>
<li><b>Escenario: Eliminar publicación exitosamente</b><br>Dado que el endpoint /api/v1/community/posts/{id} está disponible<br>Y el solicitante tiene ROLE_PROFESSOR<br>Y el solicitante es dueño de la publicación<br>Cuando se envía una solicitud DELETE<br>Entonces se devuelve 204<br>Y la publicación ya no es recuperable<br>Y un evento de auditoría community.post.deleted es registrado</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS05</td>
<td>Desarrollador</td>
<td>3</td>
<td>Community</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Dar "Me gusta" a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero registrar "Me gusta" y "Ya no me gusta" a través de la API para que las interacciones de los usuarios sean consistentes y seguras.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Dar "Me gusta" a la publicación exitosamente</b><br>Dado que el endpoint /api/v1/community/posts/{id}/like está disponible<br>Cuando se envía una solicitud POST con un token válido<br>Entonces se devuelve el Estado 200<br>Y el cuerpo de la respuesta incluye el likeCount actualizado</li>
<li><b>Escenario: Ya no me gusta la publicación exitosamente</b><br>Dado que el endpoint /api/v1/community/posts/{id}/like está disponible<br>Cuando se envía una solicitud DELETE con un token válido<br>Entonces se devuelve el Estado 200<br>Y el likeCount disminuye en 1</li>
<li><b>Escenario: Intento de doble "Me gusta"</b><br>Cuando se envía una solicitud POST dos veces para el mismo usuario y publicación<br>Entonces la segunda solicitud devuelve 200<br>Y el likeCount permanece igual</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS06</td>
<td>Desarrollador</td>
<td>3</td>
<td>Community</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Comentar a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero agregar, validar y almacenar comentarios a través de la API para que los estudiantes puedan interactuar de forma segura bajo las publicaciones.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Agregar comentario válido</b><br>Dado que el endpoint /api/v1/community/posts/{id}/comments está disponible<br>Cuando se envía una solicitud POST con: texto: "Buen trabajo, este material es claro"<br>Entonces se devuelve el Estado 201<br>Y el Recurso de Comentario incluye id, authorId, text, createdAt</li>
<li><b>Escenario: Rechazar comentario vacío</b><br>Cuando se envía una solicitud POST con texto: &quot;&quot;<br>Entonces se devuelve el Estado 400<br>Y el mensaje "El comentario no puede estar vacío" se incluye</li>
<li><b>Escenario: Rechazar texto demasiado largo</b><br>Cuando se envía una solicitud POST con texto más largo de 500 caracteres<br>Entonces se devuelve el Estado 400<br>Y el mensaje "El comentario no debe exceder los 500 caracteres" se incluye</li>
<li><b>Escenario: Rechazar caracteres no admitidos</b><br>Cuando se envía una solicitud POST con texto que contiene 汉字<br>Entonces se devuelve el Estado 400<br>Y el mensaje "Caracteres no admitidos detectados" se incluye</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS07</td>
<td>Desarrollador</td>
<td>4</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">API de Ingestión de Eventos</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero ingerir eventos de participación (unirse/responder) para que el agregador pueda calcular métricas en tiempo real.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Aceptar lote válido</b><br>Dado que la sesión ses_01A está activa y lista para recibir eventos<br>Cuando se realiza un POST con un lote de eventos bien formados para dicha sesión<br>Entonces el sistema devuelve un Estado 202 y el campo accepted es igual al número total de eventos en el lote</li>
<li><b>Escenario: Llamada no autenticada</b><br>Dado que el llamante no está autenticado<br>Cuando se realiza un POST al endpoint de ingesta<br>Entonces el sistema devuelve un Estado 401 con un problem+json</li>
<li><b>Escenario: Acceso prohibido</b><br>Dado que el llamante no tiene los permisos para enviar eventos a esa sesión (por ejemplo, no es el productor/creador)<br>Cuando se realiza un POST a la sesión<br>Entonces el sistema devuelve un Estado 403 con un problem+json y el título "Forbidden"</li>
<li><b>Escenario: Error de validación</b><br>Dado que el llamante está autorizado<br>Cuando se realiza un POST con un evento de tipo RESPONSE_SUBMITTED que carece del questionId<br>Entonces el sistema devuelve un Estado 422 con un problem+json y un array de errores (errors[]) que apunta a events[i].questionId</li>
<li><b>Escenario: Carga útil demasiado grande</b><br>Dado que el llamante está autorizado<br>Cuando se realiza un POST donde el array de eventos excede el tamaño máximo permitido<br>Entonces el sistema devuelve un Estado 413 con el título "Payload Too Large"</li>
<li><b>Escenario: Límite de tasa excedido</b><br>Dado que el llamante está autorizado<br>Cuando el productor excede la tasa de peticiones por segundo (QPS) configurada<br>Entonces el sistema devuelve un Estado 429 con la cabecera Retry-After para indicar cuándo puede reintentar</li>
<li><b>Escenario: Servicio de agregación no disponible</b><br>Dado que el pipeline de ingesta o el servicio de agregación están caídos<br>Cuando se realiza un POST a la sesión<br>Entonces el sistema devuelve un Estado 503 con el título "Service Unavailable"</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS08</td>
<td>Desarrollador</td>
<td>4</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">API de Transmisión en Tiempo Real</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero transmitir instantáneas en vivo a la interfaz de usuario del profesor para que las métricas se actualicen sin sondeo.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: El profesor autorizado se suscribe</b><br>Dado que el llamante tiene ROLE_TEACHER y está asignado a la sesión<br>Cuando GET /sessions/ses_01A/stream<br>Entonces Estado 200 y se reciben eventos SSE "snapshot" y "heartbeat"</li>
<li><b>Escenario: Transmisión no autenticada</b><br>Dado que el llamante no está autenticado<br>Cuando intenta conectarse al endpoint de transmisión<br>Entonces el sistema devuelve un Estado 401 con un problem+json y no se inicia la transmisión</li>
<li><b>Escenario: Acceso prohibido</b><br>Dado que el llamante no tiene los permisos requeridos (por ejemplo, ROLE_PROFESSOR)<br>Cuando intenta conectarse al endpoint de transmisión<br>Entonces el sistema devuelve un Estado 403 con un problem+json y no se inicia la transmisión</li>
<li><b>Escenario: Sesión no encontrada</b><br>Dado que la sesión de quiz especificada no existe o ya ha terminado<br>Cuando el llamante intenta conectarse a esa sesión para la transmisión<br>Entonces el sistema devuelve un Estado 404 con un problem+json y no se inicia la transmisión</li>
<li><b>Escenario: Tiempo de espera por inactividad</b><br>Dado que no hay actualizaciones durante N segundos<br>Cuando el servidor envía un latido periódico<br>Entonces el cliente permanece conectado y no muestra datos obsoletos</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS09</td>
<td>Desarrollador</td>
<td>5</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">API de Resumen de Cuestionario</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero un endpoint para recuperar métricas a nivel de cuestionario para que la UI pueda renderizar el panel de resumen.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Administrador autorizado recupera el resumen</b><br>Dado que el llamante tiene ROLE_ADMIN<br>Cuando GET /analytics/quizzes/{quizId}/summary con filtros válidos<br>Entonces Estado 200 con metrics.avgScore, participationRate, averageResponseTimeMs</li>
<li><b>Escenario: No autenticado</b><br>Cuando GET sin Autorización<br>Entonces Estado 401 problem+json</li>
<li><b>Escenario: Prohibido</b><br>Dado que el llamante carece de ROLE_ADMIN<br>Cuando GET<br>Entonces Estado 403 problem+json título "Forbidden"</li>
<li><b>Escenario: Cuestionario no encontrado</b><br>Dado que el llamante carece del ROLE_ADMIN<br>Cuando GET para un quizId desconocido<br>Entonces Estado 404 problem+json</li>
<li><b>Escenario: Rango de fechas inválido</b><br>Dado que el quizId es válido<br>Cuando se realiza un GET a /analytics/quizzes/{quizId}/summary con un rango de fechas donde from es posterior a to<br>Entonces el sistema devuelve un Estado 422 con un problem+json y un array de errores en los campos from y to</li>
<li><b>Escenario: Error del servidor</b><br>Dado que el sistema encuentra un error inesperado<br>Cuando se realiza un GET a /analytics/quizzes/{quizId}/summary<br>Entonces el sistema devuelve un Estado 500 con un problem+json y un errorId para su seguimiento</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS10</td>
<td>Desarrollador</td>
<td>5</td>
<td>Analytics</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Estadísticas por Pregunta API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero un endpoint para recuperar estadísticas por pregunta para que la UI pueda mostrar las preguntas más difíciles y los detalles.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Obtener estadísticas por pregunta</b><br>Dado que el usuario tiene el ROLE_ADMIN<br>Cuando GET /analytics/quizzes/{quizId}/questions?sort=correctnessRate,asc<br>Entonces Estado 200 con content[] y paginación</li>
<li><b>Escenario: Campo de ordenación no admitido</b><br>Dado que el usuario tiene el ROLE_ADMIN<br>Cuando sort=hackerField,asc<br>Entonces Estado 400 con detalle "Unsupported sort field: hackerField"</li>
<li><b>Escenario: No autenticado / Prohibido / No encontrado / Error del servidor</b><br>Dado que se realiza una petición a un endpoint de estadísticas<br>Entonces devuelve 401 / 403 / 404 / 500 con problem+json</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS11</td>
<td>Desarrollador</td>
<td>6</td>
<td>User Profile</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir crear perfil a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero crear un perfil de usuario a través de la API para que los nuevos usuarios puedan inicializar su perfil.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Crear perfil exitosamente</b><br>Dado que el endpoint /api/v1/profile está disponible<br>Cuando se envía un POST con fullName, username, avatarUrl (https), institution válidos<br>Entonces se devuelve el Estado 201<br>Y el ProfileResource incluye id y la URL almacenada (no base64)</li>
<li><b>Escenario: El nombre de usuario ya existe</b><br>Cuando se envía un POST con el nombre de usuario &quot;juan_perez&quot; que ya está tomado<br>Entonces se devuelve el Estado 409<br>Y el mensaje "El nombre de usuario ya está tomado" se incluye</li>
<li><b>Escenario: Rechazar avatar no HTTP/HTTPS</b><br>Cuando se envía un POST con avatarUrl &quot;ftp://example.com/a.jpg&quot;<br>Entonces se devuelve el Estado 400<br>Y el mensaje "La URL del avatar debe usar HTTP o HTTPS" se incluye</li>
<li><b>Escenario: Rechazar caracteres no admitidos</b><br>Cuando se envía un POST con fullName que contiene caracteres no admitidos (ej. 汉字 o emojis)<br>Entonces se devuelve el Estado 400<br>Y los detalles apuntan a los caracteres inválidos</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS12</td>
<td>Desarrollador</td>
<td>6</td>
<td>User Profile</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir actualizar perfil a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero actualizar un perfil de usuario existente a través de la API para que los usuarios puedan editar su nombre, nombre de usuario y avatar.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Actualizar nombre de usuario a un nuevo valor disponible</b><br>Dado que el endpoint /api/v1/profile está disponible<br>Y el solicitante es el propietario del perfil<br>Cuando se envía un PUT con el nombre de usuario &quot;mateo_dev&quot;<br>Entonces se devuelve el Estado 200<br>Y el perfil muestra el nombre de usuario &quot;mateo_dev&quot;</li>
<li><b>Escenario: Actualizar avatar con URL https válida</b><br>Cuando se envía un PUT con avatarUrl &quot;https://cdn.example.com/u/avatar.png&quot;<br>Entonces se devuelve el Estado 200<br>Y el avatarUrl se persiste como enlace (no en línea/base64)</li>
<li><b>Escenario: Rechazar avatar en línea/base64</b><br>Cuando se envía un PUT con avatarUrl &quot;data:image/png;base64,....&quot;<br>Entonces se devuelve el Estado 400<br>Y el mensaje "Las imágenes en línea/base64 no están permitidas" se incluye</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS13</td>
<td>Desarrollador</td>
<td>7</td>
<td>User Profile</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir progreso a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero devolver el progreso actual (nivel, puntos, insignias, racha) para que el panel del estudiante pueda ser renderizado.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Obtener mi progreso exitosamente</b><br>Dado que el endpoint /api/v1/progress/me está disponible<br>Y el solicitante tiene ROLE_STUDENT<br>Cuando se envía una solicitud GET<br>Entonces se devuelve el Estado 200 con nivel, puntos, insignias, racha</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS14</td>
<td>Desarrollador</td>
<td>7</td>
<td>User Profile</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir clasificación (leaderboard) a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero un endpoint de clasificación unificado para que el cliente pueda obtener rangos por alcance y período.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Obtener clasificación global (Histórico)</b><br>Dado que el endpoint /api/v1/leaderboards está disponible<br>Cuando se envía un GET con scope=global&amp;period=all&amp;page=1&amp;size=25<br>Entonces se devuelve el Estado 200 con una lista paginada<br>Y las entradas están ordenadas por puntos desc, los empates se resuelven por nivel desc, luego por firstAchievedAt asc<br>Y myEntry se incluye incluso si no está en la página actual</li>
<li><b>Escenario: Obtener clasificación de clase (Semanal) con membresía</b><br>Dado que el solicitante está inscrito en la clase &quot;cls_CS101_2025_2&quot;<br>Cuando se envía un GET con scope=class&amp;classId=cls_CS101_2025_2&amp;period=weekly<br>Entonces se devuelve el Estado 200<br>Y solo los miembros de la clase están clasificados</li>
<li><b>Escenario: Rechazar clasificación de clase sin membresía</b><br>Dado que el solicitante no está inscrito en &quot;cls_MATH101&quot;<br>Cuando se envía un GET con scope=class&amp;classId=cls_MATH101&amp;period=weekly<br>Entonces se devuelve el Estado 403<br>Y un mensaje "No eres miembro de esta clase" se incluye</li>
<li><b>Escenario: Obtener clasificación de Desafío</b><br>Cuando se envía un GET con scope=challenge&amp;challengeId=ch_ABC123<br>Entonces se devuelve el Estado 200<br>Y solo aparecen los estudiantes con una entrega válida para ese desafío</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS15</td>
<td>Desarrollador</td>
<td>8</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir lista de actividades del estudiante a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero obtener las actividades de un estudiante a través de la API para que el Front-end pueda mostrarlas en "Mis Actividades".
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Listar mis actividades con filtros</b><br>Dado que el endpoint /api/v1/class-activities/me está disponible<br>Cuando se envía un GET con status=ASSIGNED,IN_PROGRESS&amp;type=CHALLENGE,QUIZ&amp;sort=dueAt,asc<br>Entonces se devuelve el Estado 200 con una lista paginada<br>Y todos los ítems pertenecen al estudiante solicitante</li>
<li><b>Escenario: Límite de tasa</b><br>Dado que el endpoint /api/v1/class-activities/me está disponible<br>Y el solicitante excede el límite de tasa<br>Cuando se envía un GET<br>Entonces se devuelve el Estado 429<br>Y la respuesta incluye el encabezado "Retry-After"</li>
<li><b>Escenario: Tiempo de espera del servicio principal</b><br>Dado que el endpoint depende de ActivityService<br>Y ActivityService se agota el tiempo de espera<br>Cuando se envía un GET<br>Entonces se devuelve el Estado 504<br>Y la respuesta contiene el título "Gateway Timeout"</li>
<li><b>Escenario: Error inesperado del servidor</b><br>Dado que el endpoint /api/v1/class-activities/me está disponible<br>Cuando ocurre una excepción no manejada<br>Entonces se devuelve el Estado 500<br>Y la respuesta contiene un id de error para diagnósticos</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS16</td>
<td>Desarrollador</td>
<td>8</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">Añadir detalles de la actividad a través de API</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero recuperar los detalles de la actividad para que los estudiantes puedan ver instrucciones, enlaces y opciones de entrega.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Obtener detalles de la actividad</b><br>Dado que el solicitante pertenece a la clase &quot;cls_CS101_2025_2&quot;<br>Cuando se envía un GET a /api/v1/class-activities/act_01H<br>Entonces se devuelve el Estado 200 con los detalles de la actividad</li>
<li><b>Escenario: Entrega deshabilitada porque la fecha de vencimiento ha pasado</b><br>Dado que la actividad &quot;act_01H&quot; existe<br>Y su dueAt está en el pasado<br>Cuando se envía un GET a /api/v1/class-activities/act_01H<br>Entonces se devuelve el Estado 200 con los detalles de la actividad<br>Y la carga útil tiene submission.locked=true<br>Y submission.lockReason=&quot;DUE_DATE_PASSED&quot;</li>
<li><b>Escenario: Límite de tasa</b><br>Dado que el solicitante excede el límite de tasa<br>Cuando se envía un GET a /api/v1/class-activities/act_01H<br>Entonces se devuelve el Estado 429<br>Y la respuesta incluye el encabezado "Retry-After"</li>
<li><b>Escenario: Error inesperado del servidor</b><br>Dado que el endpoint /api/v1/class-activities/{activityId} está disponible<br>Cuando ocurre una excepción no manejada<br>Entonces se devuelve el Estado 500<br>Y la respuesta contiene un id de error para diagnósticos</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS17</td>
<td>Desarrollador</td>
<td>9</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">API de Progreso (a nivel de clase)</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero un endpoint para recuperar el progreso de la clase (métricas simples + filas de estudiantes) para que la UI pueda renderizar la vista de progreso.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: El profesor autorizado obtiene el progreso de la clase</b><br>Dado que el llamante tiene ROLE_TEACHER y está asignado a {classId}<br>Cuando GET /teacher/{classId}/progress<br>Entonces Estado 200 con completionRate, avgScore y students[]</li>
<li><b>Escenario: No autenticado</b><br>Cuando GET /teacher/{classId}/progress sin Autorización<br>Entonces Estado 401 con application/problem+json</li>
<li><b>Escenario: Prohibido (no asignado)</b><br>Dado que el llamante tiene ROLE_TEACHER pero no está asignado a {classId}<br>Cuando GET /teacher/{classId}/progress<br>Entonces Estado 403 con problem+json título "Forbidden"</li>
<li><b>Escenario: Clase no encontrada</b><br>Cuando GET /teacher/cls_UNKNOWN/progress<br>Entonces Estado 404 con problem+json título "Class Not Found"</li>
<li><b>Escenario: Error del servidor</b><br>Cuando ocurre un error inesperado<br>Entonces Estado 500 con problem+json y un errorId</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS18</td>
<td>Desarrollador</td>
<td>9</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">API de Creación de Actividad</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como Desarrollador, quiero un endpoint para recuperar la lista de actividades de un solo estudiante en una clase para que la UI pueda mostrar sus detalles.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: El profesor autorizado obtiene el progreso del estudiante</b><br>Dado que el llamante tiene ROLE_TEACHER y está asignado a {classId}<br>Cuando GET /teacher/{classId}/students/{studentId}/progress<br>Entonces Estado 200 con activities[]</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS19</td>
<td>Desarrollador</td>
<td>10</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">API de Creación de entrega con retroalimentación inmediata</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como desarrollador, quiero un endpoint que cree una entrega y (si es autocalificable) devuelva retroalimentación inmediata para que los estudiantes puedan leer los resultados de inmediato.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Envío autocalificable exitoso</b><br>Dado que la actividad está PUBLISHED y es auto-gradable<br>Y el estudiante está matriculado y tiene attemptsRemaining &gt; 0<br>Cuando hago POST a /class-activities/{activityId}/submissions con respuestas válidas<br>Entonces recibo Status 201 con score y items[] con retroalimentación</li>
<li><b>Escenario: Actividad no encontrada o no publicada</b><br>Cuando hago POST para una actividad desconocida o no PUBLISHED<br>Entonces recibo Status 404 con title = &quot;Activity Not Found&quot;</li>
<li><b>Escenario: Intentos agotados</b><br>Dado que attemptsRemaining = 0<br>Cuando hago POST<br>Entonces recibo Status 409 con title = &quot;Attempts Exhausted&quot;</li>
</ul>
</td>
</tr>
</table>

<table>
<tr>
<th>Story ID</th>
<th>User</th>
<th>Priority</th>
<th>Epic</th>
</tr>
<tr>
<td>TS20</td>
<td>Desarrollador</td>
<td>10</td>
<td>Class Activities</td>
</tr>
<tr>
<th colspan="4">Title</th>
</tr>
<tr>
<td colspan="4">API de Política de visibilidad de retroalimentación (simple)</td>
</tr>
<tr>
<th colspan="4">Description</th>
</tr>
<tr>
<td colspan="4">
Como desarrollador, quiero exponer la política de visibilidad de retroalimentación/soluciones de una actividad para que los estudiantes sepan qué podrán leer después de enviar su entrega.
</td>
</tr>
<tr>
<th colspan="4">Acceptance Criteria</th>
</tr>
<tr>
<td colspan="4">
<ul>
<li><b>Escenario: Obtener política</b><br>Cuando hago GET a /class-activities/{activityId}/feedback-policy<br>Entonces recibo Status 200 con valores booleanos para showScore, showItemCorrectness y showSolutions</li>
</ul>
</td>
</tr>
</table>

## 3.3. Impact Mapping.

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

![Impact-Map-1](../chapter3/assets/Impact-Mapping/Impact-Map-1.png)

</div>

## 3.4. Product Backlog.

| # Orden | Epic / Story ID | Título                                          | Descripción                                                  | Story Points |
| ------- | --------------- | ----------------------------------------------- | ------------------------------------------------------------ | ------------ |
| 1       | US01            | Student Registration                            | As a Student I want to access the Sign-up page So that I can register with my email and password | 3            |
| 2       | US02            | Add Student through RESTful API                 | As a Developer I want to add a Student through the API So that it can be available to build features for my applications. | 3            |
| 3       | US03            | Student Authentication                          | As a Student I want to access the Sign-in page So that I can authenticate with my email and password | 3            |
| 4       | US04            | Add Authenticate Student through RESTful API    | As a Developer I want to authenticate a Student through the API So that the Student can access the protected functionalities of the application | 3            |
| 5       | US53            | Token Issuance (Login)                          | As a Developer I want the gateway to authenticate credentials and issue tokens So that downstream services receive a verified identity. | 2            |
| 6       | US05            | Posting                                         | As a Teacher I want to create a post with text and images So that I can interact with my students and communicate events | 2            |
| 7       | US06            | Posting through RESTful API                     | As a Developer I want to create a community post via the API So that professors can publish validated content safely | 3            |
| 8       | US07            | Liking                                          | As a Student I want to like or unlike a community post So that I can express my opinion and support others | 2            |
| 9       | US08            | Commenting                                      | As a Student I want to write a comment under a post So that I can participate in the discussion | 1            |
| 10      | US09            | Liking trough API                               | As a Developer I want to register likes/unlikes through the API So that user interactions are consistent and secure | 1            |
| 11      | US10            | Commenting trough API                           | As a Developer I want to add, validate, and store comments through the API So that students can safely interact under posts | 2            |
| 12      | US44            | Live Session Dashboard                          | As a Teacher I want to see studentCount, responseDistribution, and averageResponseTime So that I can monitor the class in real time. | 5            |
| 13      | US45            | Response Distribution Chart                     | As a Teacher I want a chart of responses (A/B/C/D or numbers) So that I can identify misconceptions quickly. | 5            |
| 14      | US46            | Average Time Panel                              | As a Teacher I want to see the average response time for the current question So that I can pace the session. | 2            |
| 15      | US47            | Events Ingestion API                            | As a Developer I want to ingest participation events (join/response) So that the aggregator can compute real-time metrics. | 2            |
| 16      | US48            | Real-time Stream API                            | As a Developer I want to stream live snapshots to the teacher UI So that metrics update without polling. | 2            |
| 17      | US49            | View Quiz Summary Report                        | As an Admin I want to view average score, participation rate, and average response time for a quiz So that I can gauge overall performance. | 3            |
| 18      | US50            | Hardest Questions                               | As an Admin I want a list of the hardest questions (lowest correctness rate) So that I can spot misconceptions. | 2            |
| 19      | US51            | Quiz Summary API                                | As a Developer I want an endpoint to retrieve quiz-level metrics So that the UI can render the summary panel. | 2            |
| 20      | US52            | Per-Question Stats API                          | I want an endpoint to retrieve per-question statistics So that the UI can show hardest questions and drilldowns. | 2            |
| 21      | US11            | Add Profile settings trough Front-end           | As a Student I want to edit my profile (name, username, avatar) So that I can personalize my experience in the platform | 1            |
| 22      | US12            | Add Create Profile trough API                   | As a Developer I want to create a user profile via API So that new users can initialize their profile | 2            |
| 23      | US13            | Add Update Profile trough API                   | As a Developer I want to update an existing user profile via API So that users can edit their name, username and avatar | 1            |
| 24      | US14            | Add pogress for student via Front-end           | As a Student I want to view my level, points, badges, and streak So that I stay motivated and track my growth | 2            |
| 25      | US15            | Add Leaderboard trough Front-end                | As a Student I want to view leaderboards by scope (global, class, challenge) So that I can compare my progress and stay engaged | 3            |
| 26      | US16            | Add progress trough API                         | As a Developer I want to return current progress (level, points, badges, streak) So that the student dashboard can be rendered | 1            |
| 27      | US17            | Add Leaderboard trough APi                      | As a Developer I want a unified leaderboard endpoint So that the client can fetch ranks by scope and period | 2            |
| 28      | US18            | Add Unified list of activities trough Front-end | As a Student I want to see all my assigned activities in one place So that I can plan and prioritize my study time | 3            |
| 29      | US19            | Add List Student Activities trough API          | As a Developer, I want to fetch a student’s activities via API so that the Front-end can display them in “My Activities.” | 3            |
| 30      | US20            | Add Activity Details trough API                 | As a Developer, I want to retrieve activity details so that students can view instructions, links, and submission options. | 3            |
| 31      | US21            | Add View Class Progress via Front-end           | As a Teacher I want a class progress overview with key metrics (completion, average score, late submissions) So that I can quickly spot strengths and weaknesses at a glance. | 2            |
| 32      | US22            | View Student Progress (Detail)                  | As a Teacher I want to open a student’s progress detail So that I can review their completed/pending activities. | 2            |
| 33      | US23            | Create Activity (Task)                          | As a Teacher I want to create a new activity for my class So that students can see instructions and a due date. | 3            |
| 34      | US24            | Add Edit / Close Activity via Front-end         | As a Teacher I want to edit an existing activity and optionally close submissions So that I can correct details and stop late work. | 1            |
| 35      | US25            | Progress API (class-level)                      | As a Developer I want an endpoint to retrieve class progress (simple metrics + student rows) So that the UI can render the progress view. | 3            |
| 36      | US26            | Create Activity API                             | As a Developer I want an endpoint to retrieve a single student’s activity list in a class So that the UI can show their detail. | 3            |
| 37      | US27            | Update/Publish/Close Activity API               | As a Developer I want to create a class activity So that teachers can add tasks. | 5            |
| 38      | US28            | Submit and See Instant Feedback (auto-gradable) | As a Student I want to see my score and basic feedback right after I submit an auto-gradable activity So that I know what I did right or wrong immediately. | 5            |
| 39      | US29            | View Detailed Feedback                          | As a Student I want to open detailed feedback of my submission So that I can learn from explanations and rubric notes. | 3            |
| 40      | US30            | View Detailed Feedback                          | As a Student I want to retry an activity and get updated feedback So that I can improve within the allowed attempts. | 3            |
| 41      | US31            | Create Submission with Immediate Feedback       | As a Developer I want an endpoint that creates a submission and (if auto-gradable) returns immediate feedback So that the students can read results right away. | 5            |
| 42      | US32            | Feedback Visibility Policy (simple)             | As a Developer I want to expose the feedback/solution visibility policy for an activity So that the studens knows what to read after submission. | 5            |
