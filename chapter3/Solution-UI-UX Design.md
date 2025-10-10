# Capítulo III: Solution UI/UX Design

## 3.1. Product design

### 3.1.1. Style Guidelines

Esta sección define la identidad visual y los patrones de diseño que aseguran consistencia en la landing page de Level Up Journey. Se estructura en torno a los principios de tipografía, color, iconografía, componentes interactivos y lineamientos gráficos generales, implementados mediante Tailwind CSS y Astro framework.

#### 3.1.1.1. General Style Guidelines

**Tipografía para Landing Page:**
- Fuentes primarias del sistema de fuentes web por defecto de Tailwind (inter, sans-serif)
- Jerarquía tipográfica con títulos principales (H1) de text-5xl a text-7xl (48px-72px), font-bold (700)
- Subtítulos (H2) de text-3xl a text-5xl (30px-48px), font-bold (700)
- Texto de párrafo de text-base a text-xl (16px-20px), font-normal (400)
- Texto secundario de text-sm (14px), text-gray-400
- Espaciado y legibilidad con interlineado leading-relaxed (1.625) para párrafos
- Márgenes del sistema de espaciado consistente (mb-4, mb-6, mb-12)
- Pesos tipográficos: font-normal (400), font-semibold (600), font-bold (700)

**Consideraciones para adaptación móvil:**

- Fuentes optimizadas como SF Pro Display o Roboto para mejor legibilidad en pantallas pequeñas
- Escala responsiva con tamaños adaptativos mediante breakpoints de Tailwind (sm:, md:, lg:)
- Contraste garantizado con texto blanco sobre fondos oscuros (neutral-950) con ratio de contraste mínimo 4.5:1
- Tamaño mínimo de 14px para texto de lectura, 16px para elementos interactivos

**Paleta de colores para Landing Page:**
- Color primario (Primary) red-600 (#DC2626) para botones principales y elementos de acción
- Color secundario (Secondary) neutral-700 (#404040) para bordes y elementos decorativos
- Color de fondo principal neutral-950 (#0A0A0A) para fondo general de la página
- Color de fondo secundario neutral-900 (#171717) para tarjetas, formularios y secciones destacadas
- Color de texto primario white (#FFFFFF) para títulos y texto principal
- Color de texto secundario gray-400 (#9CA3AF) para descripciones y texto complementario
- Color de acento red-600 (#DC2626) para elementos interactivos y llamadas a acción

**Implementación móvil:**

- Adaptación Material Design con colores equivalentes en formato ARGB para Android
- Modo oscuro nativo aprovechando el sistema de colores del dispositivo
- Colores de estado: Success (green-500), Warning (yellow-500), Error (red-500)

**Reglas de contraste y accesibilidad:**
- Ratio de contraste mínimo 4.5:1 para texto normal, 3:1 para texto grande (WCAG AA)
- Texto sobre fondo oscuro blanco (#FFFFFF) sobre neutral-950 (#0A0A0A) = ratio 15.8:1
- Texto secundario gray-400 (#9CA3AF) sobre neutral-950 = ratio 5.2:1
- Elementos interactivos con foco visible mediante outline o border

**Estados interactivos:**
- Hover con hover:bg-red-700 para botones, hover:border-gray-600 para tarjetas
- Focus con focus:ring-2 focus:ring-red-600 con outline visible
- Active con active:scale-95 para feedback táctil simulado
- Disabled con opacity-50 cursor-not-allowed con pointer-events deshabilitados

**Logotipo y elementos de marca:**
- Logotipo principal imagen SVG level-up-cat-happy.svg como favicon
- Título de marca "Level Up Journey" con fuente bold y jerarquía visual
- Proporciones logotipo circular con relación de aspecto 1:1
- Área protegida mínimo 8px de espacio alrededor del logotipo
- Restricciones no distorsionar proporciones, mantener colores originales
- Uso en fondos optimizado para fondos oscuros (neutral-950)

**Iconografía institucional y favicons:**

- Iconos de sección SVG optimizados en /assets/section2/icons/ (code.svg para editor de código, calendar-check.svg para retos semanales, hammer.svg para retroalimentación)

  - `code.svg` - Editor de código
      ![code](./assets/Style-Guidelines/code.svg)
    - `calendar-check.svg` - Retos semanales
      ![calendar-check](./assets/Style-Guidelines/calendar-check.svg)
    - `hammer.svg` - Retroalimentación
      ![hammer](./assets/Style-Guidelines/hammer.svg)

- Iconos de navegación i18n.svg, account.svg en /assets/header/

   ![i18n](./assets/Style-Guidelines/i18n.svg)
    ![account](./assets/Style-Guidelines/account.svg)

- Favicon level-up-cat-happy.svg versión optimizada 32x32px

  ![level-up-cat-happy](./assets/Style-Guidelines/level-up-cat-happy.svg)

**Imágenes e ilustraciones:**
- Estilo visual fotografía oscura con overlays para mejorar legibilidad
- Tratamiento overlay negro con opacidad 50% sobre imágenes de fondo
- Ilustraciones y gráficos vectoriales con iconos de lenguajes SVG en /assets/section1/programming-languages/ (C++, Java, JavaScript, Python)
- Gráficos vectoriales optimizados para escalabilidad

**Resolución y formato:**

- Formato preferido SVG para iconos, WebP/PNG para fotografías
- Resolución mínimo 2x para retina displays
- Compresión optimización automática vía Astro

**Lineamientos específicos para web y móvil:**
- Web imágenes de fondo full-width con bg-cover
- Móvil adaptación responsiva con bg-center y overlays ajustados

**Botones y componentes interactivos:**
- Tipos de botones Primario (bg-red-600 hover:bg-red-700 text-white) para llamadas a acción principales
- Secundario (bg-neutral-900 border border-neutral-700) para acciones secundarias
- Outline (border border-red-600 text-red-600 hover:bg-red-600) para acciones alternativas
- Ghost (text-white hover:bg-white/10) para acciones sutiles

**Estados de interacción y retroalimentación visual:**

- Hover cambio de color de fondo con transición duration-200
- Focus ring visible focus:ring-2 focus:ring-red-600
- Active efecto de escala active:scale-95
- Loading opacidad reducida durante procesos asíncronos

**Dimensiones y márgenes táctiles mínimos:**
- Botones principales px-8 py-4 (128px x 64px)
- Botones pequeños px-6 py-3 (96px x 48px)
- Margen táctil mínimo 44px de altura para accesibilidad móvil

**Iconografía asociada a botones:**
- Botón de idioma i18n.svg (24x24px)
- Botón de cuenta account.svg (28x28px)
- Botones de sección iconos contextuales en tarjetas

**Componentes derivados:**
- Inputs bg-neutral-900/80 border border-neutral-700 rounded-lg con placeholder
- Cards .card class con border border-gray-700 rounded-lg p-6 lg:p-8
- Modals futura implementación con overlays oscuros
- Tabs sistema de navegación horizontal
- Snackbars notificaciones temporales (planeadas)
- Progress Indicators barras de progreso para carga

**Elementos específicos por tipo de producto:**
- Sistema de cuadrícula 12 columnas con Tailwind Grid
- Breakpoints sm: (640px), md: (768px), lg: (1024px)
- Container max-w-7xl mx-auto para contenido centrado

**Navegación y estructura:**
- Header fijo fixed top-0 con backdrop-blur al scroll
- Secciones min-h-screen para hero, py-16 lg:py-20 para secciones
- Footer enlaces organizados en grid

**Comportamientos y microinteracciones:**

- Scroll effects header con scrolled class y blur effect
- Hover animations transition-colors duration-200
- Floating elements componente FloatingLanguages con física de burbujas

**Adaptabilidad entre web y móvil:**
- Responsive images w-full con aspect ratios
- Flexible layouts grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Touch targets mínimo 44px para elementos interactivos

**Consistencia y adaptabilidad del sistema de diseño:**
- Variables CSS sistema de design tokens en :root
- Clases reutilizables .section, .container-custom, .card
- Naming convention BEM-like con Tailwind utilities

**Librería de componentes reutilizables:**
- Componentes base Header, Footer, Section components
- Utilidades classes globales en global.css
- Modularidad separación por funcionalidad

**Versionado y documentación del Design System:**
- Documentación este documento como guía de estilos
- Versionado control de versiones con Git
- Consistencia revisiones regulares de implementación

  ![1c05e5c8-f479-4e5f-815c-d44a0104caae 3.svg](assets/Components/1c05e5c8-f479-4e5f-815c-d44a0104caae%203.svg)
  ![7e4f1287-0466-43a9-b7ed-d1315976c28f](./assets/Components/7e4f1287-0466-43a9-b7ed-d1315976c28f.svg)
  ![b2d19ef2-33a7-469c-a13f-7fa3b16bcaec](./assets/Components/b2d19ef2-33a7-469c-a13f-7fa3b16bcaec.svg)
  ![Background](./assets/Components/Background.svg)
![Button 10](assets/Components/Button%2010.svg)
  ![Button 11.svg](assets/Components/Button%2011.svg)
![Button 12.svg](assets/Components/Button%2012.svg)
![Button 13.svg](assets/Components/Button%2013.svg)
![Button 14.svg](assets/Components/Button%2014.svg)
![Button 15.svg](assets/Components/Button%2015.svg)
![Button 16.svg](assets/Components/Button%2016.svg)
  ![Button4.svg](assets/Components/Button4.svg)
  ![Card Recent.svg](assets/Components/Card%20Recent.svg)
![Component 1.svg](assets/Components/Component%201.svg)
  ![Content](./assets/Components/Content.svg)
  ![Frame 1321317519.svg](assets/Components/Frame%201321317519.svg)
![Frame 1321317520.svg](assets/Components/Frame%201321317520.svg)
![Frame 1321317521.svg](assets/Components/Frame%201321317521.svg)
![Frame 1321317522.svg](assets/Components/Frame%201321317522.svg)
![Frame 1321317523.svg](assets/Components/Frame%201321317523.svg)
  ![Group 60.svg](assets/Components/Group%2060.svg)
  ![State-layer-1](./assets/Components/State-layer-1.svg)
  ![state-layer](./assets/Components/state-layer.svg)
  ![State-layer](./assets/Components/State-layer.svg)

### 3.1.2. Information Architecture

#### 3.1.2.1. Organization Systems

El contenido de **Level Up Journey** se organiza bajo un esquema jerárquico y temático, priorizando la claridad en la navegación tanto para estudiantes como docentes.  
En la **Landing Page**, la jerarquía visual guía la atención desde el *hero* principal (mensaje motivacional y CTA) hacia secciones secundarias como características, beneficios y testimonios.  

En la **aplicación móvil**, la organización se orienta a las tareas del usuario (*task-oriented design*) mediante módulos:

- **Home:** Accesos rápidos.
- **Comunidad:** interacción social y publicaciones.
- **Actividades:** retos y juegos educativos.
- **Perfil:** Datos personales.
- **Ajustes:** Preferencias de usuario.

Los esquemas de categorización se basan en tópicos (lenguajes de programación, retos, docentes). 
Esta estructura favorece la accesibilidad y evita sobrecarga cognitiva.


#### 3.1.2.2. Labelling Systems

El **sistema de etiquetado** en *Level Up Journey* asegura consistencia semántica y accesibilidad en todos los entornos.  
Se implementa bajo una estructura jerárquica, multilingüe y accesible, adaptada tanto a la **Landing Page** como a la **aplicación móvil**.

En la **Landing Page**, las etiquetas se gestionan mediante el atributo `data-i18n`, que permite la internacionalización dinámica del contenido.  
Cada texto se asocia a un identificador único vinculado con las claves de traducción en los archivos JSON (`es.json`, `en.json`).  
Un script en **JavaScript** escanea el DOM, obtiene los valores según el idioma seleccionado y actualiza los textos en tiempo real, sin recargar la página.

Los identificadores siguen una estructura jerárquica y semántica —por ejemplo:  
`section1.title`, `section2.card1.description`— lo que facilita el mantenimiento y ampliación del sistema de traducción.  
Los elementos de formularios utilizan *placeholders* dinámicos, mientras que los botones y enlaces incluyen atributos `aria-label` que describen su función para usuarios con lectores de pantalla.

En la **aplicación móvil**, las etiquetas se definen en los archivos de recursos nativos:  
`strings.xml` (Android) y `Localizable.strings` (iOS).  
Cada texto visible en la interfaz se representa mediante una clave descriptiva (`login_title`, `game_button_start`, `profile_label_email`), lo que garantiza coherencia y fácil localización.  
El idioma del sistema del dispositivo determina automáticamente qué conjunto de recursos se carga, manteniendo la experiencia homogénea entre plataformas.


#### 3.1.2.3. SEO Tags and Meta Tags

Los **metadatos y etiquetas SEO** se configuran con el propósito de optimizar la visibilidad de *Level Up Journey* en motores de búsqueda y mejorar la accesibilidad técnica del sitio web.

En la **Landing Page**, los elementos principales incluyen:

```html
<title>Level Up Journey | Aprende Programando Jugando</title>

<meta name="description" content="Plataforma educativa gamificada que combina programación, retos y comunidad para estudiantes y docentes.">

<meta name="keywords" content="educación digital, programación, gamificación, aprendizaje interactivo">

<meta name="author" content="Equipo Level Up Journey">

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link rel="icon" href="/level-up-cat-happy.svg" type="image/svg+xml">

<html lang="es">
```


#### 3.1.2.4. Searching Systems

En la **Landing Page**, no se implementa un motor de búsqueda tradicional debido a su carácter informativo.  
Sin embargo, se utilizan estrategias que **simulan una búsqueda guiada**, como el desplazamiento suave hacia secciones ancladas mediante botones *CTA* y una estructura jerárquica clara que facilita la orientación del usuario.

En la **aplicación móvil**, el sistema de búsqueda estará diseñado para mejorar la interacción dentro de los módulos **Comunidad**.  
Incluye:

- Campo de búsqueda global con ícono de lupa.
- Filtros contextuales (tipo de contenido, autor, fecha).

Este sistema reduce la carga cognitiva del usuario y facilita el acceso rápido a información relevante, optimizando la experiencia de navegación dentro de la app.


#### 3.1.2.5. Navigation Systems

El **sistema de navegación** de *Level Up Journey* está diseñado para proporcionar una experiencia fluida y accesible tanto en entorno web como móvil, manteniendo coherencia en los patrones de interacción.

En la **Landing Page**, se implementa un **header fijo** (`position: fixed; z-index: 50`) que permanece visible durante el desplazamiento.  
Este incluye:

- Logotipo que redirige al inicio.
- Selector de idioma desplegable (ES/EN) con transiciones suaves y efecto *backdrop-blur*.
- Botón de cuenta de usuario (`account.svg`) con `aria-label` para accesibilidad.

Al hacer *scroll*, el *header* adopta la clase `scrolled`, aplicando un fondo semitransparente (`rgba(23,23,23,0.95)`) y desenfoque de fondo, mejorando la legibilidad sobre el contenido variable.  
El *footer* presenta enlaces secundarios (privacidad, contacto, redes) organizados en una cuadrícula coherente con el sistema de diseño.

En la **aplicación móvil**, la navegación se basa en una **barra inferior fija** (*bottom navigation bar*) con iconografía minimalista (`home.svg`, `community.svg`, `games.svg`, `profile.svg`).  
Cada ítem cuenta con un estado activo (`fill-red-600`) y animaciones *ease-in-out* que proporcionan retroalimentación táctil.  
Las transiciones entre pantallas se gestionan mediante un sistema de **Stack Navigator**, manteniendo el contexto y estado del usuario.

Este enfoque garantiza una experiencia coherente, intuitiva y accesible en todas las plataformas de *Level Up Journey*.


### 3.1.3. Landing Page UI Design

#### 3.1.3.1. Landing Page Wireframe

#### 3.1.3.2. Landing Page Mock-up

### 3.1.4. Mobile Applications UX/UI Design

#### 3.1.4.1. Mobile Applications Wireframes



#### 3.1.4.2. Mobile Applications Wireflow Diagrams

#### 3.1.4.3. Mobile Applications Mock-ups

#### 3.1.4.4. Mobile Applications User Flow Diagrams


![FLOW 1-.png](assets/user-flows/FLOW%201-.png)

**Flow 1: Autenticación y Gestión de Perfil de Usuario**  
En el contexto de Level Up Journey, este flujo inicia con el proceso de autenticación, donde los estudiantes y docentes pueden registrarse o iniciar sesión utilizando métodos tradicionales (correo y contraseña) o integraciones con plataformas externas como GitHub y Google, facilitando el acceso rápido y seguro. Una vez autenticados, los usuarios acceden a la página principal de la aplicación móvil, desde donde pueden navegar a su perfil personal para gestionar configuraciones como preferencias de idioma, notificaciones y datos de cuenta. Este flujo asegura una experiencia de onboarding fluida, alineada con los objetivos de retención estudiantil al reducir barreras de entrada y promover la personalización del entorno de aprendizaje.

![FLOW 2.png](assets/user-flows/FLOW%202.png)

**Flow 2: Interacción Comunitaria para Estudiantes**  
Dentro de la sección Comunidad de Level Up Journey, los estudiantes pueden explorar publicaciones compartidas por docentes y compañeros, fomentando un entorno colaborativo que apoya el aprendizaje social. Este flujo permite a los estudiantes visualizar posts relevantes sobre temas de programación, desafíos o consejos, y participar activamente mediante comentarios, lo que refuerza la comunidad educativa y facilita el intercambio de conocimientos. Esta funcionalidad está diseñada para mejorar la motivación y el compromiso estudiantil, integrándose con las épicas de retención y aprobación al promover interacciones que complementan las actividades de clase tradicionales.

![FLOW 3 - 1.png](assets/user-flows/FLOW%203%20-%201.png)

**Flow 3: Participación en Actividades de Juego (Parte 1)**  
Este flujo describe el proceso de unión a una actividad de juego (conocida como "class activity") en Level Up Journey, donde los estudiantes escanean un código QR o ingresan un código de invitación proporcionado por el docente. Tras unirse, configuran un nickname personalizado, pasan por pantallas de carga que preparan la experiencia, y esperan a que el docente inicie el juego. Este diseño gamificado busca aumentar la participación activa en cursos de programación iniciales, alineándose con los objetivos de la startup para combatir la deserción estudiantil mediante experiencias interactivas y competitivas.

![FLOW 3 -2.png](assets/user-flows/FLOW%203%20-2.png)

**Flow 3: Participación en Actividades de Juego (Parte 2)**  
Continuando el flujo, una vez iniciado el juego, los estudiantes responden preguntas de manera interactiva, recibiendo feedback inmediato sobre respuestas correctas o incorrectas, lo que refuerza el aprendizaje práctico en lenguajes como Python o JavaScript. Al finalizar, se visualiza un podio que destaca a los top 5 estudiantes, promoviendo un sentido de logro y competencia saludable. Esta mecánica gamificada integra elementos de refuerzo académico, apoyando la retención y aprobación al hacer el estudio más engaging y motivador.

![FLOW 3-3.png](assets/user-flows/FLOW%203-3.png)

**Flow 3: Participación en Actividades de Juego (Parte 3)**  
La conclusión del flujo muestra la transición a la pantalla final, donde los estudiantes ven los resultados del podio, fomentando la reflexión sobre el desempeño y el aprendizaje adquirido. Este enfoque visual y competitivo está optimizado para dispositivos móviles, asegurando accesibilidad y usabilidad, y contribuye directamente a los objetivos de bienestar social y educación de la startup al integrar diversión con contenido pedagógico.

![FLOW 4.png](assets/user-flows/FLOW%204.png)

**Flow 4: Creación y Gestión de Publicaciones por Docentes en Comunidad**  
Los docentes en Level Up Journey acceden a la Comunidad y seleccionan la opción de "Agregar" para crear nuevas publicaciones, que inicialmente entran en estado de borrador para permitir revisiones. Una vez listos, publican el post, haciéndolo visible para estudiantes y colegas. Posteriormente, pueden gestionar opciones como editar o eliminar, facilitando la moderación del contenido educativo. Este flujo empodera a los docentes como líderes en la plataforma, alineándose con la visión de la startup de fomentar equipos multidisciplinarios para soluciones digitales orientadas a la educación.

![FLOW 5.png](assets/user-flows/FLOW%205.png)

**Flow 5: Biblioteca y Creación de Juegos por Docentes**  
En la Biblioteca de Level Up Journey, los docentes visualizan todas sus actividades de juego (o "class activities"), incluyendo aquellas eliminadas para referencia histórica. Desde aquí, pueden crear nuevos juegos, agregando preguntas y seleccionando formatos como quiz o verdadero/falso, adaptados a temas de programación. Esta funcionalidad permite a los docentes diseñar contenido personalizado, apoyando la diferenciación pedagógica y contribuyendo a la mejora de tasas de aprobación mediante herramientas interactivas y flexibles.

![FLOW 6.png](assets/user-flows/FLOW%206.png)

**Flow 6: Hosting y Control de Juegos por Docentes**  
Los docentes inician el lanzamiento de un juego desde la Biblioteca, asumiendo el rol de anfitrión. Esperan a que los estudiantes se unan, inician la actividad, controlan el avance de preguntas y, al final, visualizan el podio de resultados. Este flujo otorga control total al docente, facilitando sesiones de clase dinámicas y evaluativas, y se integra con los objetivos de la startup para desarrollar soluciones que combinen educación con gamificación, promoviendo un aprendizaje efectivo y retención estudiantil.



#### 3.1.4.5. Mobile Applications Prototyping

El **prototipo interactivo** se desarrolló en **Figma**, conectando todas las pantallas y flujos de usuario.  

El prototipo permite evaluar la **fluidez del recorrido**, la **claridad visual de objetivos** y el **nivel de engagement percibido**.  
Durante la validación con estudiantes y docentes se observó:

- Navegación fluida y comprensión inmediata de íconos.
- Alta satisfacción visual y motivacional.


