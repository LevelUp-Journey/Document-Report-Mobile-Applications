# 2.4. Requirements specification
## 2.4.1. User Stories.

<div align="justify"


La elaboración de las user stories en esta sección partió de la definición previa de las épicas, que permitieron agrupar los requisitos en bloques funcionales coherentes y alineados con los objetivos del proyecto. Las épicas funcionaron como marcos conceptuales amplios que organizaron las funcionalidades por áreas clave de valor, asegurando que cada conjunto de historias respondiera a una necesidad estratégica concreta identificada en el impact mapping.

A partir de cada épica se redactaron user stories que describen, desde la perspectiva del usuario final, las funcionalidades esperadas y el propósito que persiguen. Estas historias se detallaron con criterios de aceptación claros para definir el comportamiento esperado del sistema y facilitar su validación. Este enfoque permitió transformar objetivos generales en funcionalidades pequeñas, independientes y priorizables, manteniendo la trazabilidad con su épica de origen y con los objetivos de aprendizaje y retención definidos para el proyecto.

De forma complementaria, se definieron technical stories asociadas a las mismas épicas. Estas especifican los componentes técnicos, integraciones, APIs y servicios necesarios para que las user stories puedan implementarse de forma segura y escalable. Así, las user stories representan el valor funcional que recibe el usuario, mientras que las technical stories aseguran la base técnica que lo hace posible, permitiendo planificar y desarrollar el sistema de forma iterativa y coherente.

</div> <br />

<br />

<table>
  <tr>
    <th>Story ID</th>
    <th>User</th>
    <th>Priority</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>US-001</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Crear quiz</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo registrar un nuevo quiz con nombre, categoría, descripción e imagen de portada, asociándolo a mi usuario para comenzar el proceso de evaluación.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: crear quiz válido</strong></li>
        <li>Dado que soy un <strong>Teacher autenticado</strong></li>
        <li>Y tengo un <strong>nombre</strong> y una <strong>categoría válidos</strong></li>
        <li>Cuando solicito crear el quiz</li>
        <li>Entonces el sistema registra el quiz asociado a mi usuario</li>
        <li>Y emite el evento <strong>QuizCreatedEvent</strong></li>
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
    <td>US-002</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Actualizar quiz</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo actualizar los datos básicos de un quiz existente —como nombre, descripción, categoría o imagen— sin alterar su autoría ni su identificador, para mantener la coherencia del contenido.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: actualizar datos de quiz</strong></li>
        <li>Dado que soy el <strong>creador del quiz</strong></li>
        <li>Cuando edito su <strong>nombre</strong>, <strong>descripción</strong>, <strong>categoría</strong> o <strong>imagen</strong></li>
        <li>Entonces el sistema guarda los cambios</li>
        <li>Y conserva la <strong>autoría</strong> e <strong>identificador</strong> del quiz</li>
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
    <td>US-003</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Eliminar quiz</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo eliminar un quiz existente para retirarlo del uso académico y mantener actualizado el banco de evaluaciones.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: eliminar un quiz existente</strong></li>
        <li>Dado que soy el <strong>creador</strong> del quiz</li>
        <li>Cuando solicito <strong>eliminar</strong> el quiz</li>
        <li>Entonces el sistema elimina el quiz del registro</li>
        <li>Y no puede ser consultado posteriormente</li>
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
    <td>US-004</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Publicar quiz</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo publicar un quiz previamente creado y con preguntas válidas para hacerlo visible y accesible a los estudiantes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: publicar quiz con preguntas</strong></li>
        <li>Dado que soy el <strong>creador</strong> del quiz</li>
        <li>Y el quiz tiene al menos <strong>una pregunta válida</strong></li>
        <li>Cuando solicito <strong>publicar</strong> el quiz</li>
        <li>Entonces su estado cambia a <strong>PUBLIC</strong></li>
        <li>Y se emite el evento <strong>QuizPublishedEvent</strong></li>
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
    <td>US-005</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar preguntas y respuestas del quiz para asegurar calidad y validez pedagógica.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Agregar pregunta</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo agregar una pregunta a un quiz existente, definiendo su tipo, puntuación, tiempo de respuesta y posibles alternativas, para mantener la calidad y variedad en las evaluaciones.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: agregar pregunta válida</strong></li>
        <li>Dado que el quiz es de mi autoría</li>
        <li>Y defino el tipo <strong>MULTIPLE_CHOICE</strong> o <strong>TRUE_FALSE</strong></li>
        <li>Y cumplo las reglas de cantidad de respuestas y definición de la(s) respuesta(s) correcta(s)</li>
        <li>Cuando agrego la pregunta al quiz</li>
        <li>Entonces el sistema registra la nueva pregunta correctamente asociada al quiz</li>
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
    <td>US-006</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero gestionar preguntas y respuestas del quiz para asegurar calidad y validez pedagógica.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Actualizar pregunta</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo actualizar una pregunta existente dentro de un quiz, modificando su contenido, tipo, puntuación, tiempo o respuestas, asegurando que se cumplan las reglas de consistencia pedagógica y técnica.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: actualizar pregunta</strong></li>
        <li>Dado que el quiz es de mi autoría</li>
        <li>Y la pregunta existe</li>
        <li>Cuando modifico el <strong>contenido</strong>, <strong>tipo</strong>, <strong>puntos</strong>, <strong>tiempo</strong> o <strong>respuestas</strong> cumpliendo las reglas de cada tipo</li>
        <li>Entonces el sistema guarda la actualización correctamente</li>
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
    <td>US-007</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero gestionar preguntas y respuestas del quiz para asegurar calidad y validez pedagógica.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Eliminar pregunta</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo eliminar una pregunta de un quiz existente para mantener la relevancia y coherencia del contenido evaluativo.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: eliminar pregunta de quiz</strong></li>
        <li>Dado que el quiz es de mi autoría</li>
        <li>Y la pregunta existe</li>
        <li>Cuando solicito eliminarla</li>
        <li>Entonces el sistema elimina la pregunta del quiz</li>
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
    <td>US-008</td>
    <td>Usuario</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Consultar quiz</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, deseo consultar un quiz por su identificador, con la opción de incluir sus preguntas y respuestas, para visualizar su contenido según los permisos de acceso establecidos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: consultar quiz PRIVATE vs PUBLIC</strong></li>
        <li>Dado un quiz con estado <strong>PRIVATE</strong></li>
        <li>Cuando no soy su creador</li>
        <li>Entonces el sistema <strong>deniega la consulta</strong></li>
        <br>
        <li>Y dado un quiz con estado <strong>PUBLIC</strong></li>
        <li>Cuando lo consulto</li>
        <li>Entonces el sistema <strong>devuelve sus datos</strong>, incluyendo sus preguntas y respuestas si están disponibles</li>
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
    <td>US-008</td>
    <td>Usuario</td>
    <td>Baja</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Consultar quiz</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, deseo consultar un quiz por su identificador, con la opción de incluir sus preguntas y respuestas, para visualizar su contenido según los permisos de acceso establecidos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: consultar quiz PRIVATE vs PUBLIC</strong></li>
        <li>Dado un quiz con estado <strong>PRIVATE</strong></li>
        <li>Cuando no soy su creador</li>
        <li>Entonces el sistema <strong>deniega la consulta</strong></li>
        <br>
        <li>Y dado un quiz con estado <strong>PUBLIC</strong></li>
        <li>Cuando lo consulto</li>
        <li>Entonces el sistema <strong>devuelve sus datos</strong>, incluyendo sus preguntas y respuestas si están disponibles</li>
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
    <td>US-009</td>
    <td>Student</td>
    <td>Baja</td>
    <td>Como Student, quiero descubrir quizzes públicos para participar o reutilizar contenido.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar quizzes públicos</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Student, deseo listar quizzes públicos con paginación y filtros por categoría y término de búsqueda para encontrar contenido relevante y participar.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: listado con filtros</strong></li>
        <li>Dado que existen quizzes con visibilidad <strong>PUBLIC</strong></li>
        <li>Cuando aplico <strong>categoría</strong> y <strong>término de búsqueda</strong> y solicito una página (número y tamaño)</li>
        <li>Entonces recibo la <strong>página filtrada</strong> con <strong>datos básicos</strong> del quiz (id, nombre, categoría, autor, estado, imagen opcional)</li>
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
    <td>US-010</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero ver mis quizzes para gestionarlos fácilmente.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar mis quizzes</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo listar mis quizzes con paginación y filtros para administrarlos de manera eficiente desde el panel.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: listado de autor</strong></li>
        <li>Dado que soy <strong>Teacher</strong></li>
        <li>Cuando consulto mis quizzes aplicando <strong>filtros</strong> y <strong>paginación</strong></li>
        <li>Entonces obtengo <strong>solo los quizzes creados por mí</strong>, en el formato paginado solicitado</li>
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
    <td>US-011</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero dirigir sesiones en vivo para evaluar en tiempo real y obtener participación de los estudiantes.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Crear sesión en vivo</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo crear una sesión en vivo a partir de un quiz con estado <strong>PUBLIC</strong> para evaluar en tiempo real y generar un código único que los estudiantes puedan usar para unirse.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: crear sesión</strong></li>
        <li>Dado que el quiz tiene estado <strong>PUBLIC</strong></li>
        <li>Cuando solicito crear la sesión en vivo</li>
        <li>Entonces el sistema genera un <strong>código único de sesión</strong></li>
        <li>Y emite el evento <strong>SessionCreatedEvent</strong></li>
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
    <td>US-012</td>
    <td>Student</td>
    <td>Media</td>
    <td>Como Student, quiero unirme a una sesión en vivo para responder el quiz.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Unirse a sesión</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Student, deseo unirme a una sesión en vivo que acepte participantes, registrando mi rol y conexión dentro del quiz en tiempo real, con soporte para reconexión en caso de desconexión temporal.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: unirse y reingresar</strong></li>
        <li>Dado que la sesión está <strong>aceptando jugadores</strong></li>
        <li>Cuando me uno por primera vez</li>
        <li>Entonces el sistema registra mi participación</li>
        <li>Y emite el evento <strong>ParticipantJoinedEvent</strong></li>
        <br>
        <li>Y cuando me reconecto a la misma sesión</li>
        <li>Entonces el sistema emite <strong>ParticipantRejoinedEvent</strong></li>
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
    <td>US-013</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero iniciar la sesión cuando haya participantes para comenzar la evaluación.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Iniciar sesión</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo iniciar una sesión en vivo cuando existan participantes registrados, para dar inicio a la evaluación y cambiar el estado de la sesión a <strong>IN_PROGRESS</strong>.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: iniciar con participantes</strong></li>
        <li>Dado que soy <strong>Teacher</strong></li>
        <li>Y hay al menos <strong>un participante</strong> en la sesión</li>
        <li>Cuando inicio la sesión</li>
        <li>Entonces el estado de la sesión cambia a <strong>IN_PROGRESS</strong></li>
        <li>Y se emite el evento <strong>SessionStartedEvent</strong></li>
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
    <td>US-014</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero iniciar la pregunta actual para que los participantes respondan.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Iniciar pregunta</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo iniciar la pregunta activa de la sesión en vivo, para habilitar que los participantes comiencen a responder dentro del tiempo asignado.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: iniciar pregunta válida</strong></li>
        <li>Dado que la sesión está en estado <strong>IN_PROGRESS</strong></li>
        <li>Cuando inicio la pregunta activa</li>
        <li>Entonces se marca el <strong>inicio de la pregunta</strong></li>
        <li>Y se emite el evento <strong>QuestionStartedEvent</strong></li>
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
    <td>US-015</td>
    <td>Student</td>
    <td>Media</td>
    <td>Como Student, quiero enviar mi respuesta y obtener puntaje según corrección y tiempo.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Enviar respuesta</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Student, deseo enviar mi respuesta a la pregunta activa durante la sesión en vivo para registrar mi resultado, considerando la corrección y el tiempo de respuesta.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: enviar única respuesta</strong></li>
        <li>Dado que no he respondido la pregunta actual</li>
        <li>Cuando envío mi respuesta</li>
        <li>Entonces el sistema registra la <strong>corrección</strong>, los <strong>puntos obtenidos</strong> y el <strong>tiempo de envío</strong></li>
        <li>Y emite el evento <strong>AnswerSubmittedEvent</strong></li>
        <br>
        <li>Y si intento responder de nuevo</li>
        <li>Entonces el sistema <strong>rechaza</strong> el nuevo intento</li>
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
    <td>US-016</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero cerrar la pregunta y avanzar a la siguiente para continuar la sesión.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Avanzar pregunta</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo finalizar la pregunta actual y avanzar a la siguiente dentro de la sesión en vivo, para continuar con la evaluación de manera ordenada y progresiva.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: avanzar en progreso</strong></li>
        <li>Dado que la sesión está en estado <strong>IN_PROGRESS</strong></li>
        <li>Cuando avanzo de pregunta</li>
        <li>Entonces el sistema incrementa el <strong>índice de pregunta actual</strong></li>
        <li>Y se emite el evento <strong>QuestionAdvancedEvent</strong></li>
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
    <td>US-017</td>
    <td>Teacher</td>
    <td>Baja</td>
    <td>Como Teacher, quiero finalizar la sesión y obtener el ranking final para retroalimentación.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Finalizar sesión y ranking</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo cerrar la sesión en vivo y generar un ranking de los participantes con base en su rendimiento y tiempo de respuesta, para brindar retroalimentación y cerrar la actividad de forma ordenada.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: cerrar sesión</strong></li>
        <li>Dado que soy un Teacher autenticado</li>
        <li>Cuando finalizo la sesión en curso</li>
        <li>Entonces el sistema calcula el <strong>ranking final</strong> de los participantes según puntuación y tiempo</li>
        <li>Y emite el evento <strong>SessionFinishedEvent</strong> con la clasificación completa</li>
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
    <td>US-018</td>
    <td>Student</td>
    <td>Media</td>
    <td>Como Student, quiero consultar el estado de una sesión en vivo para conocer su progreso.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Consultar sesión</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Student, deseo consultar en tiempo real el estado de una sesión activa para conocer su progreso, la pregunta actual y cuántos participantes están conectados, permitiéndome seguir el ritmo del quiz.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: ver estado</strong></li>
        <li>Dado un <strong>código de sesión válido</strong></li>
        <li>Cuando consulto la sesión</li>
        <li>Entonces el sistema responde con el <strong>estado actual</strong> de la sesión, el <strong>índice de pregunta activa</strong> y los <strong>participantes conectados</strong></li>
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
    <td>US-019</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero retirar a un participante que incumpla normas para mantener el orden.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Expulsar participante</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo expulsar a un participante de una sesión en vivo que incumpla las normas o cause interrupciones, para mantener el orden y la continuidad del quiz.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: expulsión</strong></li>
        <li>Dado que soy un <strong>Teacher autenticado</strong></li>
        <li>Y el participante está <strong>activo</strong> en la sesión</li>
        <li>Cuando ejecuto la acción de expulsión</li>
        <li>Entonces el sistema lo marca como <strong>fuera de la sesión</strong></li>
        <li>Y emite el evento <strong>ParticipantKickedEvent</strong></li>
        <br>
        <li>Y si el participante sale voluntariamente</li>
        <li>Entonces el sistema emite <strong>ParticipantLeftEvent</strong></li>
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
    <td>US-020</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero generar un reporte de una sesión finalizada para analizar resultados.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Generar reporte</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo generar un reporte consolidado de la sesión finalizada para analizar los resultados y la participación de los estudiantes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: generar o reutilizar</strong></li>
        <li>Dado que la sesión está <strong>finalizada</strong></li>
        <li>Cuando solicito generar el reporte</li>
        <li>Entonces, si no existe, se <strong>crea</strong> y se devuelve su <strong>ID</strong></li>
        <li>Y si ya existe, se <strong>devuelve el reporte existente</strong></li>
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
    <td>US-021</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero consultar un reporte para revisar resultados por participante y pregunta.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Consultar reporte</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo ver el contenido de un reporte generado para revisar el desempeño por participante y las estadísticas por pregunta.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: ver reporte</strong></li>
        <li>Dado un <strong>ID de reporte</strong> válido</li>
        <li>Cuando consulto el reporte</li>
        <li>Entonces recibo el <strong>resumen</strong> general, los <strong>resultados por participante</strong> y las <strong>estadísticas por pregunta</strong></li>
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
    <td>US-022</td>
    <td>Teacher</td>
    <td>Alta</td>
    <td>Como Teacher, quiero exportar un reporte a Excel o CSV para compartir y analizar.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Exportar reporte</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Teacher, deseo exportar el reporte consolidado de una sesión en formato <strong>Excel (.xlsx)</strong> o <strong>CSV</strong> para compartirlo con otros docentes o analizarlo externamente.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: exportar formatos</strong></li>
        <li>Dado un <strong>ID de reporte válido</strong></li>
        <li>Cuando elijo el formato de exportación <strong>EXCEL</strong> o <strong>CSV</strong></li>
        <li>Entonces el sistema genera el archivo con el contenido del <strong>SessionReport</strong></li>
        <li>Y permite su <strong>descarga directa</strong> o acceso mediante enlace temporal seguro</li>
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
    <td>TUS-001</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /quizzes</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero exponer un endpoint REST para crear quizzes con validaciones y emisión de eventos de dominio, garantizando la integridad de datos y la trazabilidad de las operaciones dentro del sistema.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: creación exitosa</strong></li>
        <li>Dado un <strong>payload válido</strong> con nombre, categoría, descripción e imagen</li>
        <li>Y un usuario con <strong>rol Teacher</strong></li>
        <li>Cuando envío una solicitud <strong>POST /quizzes</strong></li>
        <li>Entonces el sistema responde <strong>201 Created</strong> con el <strong>ID del quiz</strong></li>
        <li>Y emite el evento <strong>QuizCreatedEvent</strong></li>
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
    <td>TUS-002</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint PUT /quizzes/{id}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint para actualizar quizzes existentes, aplicando validaciones de autoría y consistencia de datos, garantizando que solo el creador pueda modificar su contenido.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: actualización autorizada</strong></li>
        <li>Dado un <strong>quiz existente</strong> y su <strong>creador autenticado</strong></li>
        <li>Cuando envío una solicitud <strong>PUT</strong> con datos válidos</li>
        <li>Entonces el sistema responde <strong>200 OK</strong> y actualiza el quiz</li>
        <li>Y conserva la <strong>autoría original</strong> del recurso</li>
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
    <td>TUS-003</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint DELETE /quizzes/{id}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita eliminar quizzes de forma controlada, asegurando que solo el creador o un administrador autorizado pueda ejecutar la acción y manteniendo la integridad del sistema.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: eliminación exitosa</strong></li>
        <li>Dado un <strong>quiz existente</strong> y un <strong>usuario autenticado con rol de creador o administrador</strong></li>
        <li>Cuando envío una solicitud <strong>DELETE</strong> al recurso</li>
        <li>Entonces el sistema responde <strong>204 No Content</strong></li>
        <li>Y elimina el quiz de forma <strong>permanente</strong> del repositorio</li>
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
    <td>TUS-003</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint DELETE /quizzes/{id}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita eliminar quizzes de forma controlada, asegurando que solo el creador o un administrador autorizado pueda ejecutar la acción y manteniendo la integridad del sistema.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: eliminación exitosa</strong></li>
        <li>Dado un <strong>quiz existente</strong> y un <strong>usuario autenticado con rol de creador o administrador</strong></li>
        <li>Cuando envío una solicitud <strong>DELETE</strong> al recurso</li>
        <li>Entonces el sistema responde <strong>204 No Content</strong></li>
        <li>Y elimina el quiz de forma <strong>permanente</strong> del repositorio</li>
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
    <td>TUS-005</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar preguntas y respuestas del quiz para asegurar calidad y validez pedagógica.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /quizzes/{id}/questions</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero agregar preguntas a un quiz con validaciones de tipo y respuestas para asegurar la calidad pedagógica y la consistencia del contenido evaluativo.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: agregar pregunta válida</strong></li>
        <li>Dado un <strong>quiz</strong> existente y un <strong>payload</strong> con tipo, puntos, tiempo y respuestas</li>
        <li>Cuando envío <strong>POST</strong> a <code>/quizzes/{id}/questions</code></li>
        <li>Entonces el sistema responde <strong>201 Created</strong> y registra la pregunta asociada al quiz</li>
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
    <td>TUS-006</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar preguntas y respuestas del quiz para asegurar calidad y validez pedagógica.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint PUT /questions/{id}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero actualizar preguntas aplicando reglas de validación (tipo, respuestas, puntaje, tiempo) para mantener la consistencia pedagógica y técnica del quiz.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: actualización válida</strong></li>
        <li>Dado una <strong>pregunta existente</strong> y el <strong>autor del quiz</strong> autenticado</li>
        <li>Cuando envío <strong>PUT</strong> con cambios válidos (contenido, tipo, puntos, tiempo, respuestas cumpliendo reglas)</li>
        <li>Entonces el sistema responde <strong>200 OK</strong> y actualiza la pregunta</li>
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
    <td>TUS-007</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar preguntas y respuestas del quiz para asegurar calidad y validez pedagógica.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint DELETE /questions/{id}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita eliminar preguntas de un quiz con los permisos adecuados, asegurando la correcta gestión del contenido y evitando inconsistencias en el cuestionario.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: eliminación autorizada</strong></li>
        <li>Dado una <strong>pregunta existente</strong> y el <strong>autor del quiz autenticado</strong></li>
        <li>Cuando envío una solicitud <strong>DELETE /questions/{id}</strong></li>
        <li>Entonces el sistema responde <strong>204 No Content</strong></li>
        <li>Y elimina la pregunta de forma permanente del sistema</li>
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
    <td>TUS-008</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint GET /quizzes/{id}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint para consultar quizzes por su identificador, aplicando control de visibilidad según el estado (PUBLIC o PRIVATE) y el rol del usuario solicitante, garantizando seguridad y confidencialidad del contenido.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: consulta pública</strong></li>
        <li>Dado un <strong>quiz con estado PUBLIC</strong></li>
        <li>Cuando envío una solicitud <strong>GET /quizzes/{id}</strong></li>
        <li>Entonces el sistema responde <strong>200 OK</strong> con los datos del quiz</li>
        <br>
        <li><strong>Escenario: acceso restringido</strong></li>
        <li>Dado un <strong>quiz PRIVATE</strong> y un usuario que no es el creador</li>
        <li>Entonces el sistema responde <strong>403 Forbidden</strong></li>
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
    <td>TUS-009</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Student, quiero descubrir quizzes públicos para participar o reutilizar contenido.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint GET /quizzes/public</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que liste los quizzes con visibilidad pública, incorporando paginación, filtros por categoría y búsqueda textual, para facilitar el descubrimiento y reutilización de contenido educativo.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: listado filtrado</strong></li>
        <li>Dado filtros por <strong>categoría</strong> y <strong>término de búsqueda</strong></li>
        <li>Cuando envío una solicitud <strong>GET /quizzes/public</strong> con parámetros de consulta</li>
        <li>Entonces el sistema responde <strong>200 OK</strong> con una <strong>página paginada</strong> de quizzes públicos que cumplen los criterios</li>
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
    <td>TUS-010</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero ver mis quizzes para gestionarlos fácilmente.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint GET /users/{userId}/quizzes</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita listar los quizzes creados por un usuario específico, aplicando autenticación y filtros opcionales, para facilitar la gestión de sus propios contenidos de evaluación.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: listado propio</strong></li>
        <li>Dado un <strong>usuario autenticado</strong></li>
        <li>Cuando envío una solicitud <strong>GET /users/{userId}/quizzes</strong></li>
        <li>Entonces el sistema responde <strong>200 OK</strong> con los quizzes del usuario, presentados en una <strong>lista paginada</strong></li>
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
    <td>TUS-011</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero dirigir sesiones en vivo para evaluar en tiempo real y obtener participación de los estudiantes.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint para crear sesiones en vivo basadas en quizzes públicos, generando códigos únicos para identificar cada sesión y permitir la participación interactiva de los estudiantes en tiempo real.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: creación exitosa</strong></li>
        <li>Dado un <strong>quiz con estado PUBLIC</strong></li>
        <li>Cuando envío una solicitud <strong>POST /sessions</strong></li>
        <li>Entonces el sistema responde <strong>201 Created</strong> con un <strong>código único de sesión</strong></li>
        <li>Y emite el evento <strong>SessionCreatedEvent</strong></li>
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
    <td>TUS-012</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Student, quiero unirme a una sesión en vivo para responder el quiz.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{code}/join</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita a los estudiantes unirse a sesiones activas mediante un código único, registrando su participación y emitiendo eventos para trazabilidad y sincronización en tiempo real.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: unión exitosa</strong></li>
        <li>Dado una <strong>sesión</strong> que está aceptando participantes</li>
        <li>Cuando envío una solicitud <strong>POST /sessions/{code}/join</strong></li>
        <li>Entonces el sistema responde <strong>200 OK</strong> y registra al participante en la sesión</li>
        <li>Y emite el evento <strong>ParticipantJoinedEvent</strong></li>
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
    <td>TUS-013</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero iniciar la sesión cuando haya participantes para comenzar la evaluación.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{id}/start</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita iniciar sesiones en vivo solo cuando existan participantes y el host esté autenticado, garantizando control de flujo y consistencia del estado de la sesión.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: inicio válido</strong></li>
        <li>Dado una <strong>sesión</strong> con participantes registrados y el <strong>host autenticado</strong></li>
        <li>Cuando envío una solicitud <strong>POST /sessions/{id}/start</strong></li>
        <li>Entonces el sistema cambia el estado de la sesión a <strong>IN_PROGRESS</strong></li>
        <li>Y emite el evento <strong>SessionStartedEvent</strong></li>
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
    <td>TUS-014</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero iniciar la pregunta actual para que los participantes respondan.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{id}/questions/start</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita iniciar la pregunta activa dentro de una sesión en vivo, asegurando la correcta transición de estados y habilitando el flujo de respuestas de los participantes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: inicio de pregunta</strong></li>
        <li>Dado una <strong>sesión</strong> en estado <strong>IN_PROGRESS</strong></li>
        <li>Cuando envío una solicitud <strong>POST /sessions/{id}/questions/start</strong></li>
        <li>Entonces el sistema marca el <strong>inicio de la pregunta actual</strong></li>
        <li>Y emite el evento <strong>QuestionStartedEvent</strong></li>
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
    <td>TUS-015</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Student, quiero enviar mi respuesta y obtener puntaje según corrección y tiempo.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{id}/answers</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que registre las respuestas enviadas por los participantes durante la sesión, aplicando validaciones de integridad para evitar duplicados y garantizar el correcto cálculo de puntaje y tiempo de respuesta.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: respuesta única</strong></li>
        <li>Dado una <strong>pregunta activa</strong> y aún <strong>no respondida</strong> por el participante</li>
        <li>Cuando envío una solicitud <strong>POST /sessions/{id}/answers</strong></li>
        <li>Entonces el sistema <strong>registra la respuesta</strong> correctamente</li>
        <li>Y emite el evento <strong>AnswerSubmittedEvent</strong></li>
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
    <td>TUS-016</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero cerrar la pregunta y avanzar a la siguiente para continuar la sesión.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{id}/questions/advance</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita al host avanzar a la siguiente pregunta de la sesión en vivo, controlando la secuencia del flujo y manteniendo sincronizados a los participantes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: avance válido</strong></li>
        <li>Dado una <strong>sesión</strong> en estado <strong>IN_PROGRESS</strong> y un <strong>host autenticado</strong></li>
        <li>Cuando envío una solicitud <strong>POST /sessions/{id}/questions/advance</strong></li>
        <li>Entonces el sistema <strong>incrementa el índice</strong> de la pregunta actual</li>
        <li>Y emite el evento <strong>QuestionAdvancedEvent</strong></li>
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
    <td>TUS-017</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero finalizar la sesión y obtener el ranking final para retroalimentación.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{id}/finish</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero finalizar sesiones en vivo calculando el ranking de participantes para cerrar la actividad y disponer de resultados consolidados.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: finalización</strong></li>
        <li>Dado una sesión en estado <strong>IN_PROGRESS</strong> y el <strong>host</strong> autenticado</li>
        <li>Cuando envío <strong>POST /sessions/{id}/finish</strong></li>
        <li>Entonces el sistema <strong>calcula el ranking</strong> final de los participantes</li>
        <li>Y emite el evento <strong>SessionFinishedEvent</strong></li>
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
    <td>TUS-018</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Student, quiero consultar el estado de una sesión en vivo para conocer su progreso.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint GET /sessions/{code}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint para consultar el estado de sesiones en vivo por código,
      de modo que los participantes puedan ver el progreso: estado, índice de pregunta actual y participantes activos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: consulta estado</strong></li>
        <li>Dado un <strong>código</strong> de sesión válido</li>
        <li>Cuando envío una solicitud <strong>GET /sessions/{code}</strong></li>
        <li>Entonces el sistema responde <strong>200 OK</strong> con <strong>estado</strong> de la sesión, <strong>índice</strong> de la pregunta actual y <strong>participantes activos</strong></li>
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
    <td>TUS-019</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero retirar a un participante que incumpla normas para mantener el orden.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{id}/participants/{participantId}/kick</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita a un host expulsar participantes activos de una sesión en vivo,
      de manera controlada y registrando eventos de expulsión para auditoría y trazabilidad.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: expulsión</strong></li>
        <li>Dado un <strong>host autenticado</strong> y un <strong>participante activo</strong> en la sesión</li>
        <li>Cuando envío una solicitud <strong>POST /sessions/{id}/participants/{participantId}/kick</strong></li>
        <li>Entonces el sistema <strong>marca al participante como fuera</strong></li>
        <li>Y emite el evento <strong>ParticipantKickedEvent</strong></li>
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
    <td>TUS-020</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero generar un reporte de una sesión finalizada para analizar resultados.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /sessions/{id}/reports</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que genere reportes consolidados de sesiones finalizadas,
      de modo que los docentes puedan acceder a resultados resumidos y análisis posteriores al cierre.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: generación</strong></li>
        <li>Dado una <strong>sesión finalizada</strong></li>
        <li>Cuando envío <strong>POST /sessions/{id}/reports</strong></li>
        <li>Entonces el sistema <strong>crea un nuevo reporte</strong> si no existe</li>
        <li>Y si ya existe, <strong>devuelve el reporte existente</strong> sin duplicar</li>
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
    <td>TUS-021</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero consultar un reporte para revisar resultados por participante y pregunta.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint GET /reports/{id}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint para consultar reportes detallados de sesiones finalizadas,
      permitiendo obtener información resumida y estadísticas por participante y pregunta para el análisis docente.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: consulta de reporte</strong></li>
        <li>Dado un <strong>id de reporte válido</strong></li>
        <li>Cuando envío una solicitud <strong>GET /reports/{id}</strong></li>
        <li>Entonces el sistema responde <strong>200 OK</strong> con <strong>resumen general</strong> y <strong>estadísticas</strong> por participante y por pregunta</li>
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
    <td>TUS-022</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero exportar un reporte a Excel o CSV para compartir y analizar.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint GET /reports/{id}/export</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar un endpoint que permita exportar los reportes de sesión 
      en formatos Excel (.xlsx) o CSV, asegurando compatibilidad con herramientas externas 
      y facilitando el análisis y la difusión de resultados.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: exportación</strong></li>
        <li>Dado un <strong>id de reporte válido</strong> y un <strong>formato solicitado (Excel o CSV)</strong></li>
        <li>Cuando envío una solicitud <strong>GET /reports/{id}/export</strong></li>
        <li>Entonces el sistema responde <strong>200 OK</strong> y devuelve el <strong>archivo generado</strong> en el formato correspondiente</li>
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
    <td>TUS-024</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero dirigir sesiones en vivo para evaluar en tiempo real y obtener participación de los estudiantes.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar WebSocket con baja latencia</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero implementar comunicación en tiempo real mediante WebSockets con protocolo STOMP, 
      asegurando baja latencia en la transmisión de mensajes durante sesiones en vivo, 
      de modo que las interacciones entre docentes y estudiantes sean fluidas y sin retrasos perceptibles.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: latencia WebSocket</strong></li>
        <li>Dado una <strong>sesión con 500 participantes activos</strong></li>
        <li>Cuando se envían mensajes con tamaño ≤ 2 KB mediante <strong>STOMP</strong></li>
        <li>Entonces el sistema mantiene una latencia <strong>p95 ≤ 200 ms</strong> en la entrega de mensajes</li>
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
    <td>TUS-025</td>
    <td>Desarrollador</td>
    <td>Alta</td>
    <td>Como Teacher, quiero gestionar quizzes (crear, actualizar, publicar, eliminar) para evaluar a los estudiantes con contenido curado.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar alta disponibilidad</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como Desarrollador, quiero garantizar alta disponibilidad en los servicios del microservicio de quizzes,
      asegurando que la API permanezca operativa el 99.9% del tiempo mensual mediante monitoreo, balanceo de carga
      y despliegues resilientes, de modo que los usuarios puedan acceder sin interrupciones significativas.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: disponibilidad del servicio</strong></li>
        <li>Dado un <strong>mes operativo completo</strong></li>
        <li>Cuando se monitorea el tiempo activo del servicio</li>
        <li>Entonces la API mantiene un <strong>uptime ≥ 99.9%</strong> mensual medido por herramientas de observabilidad</li>
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
    <td>COMM-US-001</td>
    <td>Docente</td>
    <td>Alta</td>
    <td>Como docente, quiero crear y gestionar publicaciones.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Crear publicación con multimedia</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como docente, quiero crear una publicación con título, contenido y archivos multimedia para compartir información con los estudiantes y fomentar la comunicación académica.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: creación de publicación con archivos</strong></li>
        <li>Dado que soy un docente autenticado (<strong>ROLE_TEACHER</strong>)</li>
        <li>Cuando creo una publicación con título, contenido en texto enriquecido, tipo y categoría</li>
        <li>Y adjunto hasta <strong>5 archivos multimedia</strong> (máx <strong>10MB</strong> cada uno)</li>
        <li>Entonces la publicación se crea exitosamente</li>
        <li>Y queda visible inmediatamente para todos los estudiantes</li>
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
    <td>COMM-US-002</td>
    <td>Docente</td>
    <td>Baja</td>
    <td>Como docente, quiero crear y gestionar publicaciones.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Editar y eliminar publicaciones</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como docente, quiero editar o eliminar mis publicaciones para corregir errores o remover contenido obsoleto, manteniendo actualizada la información compartida con los estudiantes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: edición de publicación</strong></li>
        <li>Dado una publicación que creé anteriormente</li>
        <li>Cuando modifico su título, contenido, tipo o categoría</li>
        <li>Entonces los cambios se guardan con un indicador de <strong>"editado"</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: eliminación de publicación</strong></li>
        <li>Dado una publicación existente creada por mí</li>
        <li>Cuando elimino la publicación</li>
        <li>Entonces se elimina junto con todos sus <strong>comentarios</strong> y <strong>likes asociados</strong></li>
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
    <td>COMM-US-003</td>
    <td>Docente</td>
    <td>Alta</td>
    <td>Como docente, quiero crear y gestionar publicaciones.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Fijar publicaciones importantes</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como docente, quiero fijar publicaciones importantes al inicio del feed para destacar anuncios urgentes y asegurar su visibilidad ante los estudiantes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: fijar anuncio urgente</strong></li>
        <li>Dado que tengo una publicación importante creada</li>
        <li>Cuando la marco como <strong>fijada</strong></li>
        <li>Entonces aparece al inicio del feed</li>
        <li>Y solo pueden existir hasta <strong>3 publicaciones fijadas</strong> simultáneamente</li>
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
    <td>COMM-US-004</td>
    <td>Estudiante</td>
    <td>Alta</td>
    <td>Como estudiante, quiero visualizar y participar en la comunidad.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Visualizar feed de publicaciones</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como estudiante, quiero ver el feed de publicaciones ordenado cronológicamente para mantenerme informado sobre las novedades académicas y actividades compartidas por docentes o compañeros.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: navegación del feed</strong></li>
        <li>Dado que soy un estudiante autenticado (<strong>ROLE_STUDENT</strong>)</li>
        <li>Cuando accedo al feed de la comunidad</li>
        <li>Entonces veo las publicaciones ordenadas cronológicamente</li>
        <li>Y las publicaciones <strong>fijadas</strong> aparecen al inicio</li>
        <li>Y visualizo <strong>título</strong>, <strong>extracto</strong>, <strong>autor</strong>, <strong>fecha</strong> y <strong>contadores de comentarios/likes</strong></li>
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
    <td>COMM-US-005</td>
    <td>Estudiante</td>
    <td>Media</td>
    <td>Como estudiante, quiero visualizar y participar en la comunidad.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Comentar en publicaciones</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como estudiante, quiero comentar en publicaciones para participar en discusiones académicas, compartir opiniones y realizar preguntas a docentes o compañeros.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: crear y editar comentario</strong></li>
        <li>Dado que veo una publicación de interés</li>
        <li>Cuando escribo un comentario de hasta <strong>500 caracteres</strong></li>
        <li>Entonces el comentario se publica con mi <strong>nombre</strong>, <strong>foto</strong> y <strong>fecha</strong></li>
        <li>Y puedo <strong>editarlo</strong> dentro de las primeras <strong>24 horas</strong></li>
        <li>Y puedo <strong>eliminarlo</strong> en cualquier momento</li>
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
    <td>COMM-US-006</td>
    <td>Estudiante</td>
    <td>Alta</td>
    <td>Como estudiante, quiero visualizar y participar en la comunidad.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Reaccionar con likes</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como estudiante, quiero dar <strong>like</strong> a publicaciones y comentarios para expresar aprecio por contenido valioso y fomentar la participación positiva dentro de la comunidad.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: dar y quitar like</strong></li>
        <li>Dado que veo una publicación o comentario</li>
        <li>Cuando doy <strong>like</strong></li>
        <li>Entonces el <strong>contador de likes</strong> aumenta</li>
        <li>Y mi like queda registrado</li>
        <li>Y cuando lo quito</li>
        <li>Entonces el contador disminuye</li>
        <li>Y puedo ver la <strong>lista de usuarios</strong> que dieron like</li>
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
    <td>COMM-US-007</td>
    <td>Usuario</td>
    <td>Alta</td>
    <td>Como usuario, quiero notificaciones y búsqueda.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Recibir notificaciones en tiempo real</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero recibir notificaciones en tiempo real para mantenerme informado sobre nuevas publicaciones, comentarios y actividades relevantes dentro de la comunidad, según mis preferencias configuradas.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: notificación de nueva publicación</strong></li>
        <li>Dado que soy un estudiante activo</li>
        <li>Cuando un docente crea una nueva publicación</li>
        <li>Entonces recibo una <strong>notificación en tiempo real</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: notificación al docente</strong></li>
        <li>Dado que soy un docente</li>
        <li>Cuando un estudiante comenta mi publicación</li>
        <li>Entonces recibo una notificación inmediata del nuevo comentario</li>
      </ul>
      <ul>
        <li><strong>Escenario: configuración de notificaciones</strong></li>
        <li>Dado mis preferencias de usuario</li>
        <li>Cuando modifico qué tipos de notificaciones deseo recibir</li>
        <li>Entonces el sistema actualiza mi configuración y aplica los cambios en tiempo real</li>
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
    <td>COMM-US-007</td>
    <td>Usuario</td>
    <td>Media</td>
    <td>Como usuario, quiero notificaciones y búsqueda.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Recibir notificaciones en tiempo real</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero recibir notificaciones en tiempo real para mantenerme informado sobre nuevas publicaciones, comentarios y actividades relevantes dentro de la comunidad, según mis preferencias configuradas.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: notificación de nueva publicación</strong></li>
        <li>Dado que soy un estudiante activo</li>
        <li>Cuando un docente crea una nueva publicación</li>
        <li>Entonces recibo una <strong>notificación en tiempo real</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: notificación al docente</strong></li>
        <li>Dado que soy un docente</li>
        <li>Cuando un estudiante comenta mi publicación</li>
        <li>Entonces recibo una notificación inmediata del nuevo comentario</li>
      </ul>
      <ul>
        <li><strong>Escenario: configuración de notificaciones</strong></li>
        <li>Dado mis preferencias de usuario</li>
        <li>Cuando modifico qué tipos de notificaciones deseo recibir</li>
        <li>Entonces el sistema actualiza mi configuración y aplica los cambios en tiempo real</li>
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
    <td>IAM-US-001</td>
    <td>Usuario</td>
    <td>Baja</td>
    <td>Como usuario nuevo, quiero registrarme con email y contraseña para acceder a la plataforma</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Registro con validaciones y rol por defecto</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario nuevo, quiero registrarme con email y contraseña para acceder a la plataforma con rol estudiante por defecto.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: registro exitoso</li>
        <li>Dado que proporciono un email válido (RFC 5322) y una contraseña que cumple políticas</li>
        <li>Cuando envío la solicitud de registro sin roles</li>
        <li>Entonces el sistema crea el usuario con email normalizado en minúsculas y rol <strong>ROLE_STUDENT</strong> asignado</li>
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
    <td>IAM-US-002</td>
    <td>Usuario</td>
    <td>Media</td>
    <td>Como usuario autenticado, quiero iniciar sesión y gestionar tokens</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Inicio de sesión (email/contraseña)</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero iniciar sesión para obtener tokens y acceder a recursos protegidos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: autenticación válida</li>
        <li>Dado que existe un usuario con email y contraseña correctos</li>
        <li>Cuando solicito iniciar sesión</li>
        <li>Entonces el sistema autentica con comparación segura y devuelve los datos del usuario junto con un par de tokens (acceso y actualización)</li>
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
    <td>IAM-US-003</td>
    <td>Usuario</td>
    <td>Media</td>
    <td>Como usuario autenticado, quiero iniciar sesión y gestionar tokens</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Rechazo por credenciales inválidas</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero recibir mensajes claros si mis credenciales son inválidas para corregir el acceso.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: autenticación inválida</li>
        <li>Dado un email o contraseña incorrectos</li>
        <li>Cuando intento iniciar sesión</li>
        <li>Entonces el sistema rechaza la solicitud indicando credenciales inválidas</li>
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
    <td>IAM-US-004</td>
    <td>Usuario autenticado</td>
    <td>Baja</td>
    <td>Como usuario autenticado, quiero iniciar sesión y gestionar tokens</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Renovación de token (refresh)</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero renovar mi token con el refresh para mantener la sesión sin volver a autenticarme.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: refresh token válido</li>
        <li>Dado que poseo un token de actualización válido y no expirado</li>
        <li>Cuando solicito renovar la sesión</li>
        <li>Entonces el sistema genera y retorna nuevos tokens (acceso y actualización) reemplazando los anteriores</li>
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
    <td>IAM-US-005</td>
    <td>Usuario autenticado</td>
    <td>Media</td>
    <td>Como usuario autenticado, quiero iniciar sesión y gestionar tokens</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Validación de token de acceso</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero validar mi token para confirmar que mi sesión sigue activa.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: token válido</li>
        <li>Dado un token de acceso vigente emitido por el sistema</li>
        <li>Cuando solicito validarlo</li>
        <li>Entonces el sistema confirma su validez y devuelve el email asociado</li>
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
    <td>IAM-US-006</td>
    <td>Usuario nuevo</td>
    <td>Baja</td>
    <td>Como usuario nuevo, quiero registrarme con email y contraseña para acceder a la plataforma</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Autenticación con proveedores (Google/GitHub)</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero autenticarme con Google o GitHub para ingresar rápidamente.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: primer login con OAuth2</li>
        <li>Dado que me autentico por primera vez con Google o GitHub</li>
        <li>Cuando el proveedor retorna mis datos válidos</li>
        <li>Entonces el sistema registra automáticamente la cuenta, asigna <strong>ROLE_STUDENT</strong> y emite un token de acceso</li>
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
    <td>IAM-US-007</td>
    <td>Usuario de GitHub sin email</td>
    <td>Baja</td>
    <td>Como usuario nuevo, quiero registrarme con email y contraseña para acceder a la plataforma</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Caso GitHub sin email</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario de GitHub sin email, quiero un identificador alternativo para completar el login.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: identificador alternativo</li>
        <li>Dado que GitHub no devuelve email</li>
        <li>Cuando completo la autenticación</li>
        <li>Entonces el sistema genera un identificador <strong>&lt;login&gt;@github.oauth</strong> y emite un token de acceso</li>
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
    <td>IAM-US-008</td>
    <td>Administrador</td>
    <td>Media</td>
    <td>Como administrador o docente, quiero gestionar usuarios y roles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar usuarios (ADMIN)</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como administrador, quiero listar usuarios para gestionarlos y auditarlos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: listado de usuarios</li>
        <li>Dado que soy <strong>ROLE_ADMIN</strong> autenticado</li>
        <li>Cuando consulto la lista de usuarios</li>
        <li>Entonces recibo <strong>id</strong>, <strong>email</strong> y <strong>roles</strong> de todos los usuarios</li>
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
    <td>IAM-US-009</td>
    <td>Administrador o docente</td>
    <td>Baja</td>
    <td>Como administrador o docente, quiero gestionar usuarios y roles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Obtener usuario por ID o email</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como administrador o docente, quiero obtener usuarios por ID o email para consultar su información.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: consulta de usuario</li>
        <li>Dado que poseo un token válido</li>
        <li>Cuando consulto un usuario por <strong>UUID</strong> o por <strong>email</strong></li>
        <li>Entonces obtengo su información con roles si existe; de lo contrario, el sistema responde <em>no encontrado</em></li>
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
    <td>IAM-US-010</td>
    <td>Administrador o docente</td>
    <td>Media</td>
    <td>Como administrador o docente, quiero gestionar usuarios y roles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar roles y consultar rol</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como administrador o docente, quiero listar y consultar roles para validar permisos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: catálogo de roles</li>
        <li>Dado que poseo permisos (<strong>ROLE_TEACHER</strong> o <strong>ROLE_ADMIN</strong>)</li>
        <li>Cuando listo o consulto un rol por nombre</li>
        <li>Entonces obtengo <strong>ROLE_STUDENT</strong>, <strong>ROLE_TEACHER</strong> o <strong>ROLE_ADMIN</strong> según corresponda</li>
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
    <td>IAM-US-011</td>
    <td>Administrador o docente</td>
    <td>Baja</td>
    <td>Como administrador o docente, quiero gestionar usuarios y roles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Seed de roles base</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como administrador o docente, quiero crear roles base para preparar el sistema.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: inicialización/verificación de roles</li>
        <li>Dado que el sistema arranca o ejecuto la operación de <em>seed</em></li>
        <li>Cuando verifico los roles predefinidos</li>
        <li>Entonces se crean los que falten sin duplicar los existentes</li>
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
    <td>IAM-US-012</td>
    <td>Usuario</td>
    <td>Alta</td>
    <td>Como usuario, quiero evaluar la fortaleza de mi contraseña</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Puntaje de fortaleza 0–5</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero evaluar la fortaleza de mi contraseña para mejorar la seguridad.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: cálculo de puntaje</li>
        <li>Dado una contraseña propuesta</li>
        <li>Cuando solicito evaluar su seguridad</li>
        <li>Entonces recibo un puntaje de <strong>0–5</strong> y se considera fuerte con puntaje <strong>≥ 4</strong></li>
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
    <td>IAM-US-013</td>
    <td>Administrador o docente</td>
    <td>Media</td>
    <td>Como administrador o docente, quiero gestionar usuarios y roles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Asignación de múltiples roles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como administrador o docente, quiero asignar múltiples roles a un usuario para controlar sus permisos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li>Escenario: asignación y deduplicación</li>
        <li>Dado un usuario existente y un conjunto de roles válidos</li>
        <li>Cuando asigno roles (individual o en lote)</li>
        <li>Entonces el sistema valida su existencia, evita duplicados y garantiza al menos <strong>ROLE_STUDENT</strong> si no hay roles definidos</li>
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
    <td>TIAM-001</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como usuario nuevo, quiero registrarme con email y contraseña para acceder a la plataforma con seguridad (rol estudiante por defecto).</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar POST /auth/signup</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero implementar el endpoint de registro para crear usuarios seguros y asignar un rol por defecto que permita el acceso inicial a la plataforma.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: registro exitoso</strong></li>
        <li>Dado el endpoint "/auth/signup" disponible sobre HTTPS</li>
        <li>Y un payload con email válido (RFC 5322) y contraseña que cumple políticas</li>
        <li>Cuando persisto el usuario con contraseña cifrada en BCrypt y sin roles explícitos</li>
        <li>Entonces respondo <strong>201 Created</strong> con el usuario creado y <strong>ROLE_STUDENT</strong> asignado</li>
      </ul>
      <ul>
        <li><strong>Escenario: email duplicado o datos inválidos</strong></li>
        <li>Dado un email ya registrado o payload inválido</li>
        <li>Cuando valido los datos de entrada</li>
        <li>Entonces respondo <strong>409 Conflict</strong> (duplicado) o <strong>400 Bad Request</strong> con mensajes claros</li>
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
    <td>TIAM-002</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como usuario autenticado, quiero iniciar sesión y gestionar tokens (validar y refrescar) para mantener una sesión segura y continua.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar POST /auth/signin</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero implementar el inicio de sesión con verificación segura para emitir tokens JWT y permitir sesiones <em>stateless</em>.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: autenticación válida</strong></li>
        <li>Dado credenciales correctas (email normalizado y contraseña hash BCrypt)</li>
        <li>Cuando verifico y genero <code>accessToken</code> (≤1h) y <code>refreshToken</code> (≤7d)</li>
        <li>Entonces respondo <strong>200 OK</strong> con <code>{ user, accessToken, refreshToken }</code></li>
      </ul>
      <ul>
        <li><strong>Escenario: autenticación inválida y auditoría</strong></li>
        <li>Dado email o contraseña incorrectos</li>
        <li>Cuando rechazo el acceso</li>
        <li>Entonces respondo <strong>401 Unauthorized</strong> y registro intento fallido con <em>timestamp</em> e IP</li>
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
    <td>TIAM-003</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como usuario autenticado, quiero iniciar sesión y gestionar tokens (validar y refrescar) para mantener una sesión segura y continua.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar POST /auth/token/refresh</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero implementar la renovación de tokens para extender sesiones válidas sin reautenticación, mejorando la experiencia de usuario (UX) y la seguridad.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: refresh válido</strong></li>
        <li>Dado un <code>refreshToken</code> vigente emitido por el sistema</li>
        <li>Cuando valido su firma y expiración</li>
        <li>Entonces emito nuevos <code>accessToken</code> y <code>refreshToken</code> y respondo <strong>200 OK</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: refresh inválido o expirado</strong></li>
        <li>Dado un token alterado o vencido</li>
        <li>Entonces respondo <strong>401 Unauthorized</strong> con el motivo del rechazo</li>
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
    <td>TIAM-004</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como usuario autenticado, quiero iniciar sesión y gestionar tokens (validar y refrescar) para mantener una sesión segura y continua.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar POST /auth/token/validate</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer la validación de token de acceso para permitir a los clientes verificar sesiones activas con confianza.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: token válido</strong></li>
        <li>Dado un <code>accessToken</code> con firma HMAC-SHA válida y no expirado</li>
        <li>Cuando valido el token</li>
        <li>Entonces respondo <strong>200 OK</strong> con <code>{ valid: true, email }</code></li>
      </ul>
      <ul>
        <li><strong>Escenario: token inválido</strong></li>
        <li>Dado un token mal firmado o expirado</li>
        <li>Entonces respondo <strong>401 Unauthorized</strong> con <code>{ valid: false, reason }</code></li>
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
    <td>TIAM-005</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar /auth/oauth2/authorize y /auth/oauth2/callback</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero integrar OAuth2 (Google/GitHub) con registro automático para soportar inicio social y simplificar la autenticación del usuario.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: primer login con email</strong></li>
        <li>Dado que el proveedor retorna un email verificado</li>
        <li>Cuando proceso el callback</li>
        <li>Entonces creo el usuario si no existe, asigno <strong>ROLE_STUDENT</strong> y emito <code>accessToken</code></li>
      </ul>
      <ul>
        <li><strong>Escenario: GitHub sin email</strong></li>
        <li>Dado que el proveedor no retorna email pero sí login</li>
        <li>Cuando proceso el callback</li>
        <li>Entonces genero identificador <strong>"@github.oauth"</strong> y emito <code>accessToken</code></li>
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
    <td>TIAM-006</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar GET /users (paginado)</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero listar usuarios con control RBAC para permitir una gestión administrativa segura y eficiente.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: acceso ADMIN</strong></li>
        <li>Dado un <code>accessToken</code> válido con <strong>ROLE_ADMIN</strong></li>
        <li>Cuando consulto <code>/users</code> con paginación</li>
        <li>Entonces respondo <strong>200 OK</strong> con <code>[{ id, email, roles }]</code> en &lt; 200 ms promedio</li>
      </ul>
      <ul>
        <li><strong>Escenario: acceso denegado</strong></li>
        <li>Dado un usuario sin <strong>ROLE_ADMIN</strong></li>
        <li>Entonces respondo <strong>403 Forbidden</strong></li>
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
    <td>TIAM-007</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar GET /users/{userId} y GET /users:by-email</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero obtener un usuario por ID o email con control RBAC para facilitar consultas puntuales y mantener la seguridad de acceso.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: por ID</strong></li>
        <li>Dado <strong>ROLE_ADMIN</strong> o el propio usuario</li>
        <li>Cuando consulto <code>/users/{userId}</code></li>
        <li>Entonces respondo <strong>200 OK</strong> o <strong>404 Not Found</strong> si no existe</li>
      </ul>
      <ul>
        <li><strong>Escenario: por email</strong></li>
        <li>Dado <strong>ROLE_ADMIN</strong> o <strong>ROLE_TEACHER</strong> según políticas</li>
        <li>Cuando consulto <code>/users:by-email?email=...</code></li>
        <li>Entonces respondo <strong>200 OK</strong> o <strong>404 Not Found</strong>; si falta email, <strong>400 Bad Request</strong></li>
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
    <td>TIAM-008</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar GET /roles y GET /roles/{roleName}</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer un catálogo de roles y sus detalles para soportar la interfaz de administración y mantener la gestión de permisos centralizada.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: listado de roles</strong></li>
        <li>Dado un usuario autenticado</li>
        <li>Cuando consulto <code>/roles</code></li>
        <li>Entonces respondo <strong>200 OK</strong> con <code>[ROLE_STUDENT, ROLE_TEACHER, ROLE_ADMIN]</code></li>
      </ul>
      <ul>
        <li><strong>Escenario: detalle de rol</strong></li>
        <li>Dado <strong>ROLE_TEACHER</strong> o <strong>ROLE_ADMIN</strong></li>
        <li>Cuando consulto <code>/roles/{roleName}</code></li>
        <li>Entonces respondo <strong>200 OK</strong> con el rol o <strong>404 Not Found</strong></li>
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
    <td>TIAM-009</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar POST /roles/seed</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero inicializar o sembrar roles base de manera idempotente para asegurar que el sistema esté listo desde el arranque sin duplicar registros.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: seed idempotente</strong></li>
        <li>Dado que algunos roles no existen</li>
        <li>Cuando invoco <code>/roles/seed</code> con permisos (<strong>ROLE_TEACHER</strong> o <strong>ROLE_ADMIN</strong>)</li>
        <li>Entonces creo solo los faltantes y respondo <strong>200 OK</strong></li>
        <li>Y si todos existen, respondo <strong>200 OK</strong> sin duplicar</li>
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
    <td>TIAM-010</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como usuario, quiero evaluar la fortaleza de mi contraseña para mejorar mi seguridad antes de registrarme o cambiarla.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar POST /auth/password/strength</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero evaluar la fortaleza de contraseñas para guiar a los usuarios hacia credenciales seguras y reducir riesgos de seguridad en la autenticación.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: cálculo de puntaje</strong></li>
        <li>Dado una contraseña propuesta</li>
        <li>Cuando aplico la política (longitud + variedad, penalizar patrones/secuencias/repeticiones)</li>
        <li>Entonces respondo <strong>200 OK</strong> con <code>{ score: 0..5, strong: score &gt;= 4 }</code></li>
      </ul>
      <ul>
        <li><strong>Escenario: payload inválido</strong></li>
        <li>Dado ausencia de contraseña</li>
        <li>Entonces respondo <strong>400 Bad Request</strong></li>
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
    <td>TIAM-011</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar POST /users/{userId}/roles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero asignar múltiples roles a un usuario con validaciones y deduplicación para mantener coherencia de permisos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: asignación válida</strong></li>
        <li>Dado <strong>ROLE_ADMIN</strong> o <strong>ROLE_TEACHER</strong> con permisos</li>
        <li>Cuando envío roles existentes evitando duplicados</li>
        <li>Entonces respondo <strong>200 OK</strong> con roles asignados; si el conjunto es vacío, garantizo <strong>ROLE_STUDENT</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: roles inválidos o sin permisos</strong></li>
        <li>Dado roles inexistentes o actor sin privilegios</li>
        <li>Entonces respondo <strong>400 Bad Request</strong> o <strong>403 Forbidden</strong></li>
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
    <td>TIAM-012</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Documentación OpenAPI 3.0</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero documentar automáticamente la API para facilitar la integración y reducir la ambigüedad en los contratos de los endpoints.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: descriptor accesible</strong></li>
        <li>Dado el servicio levantado</li>
        <li>Cuando accedo a Swagger UI o al JSON OpenAPI</li>
        <li>Entonces encuentro todos los endpoints con esquemas, parámetros y respuestas documentadas</li>
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
    <td>TIAM-013</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Configurar HTTPS y CORS</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero aplicar CORS seguro y HTTPS/TLS para proteger datos en tránsito y restringir orígenes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: CORS restringido</strong></li>
        <li>Dado <code>CORS_ALLOWED_ORIGINS</code> configurado</li>
        <li>Cuando llega una solicitud desde un origen no autorizado</li>
        <li>Entonces respondo con bloqueo CORS apropiado</li>
      </ul>
      <ul>
        <li><strong>Escenario: transporte seguro</strong></li>
        <li>Dado el despliegue en ambientes productivos</li>
        <li>Entonces el servicio opera bajo <strong>HTTPS/TLS 1.2+</strong></li>
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
    <td>TIAM-014</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Filtro de autenticación/autorización JWT</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero validar JWT en endpoints protegidos para asegurar acceso por rol y mantener sesiones <em>stateless</em>.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: acceso autorizado</strong></li>
        <li>Dado un <code>accessToken</code> válido con rol adecuado</li>
        <li>Cuando accedo a un endpoint protegido (p.ej., <code>/users</code>)</li>
        <li>Entonces respondo <strong>200 OK</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: acceso denegado</strong></li>
        <li>Dado token ausente, inválido o rol insuficiente</li>
        <li>Entonces respondo <strong>401/403</strong> según corresponda</li>
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
    <td>TIAM-015</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar usuarios y roles para controlar el acceso y permisos del sistema.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Logging y métricas de seguridad</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero registrar logs estructurados y métricas de autenticación para auditoría y monitoreo del sistema.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: intento fallido</strong></li>
        <li>Dado un intento de login fallido</li>
        <li>Cuando lo registro con <em>timestamp</em>, IP y email</li>
        <li>Entonces queda disponible para auditoría y monitoreo</li>
      </ul>
      <ul>
        <li><strong>Escenario: trazabilidad</strong></li>
        <li>Dado operaciones clave (<code>signup</code>, <code>signin</code>, <code>refresh</code>, <code>roles</code>)</li>
        <li>Entonces se registran en logs estructurados con niveles <strong>INFO/WARN/ERROR</strong></li>
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
    <td>PROF-US-001</td>
    <td>Usuario</td>
    <td>Baja</td>
    <td>Como usuario, quiero crear y mantener mi perfil para identificarme en la plataforma y en rankings.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Crear perfil con username y rank inicial</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero crear mi perfil con un <em>username</em> y un <em>rank</em> inicial para participar en la gamificación y aparecer en los rankings de la plataforma.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: creación de perfil</strong></li>
        <li>Dado que estoy autenticado y proporciono nombre, apellido y URL opcional</li>
        <li>Cuando registro mi perfil</li>
        <li>Entonces el sistema crea el perfil y genera un <strong>Username</strong> en formato <code>USER#########</code></li>
        <li>Y asigna el nivel <strong>Bronze</strong> con <strong>1000 puntos</strong></li>
        <li>Y registra el evento en el historial de cambios de puntuación</li>
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
    <td>PROF-US-002</td>
    <td>Usuario</td>
    <td>Baja</td>
    <td>Como usuario, quiero crear y mantener mi perfil para identificarme en la plataforma y en rankings.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Consultar perfil por ID o Username</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero consultar mi perfil por ID o <em>username</em> para ver mi información actual registrada en la plataforma.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: consulta de perfil</strong></li>
        <li>Dado un perfil existente</li>
        <li>Cuando consulto por su ID o por su <em>Username</em></li>
        <li>Entonces obtengo el nombre completo, el <strong>Username</strong> y la URL de perfil si existe</li>
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
    <td>PROF-US-003</td>
    <td>Docente o Administrador</td>
    <td>Baja</td>
    <td>Como usuario, quiero crear y mantener mi perfil para identificarme en la plataforma y en rankings.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar perfiles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como docente o administrador, quiero listar los perfiles de los usuarios para poder administrarlos desde la plataforma.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: listado de perfiles</strong></li>
        <li>Dado que poseo permisos para listar perfiles</li>
        <li>Cuando consulto el listado general</li>
        <li>Entonces recibo <strong>id</strong>, <strong>nombre completo</strong>, <strong>Username</strong> y <strong>URL</strong> de cada perfil</li>
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
    <td>PROF-US-004</td>
    <td>Docente o Administrador</td>
    <td>Media</td>
    <td>Como administrador o docente, quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Seed de niveles competitivos</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como docente o administrador, quiero inicializar los niveles competitivos para habilitar el ranking general de la plataforma.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: inicialización de niveles</strong></li>
        <li>Dado que el sistema no tiene niveles registrados</li>
        <li>Cuando ejecuto la operación de <em>seed</em></li>
        <li>Entonces se crean los 7 niveles (<strong>Bronze → Grandmaster</strong>) con rangos establecidos</li>
        <li>Y si ya existen, la operación no duplica registros</li>
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
    <td>PROF-US-005</td>
    <td>Usuario</td>
    <td>Baja</td>
    <td>Como administrador o docente, quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Consultar niveles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero consultar los niveles competitivos para conocer sus rangos y requisitos, entendiendo mi progreso dentro del sistema de gamificación.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: catálogo de niveles</strong></li>
        <li>Dado niveles competitivos existentes</li>
        <li>Cuando los consulto todos o por nombre</li>
        <li>Entonces recibo su <strong>nombre</strong>, <strong>rango de puntuación</strong> y <strong>orden</strong></li>
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
    <td>PROF-US-006</td>
    <td>Docente o Administrador</td>
    <td>Media</td>
    <td>Como administrador o docente, quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Agregar puntos y evaluar ascenso</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como docente o administrador, quiero agregar puntos y evaluar el ascenso de los usuarios para reflejar sus logros y avances dentro del sistema de gamificación.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: incremento de puntuación</strong></li>
        <li>Dado un perfil con puntaje actual y total acumulado</li>
        <li>Cuando agrego <strong>N puntos</strong> con una razón y referencia opcional</li>
        <li>Entonces el puntaje actual y el total acumulado aumentan en <strong>N</strong></li>
        <li>Y se registra un evento de auditoría con el puntaje anterior/nuevo y el tipo de cambio</li>
        <li>Y si el nuevo puntaje cruza el umbral de nivel, el nivel competitivo se actualiza</li>
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
    <td>PROF-US-007</td>
    <td>Usuario</td>
    <td>Alta</td>
    <td>Como usuario, quiero consultar mi puntuación/nivel e historial para seguir mi progreso y auditar cambios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Consultar nivel y puntuación actual</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero consultar mi puntuación y nivel actuales para conocer mi estado competitivo dentro de la plataforma y evaluar mi progreso.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: estado competitivo</strong></li>
        <li>Dado un perfil existente</li>
        <li>Cuando consulto su estado competitivo</li>
        <li>Entonces obtengo el <strong>ID del perfil</strong>, el <strong>nivel actual</strong> (ID y nombre), la <strong>puntuación vigente</strong> y la <strong>total acumulada</strong></li>
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
    <td>PROF-US-008</td>
    <td>Usuario o Administrador</td>
    <td>Alta</td>
    <td>Como usuario, quiero consultar mi puntuación/nivel e historial para seguir mi progreso y auditar cambios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Ver historial de cambios de puntuación</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario o administrador, quiero ver el historial de puntuación para auditar los cambios y mantener la trazabilidad del progreso dentro del sistema.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: auditoría de puntajes</strong></li>
        <li>Dado un perfil con eventos de puntuación</li>
        <li>Cuando consulto el historial</li>
        <li>Entonces veo la <strong>fecha/hora</strong>, el <strong>tipo de cambio</strong>, los <strong>puntos</strong>, el <strong>puntaje anterior/nuevo</strong>, la <strong>razón</strong> y la <strong>referencia externa</strong> por cada evento</li>
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
    <td>PROF-US-009</td>
    <td>Usuario</td>
    <td>Alta</td>
    <td>Como comunidad, quiero un leaderboard con límites para reconocer a los mejores y fomentar competencia sana.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Leaderboard con límite y orden</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como usuario, quiero ver el leaderboard para conocer a los mejores participantes y motivarme a mejorar mi rendimiento en la plataforma.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: top por puntuación</strong></li>
        <li>Dado perfiles con distintas puntuaciones</li>
        <li>Cuando solicito el leaderboard con límite <strong>L</strong> (por defecto 10, máximo 100)</li>
        <li>Entonces recibo la lista ordenada de mayor a menor puntuación</li>
        <li>Y cada entrada muestra el <strong>ID del perfil</strong>, el <strong>nombre del nivel</strong> y la <strong>puntuación</strong></li>
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
    <td>PROF-US-010</td>
    <td>Docente o Administrador</td>
    <td>Baja</td>
    <td>Como administrador o docente, quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Reasignación automática de nivel</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como docente o administrador, quiero que el sistema reasigne el nivel automáticamente para mantener la coherencia con los rangos establecidos de cada nivel competitivo.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: cruce de umbral</strong></li>
        <li>Dado un perfil con nivel actual y puntaje cercano al umbral superior</li>
        <li>Cuando recibe puntos que superan el rango del nivel actual</li>
        <li>Entonces el sistema reasigna el nivel competitivo correspondiente según los rangos definidos</li>
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
    <td>TPROF-001</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como usuario (ROLE_STUDENT/ROLE_TEACHER), quiero crear y mantener mi perfil para identificarme en la plataforma y en rankings.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Implementar endpoint POST /profiles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>POST /profiles</strong> para crear perfiles con <em>username</em> único y <em>rank</em> inicial, habilitando identidad y gamificación desde el inicio.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: creación válida</strong></li>
        <li>Dado el endpoint "/profiles" y un usuario autenticado (STUDENT/TEACHER/ADMIN)</li>
        <li>Cuando envío <code>firstName</code>, <code>lastName</code> y <code>profileUrl</code> opcional válidos</li>
        <li>Entonces responde <strong>201 Created</strong> con <code>profileId=UUIDv4</code>, <strong>username</strong> en formato <code>USER#########</code>, <strong>rank</strong> inicial <strong>Bronze</strong> y <strong>1000 puntos</strong>, y registra auditoría de puntuación</li>
      </ul>
      <ul>
        <li><strong>Escenario: validación de datos</strong></li>
        <li>Dado payload inválido</li>
        <li>Entonces responde <strong>400 Bad Request</strong> con mensajes claros</li>
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
    <td>TPROF-002</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como usuario (ROLE_STUDENT/ROLE_TEACHER), quiero crear y mantener mi perfil para identificarme en la plataforma y en rankings.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Obtener perfil por ID</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>GET /profiles/{profileId}</strong> con control RBAC para permitir la consulta segura del perfil de un usuario según sus permisos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: propietario o rol con permiso</strong></li>
        <li>Dado <code>profileId</code> válido y un token del propietario o <strong>TEACHER/ADMIN</strong></li>
        <li>Cuando consulto el recurso</li>
        <li>Entonces respondo <strong>200 OK</strong> con nombre completo, <strong>username</strong> y <strong>profileUrl</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: recurso inexistente o sin permisos</strong></li>
        <li>Dado <code>profileId</code> inexistente o rol sin permiso</li>
        <li>Entonces respondo <strong>404 Not Found</strong> o <strong>403 Forbidden</strong></li>
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
    <td>TPROF-003</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como usuario (ROLE_STUDENT/ROLE_TEACHER), quiero crear y mantener mi perfil para identificarme en la plataforma y en rankings.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Obtener perfil por Username</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>GET /profiles/username/{username}</strong> para permitir la búsqueda y consulta de perfiles por nombre de usuario.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: username existente</strong></li>
        <li>Dado un <code>username</code> válido</li>
        <li>Cuando consulto <code>/profiles/username/{username}</code></li>
        <li>Entonces respondo <strong>200 OK</strong> con los datos del perfil</li>
      </ul>
      <ul>
        <li><strong>Escenario: username inexistente</strong></li>
        <li>Dado un <code>username</code> inexistente</li>
        <li>Cuando consulto <code>/profiles/username/{username}</code></li>
        <li>Entonces respondo <strong>404 Not Found</strong></li>
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
    <td>TPROF-004</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar perfiles (paginado)</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>GET /profiles</strong> con paginación y filtro para soportar listados administrativos y optimizar la gestión de usuarios desde el panel de control.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: acceso permitido y paginación</strong></li>
        <li>Dado <strong>ROLE_TEACHER</strong> o <strong>ROLE_ADMIN</strong></li>
        <li>Cuando consulto <code>/profiles?page=N&amp;size=M&amp;search?</code></li>
        <li>Entonces respondo <strong>200 OK</strong> en &lt; 1s con la página solicitada</li>
      </ul>
      <ul>
        <li><strong>Escenario: acceso denegado</strong></li>
        <li>Dado un usuario sin permisos</li>
        <li>Entonces respondo <strong>403 Forbidden</strong></li>
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
    <td>TPROF-005</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Seed de niveles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>POST /ranks/seed</strong> de forma idempotente para garantizar la disponibilidad de los niveles competitivos sin duplicar registros existentes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: creación idempotente</strong></li>
        <li>Dado que faltan niveles competitivos</li>
        <li>Cuando invoco <code>/ranks/seed</code> con <strong>ROLE_TEACHER</strong> o <strong>ROLE_ADMIN</strong></li>
        <li>Entonces crea solo los faltantes y responde <strong>200 OK</strong></li>
        <li>Y si ya existen, no duplica los registros</li>
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
    <td>TPROF-006</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar y detallar niveles</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>GET /ranks</strong> y <strong>GET /ranks/{rankName}</strong> para permitir la consulta del catálogo de niveles competitivos y sus detalles asociados.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: listado</strong></li>
        <li>Dado un usuario autenticado</li>
        <li>Cuando consulto <code>/ranks</code></li>
        <li>Entonces respondo <strong>200 OK</strong> con los 7 niveles y sus rangos</li>
      </ul>
      <ul>
        <li><strong>Escenario: detalle por nombre</strong></li>
        <li>Dado <code>rankName</code> válido</li>
        <li>Cuando consulto <code>/ranks/{rankName}</code></li>
        <li>Entonces respondo <strong>200 OK</strong> o <strong>404 Not Found</strong></li>
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
    <td>TPROF-007</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Agregar puntos y evaluar ascenso</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>POST /profiles/{profileId}/scores:add</strong> transaccional para sumar puntos, auditar el cambio y evaluar ascenso de rango.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: incremento con auditoría y ascenso</strong></li>
        <li>Dado <strong>ROLE_TEACHER</strong> o <strong>ROLE_ADMIN</strong> y un <code>profileId</code> válido</li>
        <li>Cuando envío <code>points &gt; 0</code>, <code>reason</code> y <code>externalRefId</code> opcional</li>
        <li>Entonces respondo <strong>200 OK</strong>, incremento <strong>currentScore</strong> y <strong>totalScore</strong>, registro <strong>ScoreAuditLog</strong> con puntaje anterior/nuevo y tipo de cambio, y actualizo <strong>rank</strong> si cruza umbral (todo en una transacción)</li>
      </ul>
      <ul>
        <li><strong>Escenario: datos inválidos o sin permisos</strong></li>
        <li>Dado <code>points &lt;= 0</code> o rol insuficiente</li>
        <li>Entonces respondo <strong>400 Bad Request</strong> o <strong>403 Forbidden</strong></li>
      </ul>
    </td>
  </tr>
</table>

<table>
  <tr>
    <th>Story ID</th>
    <th>User</th>
    <th>Priority</</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>TPROF-008</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Obtener estado competitivo</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>GET /profiles/{profileId}/score</strong> para consultar el estado competitivo del perfil, incluyendo su nivel actual y puntuaciones vigentes.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: estado actual</strong></li>
        <li>Dado <code>profileId</code> válido y permisos (propietario o <strong>TEACHER/ADMIN</strong>)</li>
        <li>Cuando consulto el estado competitivo</li>
        <li>Entonces respondo <strong>200 OK</strong> con <code>{ profileId, rankId, rankName, currentScore, totalScore }</code></li>
      </ul>
      <ul>
        <li><strong>Escenario: perfil inexistente</strong></li>
        <li>Dado un <code>id</code> inválido</li>
        <li>Entonces respondo <strong>404 Not Found</strong></li>
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
    <td>TPROF-009</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como administrador o docente (ROLE_ADMIN/ROLE_TEACHER), quiero gestionar puntuación y niveles para reflejar progreso y motivar a los usuarios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Listar historial de puntuación</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>GET /profiles/{profileId}/score/audit-logs</strong> con orden cronológico para proveer una auditoría completa de los cambios de puntuación.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: historial disponible</strong></li>
        <li>Dado un perfil con eventos registrados</li>
        <li>Cuando consulto <code>audit-logs</code></li>
        <li>Entonces respondo <strong>200 OK</strong> con lista ordenada por fecha/hora incluyendo <strong>tipo de cambio</strong>, <strong>puntos</strong>, <strong>puntaje anterior/nuevo</strong>, <strong>razón</strong> y <strong>referencia externa</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: perfil inexistente o sin eventos</strong></li>
        <li>Dado un <code>id</code> inválido</li>
        <li>Entonces respondo <strong>404 Not Found</strong></li>
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
    <td>TPROF-010</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como comunidad (todos los roles), quiero un leaderboard con límites para reconocer a los mejores y fomentar competencia sana.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Leaderboard top-N</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero exponer <strong>GET /leaderboard</strong> con límite y orden descendente para ofrecer visibilidad del top de usuarios y fortalecer la competitividad dentro de la comunidad.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: top por puntuación</strong></li>
        <li>Dado usuarios con distintas puntuaciones</li>
        <li>Cuando consulto <code>/leaderboard?limit=L</code> (por defecto 10, máximo 100)</li>
        <li>Entonces respondo <strong>200 OK</strong> con <strong>L</strong> entradas ordenadas descendentemente por <strong>currentScore</strong> e incluyo <strong>profileId</strong>, <strong>rankName</strong> y <strong>currentScore</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario: límite inválido</strong></li>
        <li>Dado <code>L &gt; 100</code> o <code>L &lt;= 0</code></li>
        <li>Entonces respondo <strong>400 Bad Request</strong></li>
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
    <td>TPROF-011</td>
    <td>Desarrollador</td>
    <td>Media</td>
    <td>Como usuario (ROLE_STUDENT/ROLE_TEACHER), quiero consultar mi puntuación/nivel e historial para seguir mi progreso y auditar cambios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">Documentación y errores estándar</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero documentar OpenAPI y aplicar códigos HTTP consistentes para asegurar contratos claros y predecibles entre servicios y consumidores de la API.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: documentación disponible</strong></li>
        <li>Dado el servicio operativo</li>
        <li>Cuando accedo a <strong>Swagger UI</strong> o al <strong>JSON OpenAPI</strong></li>
        <li>Entonces encuentro todos los endpoints con esquemas, parámetros y respuestas documentadas</li>
      </ul>
      <ul>
        <li><strong>Escenario: errores consistentes</strong></li>
        <li>Dado validaciones o recursos inexistentes</li>
        <li>Entonces el servicio responde con códigos <strong>400 / 404 / 409 / 401 / 403</strong> según corresponda, con mensajes trazables</li>
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
    <td>TPROF-012</td>
    <td>Desarrollador</td>
    <td>Baja</td>
    <td>Como usuario (ROLE_STUDENT/ROLE_TEACHER), quiero consultar mi puntuación/nivel e historial para seguir mi progreso y auditar cambios.</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4" style="color: green;">IDs y auditoría de entidades</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como desarrollador, quiero asegurar el uso de identificadores <strong>UUID v4</strong> y auditoría de entidades para mantener la trazabilidad, integridad y unicidad en la base de datos.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario: creación de recursos</strong></li>
        <li>Dado la creación de <strong>Profile</strong> y <strong>ScoreAuditLog</strong></li>
        <li>Cuando se persisten en la base de datos</li>
        <li>Entonces usan <strong>UUID v4</strong> como identificadores y campos auditables <strong>createdAt / updatedAt</strong> gestionados automáticamente</li>
      </ul>
    </td>
  </tr>
</table>


<table>
  <tr>
    <th>Story ID</th>
    <th>Type</th>
    <th>Priority</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>SP01</td>
    <td>Spike (Investigación Técnica)</td>
    <td>Alta</td>
    <td>WebSocket + OAuth2 para Sesiones en Vivo</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4">Integrar WebSocket con OAuth2 y JWT para autenticación en sesiones en vivo</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como equipo de desarrollo, queremos investigar cómo integrar WebSocket con OAuth2 y JWT
      para documentar un método seguro de establecer sesiones en vivo con autenticación válida,
      asegurando la protección de los canales de comunicación en tiempo real.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario 1: investigación documental y bibliográfica</strong></li>
        <li>Dado que el equipo no conoce un método claro para autenticar WebSockets con OAuth2 y JWT</li>
        <li>Cuando se revisa documentación oficial, artículos técnicos y ejemplos en GitHub</li>
        <li>Entonces se identifican al menos <strong>dos enfoques viables</strong> y se documentan sus ventajas, desventajas y requisitos técnicos en un informe comparativo</li>
      </ul>
      <ul>
        <li><strong>Escenario 2: prototipo de autenticación exitosa</strong></li>
        <li>Dado que se dispone de un entorno de prueba controlado</li>
        <li>Cuando se implementa un prototipo mínimo con <strong>handshake WebSocket</strong> que valida un <strong>JWT</strong> emitido previamente</li>
        <li>Entonces la conexión se establece correctamente y el flujo queda documentado paso a paso en una guía técnica</li>
      </ul>
      <ul>
        <li><strong>Escenario 3: validación de errores y casos límite</strong></li>
        <li>Dado que el prototipo permite pruebas controladas</li>
        <li>Cuando se intenta conectar con tokens inválidos o expirados</li>
        <li>Entonces el servidor <strong>rechaza o cierra la conexión</strong> según corresponda</li>
        <li>Y se documenta el manejo de errores recomendado para la implementación futura</li>
      </ul>
    </td>
  </tr>
</table>

<table>
  <tr>
    <th>Story ID</th>
    <th>Type</th>
    <th>Priority</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>SP02</td>
    <td>Spike (Investigación Técnica)</td>
    <td>Alta</td>
    <td>API Gateway para Autenticación y Rate Limiting</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4">Evaluar implementación de API Gateway con autenticación, rate limiting y CORS centralizado</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como equipo de desarrollo, queremos evaluar el uso de un <strong>API Gateway</strong> 
      para definir una estrategia centralizada de autenticación, limitación de uso (rate limiting) 
      y enrutamiento hacia los microservicios, con el fin de mejorar la seguridad, el control de tráfico 
      y la mantenibilidad de la arquitectura distribuida.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario 1: validación de JWT en prototipo</strong></li>
        <li>Dado que el equipo desconoce cómo validar <strong>JWT</strong> en un API Gateway</li>
        <li>Cuando se revisa documentación oficial y ejemplos en GitHub</li>
        <li>Y se implementa un prototipo que reenvía solicitudes con un <strong>JWT válido</strong> a un servicio de prueba</li>
        <li>Entonces la solicitud es aceptada y enrutada correctamente</li>
        <li>Y el flujo queda documentado con diagramas y pasos reproducibles</li>
      </ul>
      <ul>
        <li><strong>Escenario 2: prueba de políticas de rate limiting</strong></li>
        <li>Dado que se requiere definir límites de uso centralizados</li>
        <li>Cuando se configura una política de <strong>50 solicitudes por minuto</strong> en el prototipo</li>
        <li>Y se ejecutan pruebas de carga con múltiples peticiones simultáneas</li>
        <li>Entonces el sistema responde con <strong>HTTP 429 Too Many Requests</strong> al superar el límite</li>
        <li>Y se documenta la política y parámetros utilizados</li>
      </ul>
      <ul>
        <li><strong>Escenario 3: configuración de CORS centralizado</strong></li>
        <li>Dado que el equipo necesita manejar <strong>CORS</strong> desde el gateway</li>
        <li>Cuando se aplican reglas para permitir solo dominios autorizados</li>
        <li>Y se realiza una solicitud <strong>preflight</strong> desde un frontend autorizado</li>
        <li>Entonces se reciben las cabeceras <strong>CORS correctas</strong> (Access-Control-Allow-*)</li>
        <li>Y la configuración final queda registrada en la guía técnica</li>
      </ul>
    </td>
  </tr>
</table>



<table>
  <tr>
    <th>Story ID</th>
    <th>Type</th>
    <th>Priority</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>SP03</td>
    <td>Spike (Investigación Técnica)</td>
    <td>Alta</td>
    <td>Apache Kafka para Respuestas en Vivo</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4">Evaluar Apache Kafka para procesar respuestas en tiempo real con métricas de sesión</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como equipo de desarrollo, queremos investigar el uso de <strong>Apache Kafka</strong> para procesar respuestas en tiempo real,
      a fin de identificar una arquitectura que permita calcular métricas de sesión sin afectar el rendimiento de la plataforma.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario 1: prototipo y medición de latencia</strong></li>
        <li>Dado que el equipo necesita validar el procesamiento en tiempo real</li>
        <li>Cuando se construye un prototipo con un tópico de entrada (<code>responses.ses_01A</code>) y un job de stream (Kafka Streams o Flink) que agrega métricas (conteo, promedio, p50/p95)</li>
        <li>Entonces se evidencia, con mediciones reproducibles, una <strong>latencia p95 ≤ 1 s</strong> desde publicación hasta métrica agregada</li>
        <li>Y se documenta la configuración (particiones, acks, <code>batch.size</code>, <code>linger.ms</code>, etc.)</li>
      </ul>
      <ul>
        <li><strong>Escenario 2: validación de esquema</strong></li>
        <li>Dado que se requiere estabilidad de contrato de datos</li>
        <li>Cuando se integra un <strong>Schema Registry</strong> (p. ej., Avro/JSON Schema) y se publican eventos válidos e inválidos</li>
        <li>Entonces los eventos válidos son procesados y los inválidos son rechazados con <strong>logs trazables</strong></li>
        <li>Y se documentan compatibilidades (<strong>BACKWARD/FORWARD</strong>) y el procedimiento para evolución de esquema</li>
      </ul>
      <ul>
        <li><strong>Escenario 3: manejo de errores y DLQ</strong></li>
        <li>Dado que el sistema debe ser tolerante a mensajes malformados o no procesables</li>
        <li>Cuando el consumidor encuentra un evento con error irrecuperable</li>
        <li>Entonces el mensaje se enruta a un tópico <strong>DLQ</strong> con metadatos (offset, key, excepción) y el flujo principal continúa</li>
        <li>Y se documenta la política de <strong>reintentos</strong>, <strong>dead lettering</strong> y <strong>observabilidad</strong> (métricas/alertas)</li>
      </ul>
    </td>
  </tr>
</table>

<table>
  <tr>
    <th>Story ID</th>
    <th>Type</th>
    <th>Priority</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>SP04</td>
    <td>Spike (Investigación Técnica)</td>
    <td>Alta</td>
    <td>Proveedor PostgreSQL: Aiven</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4">Evaluar Aiven como proveedor de PostgreSQL gestionado con HA, seguridad y respaldos automáticos</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como equipo de desarrollo, queremos evaluar a <strong>Aiven</strong> como proveedor de <strong>PostgreSQL gestionado</strong>,
      para determinar si cumple con los requisitos de alta disponibilidad, seguridad y respaldos automáticos
      de la base de datos principal del sistema.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario 1: backup y Point-in-Time Restore (PITR) con métricas</strong></li>
        <li>Dado una base de prueba con dataset conocido (filas y checksums registrados)</li>
        <li>Cuando se habilitan y verifican los <strong>backups automáticos</strong> y se ejecuta un restore a un punto en el tiempo T</li>
        <li>Entonces los datos restaurados coinciden (conteos y checksums)</li>
        <li>Y se documentan los valores observados de <strong>RPO</strong> y <strong>RTO</strong>, junto con los pasos exactos del proceso PITR</li>
      </ul>
      <ul>
        <li><strong>Escenario 2: failover automático en plan HA</strong></li>
        <li>Dado un clúster con <strong>alta disponibilidad (HA)</strong> habilitada</li>
        <li>Cuando se fuerza una conmutación (mantenimiento, switchover o caída simulada del primario)</li>
        <li>Entonces el servicio sigue disponible mediante el endpoint gestionado</li>
        <li>Y se mide el tiempo de <strong>failover efectivo</strong>, documentando además el comportamiento del cliente (p. ej., pgbouncer o connection string)</li>
      </ul>
      <ul>
        <li><strong>Escenario 3: controles de seguridad y aislamiento de red</strong></li>
        <li>Dado que se requiere <strong>seguridad en tránsito y en reposo</strong></li>
        <li>Cuando se verifica el uso de <strong>TLS</strong> para conexiones, cifrado en reposo, aislamiento de red (VPC peering o allow-lists) y políticas de acceso (roles/ACLs)</li>
        <li>Entonces se valida que los controles funcionan (tests de conexión con/sin TLS, accesos permitidos/denegados por red)</li>
        <li>Y se documenta la configuración aplicada, junto con logs, auditoría y hallazgos de seguridad detectados</li>
      </ul>
    </td>
  </tr>
</table>

<table>
  <tr>
    <th>Story ID</th>
    <th>Type</th>
    <th>Priority</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>SP05</td>
    <td>Spike (Investigación Técnica)</td>
    <td>Alta</td>
    <td>Spring Data Mongo para Social Feed</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4">Evaluar Spring Data MongoDB para publicaciones, comentarios y reacciones con foco en rendimiento y escalabilidad</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como equipo de desarrollo, queremos investigar el uso de <strong>Spring Data MongoDB</strong> para validar si soporta
      publicaciones, comentarios y reacciones con el rendimiento y la escalabilidad requeridos en el módulo social
      (feed, conteos, concurrencia y crecimiento sostenido).
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario 1: feed paginado con índices y evidencia de latencia</strong></li>
        <li>Dado que necesitamos validar la lectura eficiente del feed</li>
        <li>Cuando construimos un prototipo con Spring Data MongoDB que pagina publicaciones (ordenadas por <code>createdAt</code> y/o <code>score</code>) usando índices adecuados</li>
        <li>Y cargamos una colección de prueba (≥ 100k publicaciones)</li>
        <li>Entonces obtenemos <strong>p95 ≤ 200 ms</strong> para páginas típicas (tamaño definido)</li>
        <li>Y dejamos evidencia con <code>explain()</code> de las consultas, índices usados y recomendaciones (p. ej., <em>keyset pagination</em> vs <code>skip/limit</code>) documentadas</li>
      </ul>
      <ul>
        <li><strong>Escenario 2: contador de “likes” bajo alta concurrencia (sin sobrecontar)</strong></li>
        <li>Dado que debemos evitar sobreconteo con múltiples usuarios reaccionando al mismo post</li>
        <li>Cuando implementamos operaciones atómicas (<code>$inc</code> / <code>$addToSet</code> con índice único por <code>postId+userId</code> o patrón equivalente) y simulamos concurrencia</li>
        <li>Entonces no se produce sobreconteo (la métrica de likes coincide con los eventos únicos)</li>
        <li>Y se documenta el patrón elegido, pruebas de carrera realizadas y <em>trade-offs</em> (consistencia vs. costo)</li>
      </ul>
      <ul>
        <li><strong>Escenario 3: estrategia de escalabilidad (particionado/sharding) para el feed</strong></li>
        <li>Dado que el volumen y el acceso al feed pueden crecer significativamente</li>
        <li>Cuando evaluamos claves de partición candidatas (p. ej., <code>hashed(postId)</code> o compuesta <code>authorId+createdAt</code>) y medimos distribución / “hot partitions” en entorno de prueba</li>
        <li>Entonces documentamos la estrategia recomendada (clave de shard, índices, balanceo esperado), riesgos identificados y lineamientos de migración/operación (TTL/archivado, colecciones inmutables para posts, colecciones separadas para reacciones)</li>
      </ul>
    </td>
  </tr>
</table>

<table>
  <tr>
    <th>Story ID</th>
    <th>Type</th>
    <th>Priority</th>
    <th>Epic</th>
  </tr>
  <tr>
    <td>SP06</td>
    <td>Spike (Investigación Técnica)</td>
    <td>Alta</td>
    <td>Observabilidad en Tiempo Real con OpenTelemetry</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Title</th>
  </tr>
  <tr>
    <td colspan="4">Explorar OpenTelemetry + Prometheus + Grafana para métricas, trazas y errores en tiempo real</td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Description</th>
  </tr>
  <tr>
    <td colspan="4">
      Como equipo de desarrollo, queremos explorar el uso de <strong>OpenTelemetry</strong> junto con <strong>Prometheus</strong> y <strong>Grafana</strong>
      para establecer una solución de observabilidad en tiempo real (métricas, trazas y errores) que garantice la calidad de servicio y facilite el diagnóstico.
    </td>
  </tr>
  <tr>
    <th colspan="4" style="color: green;">Acceptance Criteria</th>
  </tr>
  <tr>
    <td colspan="4">
      <ul>
        <li><strong>Escenario 1: trazas end-to-end instrumentadas y visibles</strong></li>
        <li>Dado que necesitamos confirmar la <strong>trazabilidad completa</strong></li>
        <li>Cuando instrumentamos un flujo mínimo <strong>API Gateway → Servicio A → Kafka Producer → Kafka Consumer (Servicio B)</strong> con OpenTelemetry (propagación W3C <code>traceparent</code>) y enviamos spans vía <strong>OTLP</strong> al <em>OpenTelemetry Collector</em></li>
        <li>Entonces en <strong>Grafana</strong> (con <strong>Tempo/Jaeger</strong> como backend de trazas) se visualiza una <strong>traza única</strong> que encadena spans de gateway, servicios y consumidores Kafka</li>
        <li>Y los spans incluyen atributos clave (<code>http.route</code>, <code>messaging.system=kafka</code>, <code>enduser.id</code> simulado); se dejan <strong>capturas/IDs</strong> y <strong>pasos de configuración</strong> documentados</li>
      </ul>
      <ul>
        <li><strong>Escenario 2: métricas + alerta de latencia p95</strong></li>
        <li>Dado que debemos alertar ante <strong>degradación</strong></li>
        <li>Cuando exponemos métricas con OTel (histogramas <code>http.server.duration</code>) y las recolecta <strong>Prometheus</strong> (vía OTel Collector → Prometheus exporter)</li>
        <li>Entonces definimos una <strong>alerta</strong> en Grafana/Prometheus: <strong>p95 &gt; 300 ms</strong> durante 5 min (usando <code>histogram_quantile</code>)</li>
        <li>Y la alerta se dispara y <strong>notifica</strong> al canal acordado (Alertmanager/Grafana Alerting); se documentan la <strong>regla</strong>, el <strong>panel</strong> y el <strong>destino de notificación</strong></li>
      </ul>
      <ul>
        <li><strong>Escenario 3: errores y correlación con logs</strong></li>
        <li>Dado que necesitamos <strong>diagnosticar fallos</strong> rápidamente</li>
        <li>Cuando registramos excepciones con OTel (<code>status=ERROR</code>, eventos <code>exception.*</code>) y habilitamos <strong>exemplars</strong> para correlacionar métricas con trazas, además de propagar <code>trace_id</code> a logs (JSON)</li>
        <li>Entonces en Grafana podemos: ver el <strong>ratio de errores</strong> por endpoint/servicio, saltar desde un <strong>exemplar</strong> de la serie temporal a la traza específica, y desde la traza abrir los <strong>logs correlacionados</strong> por <code>trace_id</code></li>
        <li>Y se documenta la configuración del Collector (pipelines, exporters) y se entregan <strong>dashboards base</strong></li>
      </ul>
    </td>
  </tr>
</table>



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

| # Orden | User Story Id | TITULO                                                       | Story Points |
| ------- | ------------- | ------------------------------------------------------------ | ------------ |
| 1       | US-001        | Crear quiz                                                   | 2            |
| 2       | US-002        | Actualizar quiz                                              | 1            |
| 3       | US-003        | Eliminar quiz                                                | 1            |
| 4       | US-004        | Publicar quiz                                                | 2            |
| 5       | US-005        | Agregar pregunta                                             | 3            |
| 6       | US-006        | Actualizar pregunta                                          | 2            |
| 7       | US-007        | Eliminar pregunta                                            | 1            |
| 8       | US-008        | Consultar quiz                                               | 1            |
| 9       | US-009        | Listar quizzes públicos                                      | 2            |
| 10      | US-010        | Listar mis quizzes                                           | 1            |
| 11      | US-011        | Crear sesión en vivo                                         | 3            |
| 12      | US-012        | Unirse a sesión                                              | 2            |
| 13      | US-013        | Iniciar sesión                                               | 1            |
| 14      | US-014        | Iniciar pregunta                                             | 1            |
| 15      | US-015        | Enviar respuesta                                             | 3            |
| 16      | US-016        | Avanzar pregunta                                             | 1            |
| 17      | US-017        | Finalizar sesión y ranking                                   | 2            |
| 18      | US-018        | Consultar sesión                                             | 1            |
| 19      | US-019        | Expulsar participante                                        | 2            |
| 20      | US-020        | Generar reporte                                              | 3            |
| 21      | US-021        | Consultar reporte                                            | 1            |
| 22      | US-022        | Exportar reporte                                             | 2            |
| 23      | TUS-001       | Implementar endpoint POST /quizzes                           | 3            |
| 24      | TUS-002       | Implementar endpoint PUT /quizzes/{id}                       | 2            |
| 25      | TUS-003       | Implementar endpoint DELETE /quizzes/{id}                    | 1            |
| 26      | TUS-004       | Implementar endpoint POST /quizzes/{id}/publish              | 2            |
| 27      | TUS-005       | Implementar endpoint POST /quizzes/{id}/questions            | 3            |
| 28      | TUS-006       | Implementar endpoint PUT /questions/{id}                     | 2            |
| 29      | TUS-007       | Implementar endpoint DELETE /questions/{id}                  | 1            |
| 30      | TUS-008       | Implementar endpoint GET /quizzes/{id}                       | 2            |
| 31      | TUS-009       | Implementar endpoint GET /quizzes/public                     | 3            |
| 32      | TUS-010       | Implementar endpoint GET /users/{userId}/quizzes             | 2            |
| 33      | TUS-011       | Implementar endpoint POST /sessions                          | 5            |
| 34      | TUS-012       | Implementar endpoint POST /sessions/{code}/join              | 3            |
| 35      | TUS-013       | Implementar endpoint POST /sessions/{id}/start               | 2            |
| 36      | TUS-014       | Implementar endpoint POST /sessions/{id}/questions/start     | 2            |
| 37      | TUS-015       | Implementar endpoint POST /sessions/{id}/answers             | 3            |
| 38      | TUS-016       | Implementar endpoint POST /sessions/{id}/questions/advance   | 2            |
| 39      | TUS-017       | Implementar endpoint POST /sessions/{id}/finish              | 3            |
| 40      | TUS-018       | Implementar endpoint GET /sessions/{code}                    | 2            |
| 41      | TUS-019       | Implementar endpoint POST /sessions/{id}/participants/{participantId}/kick | 2            |
| 42      | TUS-020       | Implementar endpoint POST /sessions/{id}/reports             | 5            |
| 43      | TUS-021       | Implementar endpoint GET /reports/{id}                       | 2            |
| 44      | TUS-022       | Implementar endpoint GET /reports/{id}/export                | 3            |
| 45      | TUS-023       | Implementar optimizaciones de rendimiento para endpoints REST | 5            |
| 46      | TUS-024       | Implementar WebSocket con baja latencia                      | 5            |
| 47      | TUS-025       | Implementar alta disponibilidad                              | 8            |
| 48      | COMM-US-001   | Crear publicación con multimedia                             | 2            |
| 49      | COMM-US-002   | Editar y eliminar publicaciones                              | 5            |
| 50      | COMM-US-003   | Fijar publicaciones importantes                              | 3            |
| 51      | COMM-US-004   | Visualizar feed de publicaciones                             | 2            |
| 52      | COMM-US-005   | Comentar en publicaciones                                    | 2            |
| 53      | COMM-US-006   | Reaccionar con likes                                         | 3            |
| 54      | COMM-US-007   | Recibir notificaciones en tiempo real                        | 2            |
| 55      | COMM-US-008   | Moderar contenido reportado                                  | 3            |
| 56      | IAM-US-001    | Registro con validaciones y rol por defecto                  | 2            |
| 57      | IAM-US-002    | Inicio de sesión (email/contraseña)                          | 2            |
| 58      | IAM-US-003    | Rechazo por credenciales inválidas                           | 5            |
| 59      | IAM-US-004    | Renovación de token (refresh)                                | 2            |
| 60      | IAM-US-005    | Validación de token de acceso                                | 3            |
| 61      | IAM-US-006    | Autenticación con proveedores (Google/GitHub)                | 5            |
| 62      | IAM-US-007    | Caso GitHub sin email                                        | 5            |
| 63      | IAM-US-008    | Listar usuarios (ADMIN)                                      | 8            |
| 64      | IAM-US-009    | Obtener usuario por ID o email                               | 2            |
| 65      | IAM-US-010    | Listar roles y consultar rol                                 | 5            |
| 66      | IAM-US-011    | Seed de roles base                                           | 3            |
| 67      | IAM-US-012    | Puntaje de fortaleza 0–5                                     | 2            |
| 68      | IAM-US-013    | Asignación de múltiples roles                                | 2            |
| 69      | TIAM-001      | Implementar POST /auth/signup                                | 3            |
| 70      | TIAM-002      | Implementar POST /auth/signin                                | 2            |
| 71      | TIAM-003      | Implementar POST /auth/token/refresh                         | 3            |
| 72      | TIAM-004      | Implementar POST /auth/token/validate                        | 2            |
| 73      | TIAM-005      | Implementar /auth/oauth2/authorize y /auth/oauth2/callback   | 2            |
| 74      | TIAM-006      | Implementar GET /users (paginado)                            | 5            |
| 75      | TIAM-007      | Implementar GET /users/{userId} y GET /users:by-email        | 2            |
| 76      | TIAM-008      | Implementar GET /roles y GET /roles/{roleName}               | 3            |
| 77      | TIAM-009      | Implementar POST /roles/seed                                 | 5            |
| 78      | TIAM-010      | Implementar POST /auth/password/strength                     | 5            |
| 79      | TIAM-011      | Implementar POST /users/{userId}/roles                       | 8            |
| 80      | TIAM-012      | Documentación OpenAPI 3.0                                    | 2            |
| 81      | TIAM-013      | Configurar HTTPS y CORS                                      | 2            |
| 82      | TIAM-014      | Filtro de autenticación/autoría JWT                          | 2            |
| 83      | TIAM-015      | Logging y métricas de seguridad                              | 5            |
| 84      | PROF-US-001   | Crear perfil con username y rank inicial                     | 3            |
| 85      | PROF-US-002   | Consultar perfil por ID o Username                           | 2            |
| 86      | PROF-US-003   | Listar perfiles                                              | 2            |
| 87      | PROF-US-004   | Seed de niveles competitivos                                 | 3            |
| 88      | PROF-US-005   | Consultar niveles                                            | 2            |
| 89      | PROF-US-006   | Agregar puntos y evaluar ascenso                             | 3            |
| 90      | PROF-US-007   | Consultar nivel y puntuación actual                          | 2            |
| 91      | PROF-US-008   | Ver historial de cambios de puntuación                       | 2            |
| 92      | PROF-US-009   | Leaderboard con límite y orden                               | 5            |
| 93      | PROF-US-010   | Reasignación automática de nivel                             | 2            |
| 94      | TPROF-001     | Implementar endpoint POST /profiles                          | 3            |
| 95      | TPROF-002     | Obtener perfil por ID                                        | 5            |
| 96      | TPROF-003     | Obtener perfil por Username                                  | 5            |
| 97      | TPROF-004     | Listar perfiles (paginado)                                   | 8            |
| 98      | TPROF-005     | Seed de niveles                                              | 2            |
| 99      | TPROF-006     | Listar y detallar niveles                                    | 2            |
| 100     | TPROF-007     | Agregar puntos y evaluar ascenso                             | 5            |
| 101     | TPROF-008     | Obtener estado competitivo                                   | 2            |
| 102     | TPROF-009     | Listar historial de puntuación                               | 3            |
| 103     | TPROF-010     | Leaderboard top-N                                            | 3            |
| 104     | TPROF-011     | Documentación y errores estándar                             | 2            |
| 105     | TPROF-012     | IDs y auditoría de entidades                                 | 2            |
| 106     | SP01          | WebSocket + OAuth2 para Sesiones en Vivo                     | 3            |
| 107     | SP02          | API Gateway para Autenticación y Rate Limiting               | 3            |
| 108     | SP03          | Apache Kafka para Respuestas en Vivo                         | 2            |
| 109     | SP04          | Proveedor PostgreSQL: Aiven                                  | 2            |
| 110     | SP05          | Spring Data Mongo para Social Feed1                          | 1            |
| 111     | SP06          | Observabilidad en Tiempo Real con OpenTelemetry              | 5            |

