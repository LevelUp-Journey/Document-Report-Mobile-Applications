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
- Consistencia revisiones regulares de implementació

  ![1c05e5c8-f479-4e5f-815c-d44a0104caae3](<./assets/Components/1c05e5c8-f479-4e5f-815c-d44a0104caae 3.svg>)
  ![7e4f1287-0466-43a9-b7ed-d1315976c28f](./assets/Components/7e4f1287-0466-43a9-b7ed-d1315976c28f.svg)
  ![b2d19ef2-33a7-469c-a13f-7fa3b16bcaec](./assets/Components/b2d19ef2-33a7-469c-a13f-7fa3b16bcaec.svg)
  ![Background](./assets/Components/Background.svg)
  ![Button10](<./assets/Components/Button 10.svg>)
  ![Button11](<./assets/Components/Button 11.svg>)
  ![Button12](<./assets/Components/Button 12.svg>)
  ![Button13](<./assets/Components/Button 13.svg>)
  ![Button14](<./assets/Components/Button 14.svg>)
  ![Button15](<./assets/Components/Button 15.svg>)
  ![Button16](<./assets/Components/Button 16.svg>)
  ![Button4](<./assets/Components/Button4.svg>)
  ![CardRecent](<./assets/Components/Card Recent.svg>)
  ![Component1](<./assets/Components/Component 1.svg>)
  ![Content](./assets/Components/Content.svg)
  ![Frame1321317519](<./assets/Components/Frame 1321317519.svg>)
  ![Frame1321317520](<./assets/Components/Frame 1321317520.svg>)
  ![Frame1321317521](<./assets/Components/Frame 1321317521.svg>)
  ![Frame1321317522](<./assets/Components/Frame 1321317522.svg>)
  ![Frame1321317523](<./assets/Components/Frame 1321317523.svg>)
  ![Group60](<./assets/Components/Group 60.svg>)
  ![State-layer-1](./assets/Components/State-layer-1.svg)
  ![state-layer](./assets/Components/state-layer.svg)
  ![State-layer](./assets/Components/State-layer.svg)

### 3.1.2. Information Architecture

#### 3.1.2.1. Organization Systems



#### 3.1.2.2. Labelling Systems

- Landing Page

El sistema de etiquetado se implementa mediante atributos `data-i18n` que permiten la internacionalización dinámica del contenido. Cada elemento textual incluye un identificador único que referencia las claves en los archivos JSON de traducción (`es.json`, `en.json`). El sistema se activa mediante JavaScript que escanea el DOM en busca de elementos con `data-i18n`, recupera el valor correspondiente según el idioma seleccionado y actualiza el contenido en tiempo real. Los identificadores siguen una estructura jerárquica (ejemplo: `section1.title`, `section2.card1.description`) que facilita la organización y mantenimiento de las traducciones. Para elementos de formulario, se emplean atributos `placeholder` dinámicos que se actualizan junto con el cambio de idioma. Los botones incluyen atributos `aria-label` para accesibilidad, proporcionando descripciones alternativas en el idioma activo. El sistema de etiquetado asegura consistencia visual mediante clases CSS que mantienen el estilo tipográfico independientemente del contenido dinámico.

- Aplicación Móvil

#### 3.1.2.3. SEO Tags and Meta Tags

- Landing Page

Los metadatos SEO se configuran en el elemento `<head>` del documento HTML principal. El título de página se establece como "LevelUp Journey" mediante la etiqueta `<title>`, optimizado para motores de búsqueda con palabras clave relevantes al producto educativo. El atributo `lang` se define como "es" por defecto, cambiando dinámicamente según la selección de idioma del usuario. El favicon se implementa mediante `<link rel="icon">` apuntando a `/level-up-cat-happy.svg`, proporcionando identificación visual consistente en pestañas del navegador. La etiqueta `<meta name="viewport">` con `content="width=device-width"` asegura renderizado responsivo en dispositivos móviles. El generador de contenido se identifica mediante `<meta name="generator">` con el valor de `Astro.generator`, facilitando el rastreo técnico. La codificación de caracteres se establece como UTF-8 mediante `<meta charset="utf-8">`, garantizando compatibilidad con caracteres especiales en múltiples idiomas. No se incluyen meta descriptions explícitas, lo que representa una oportunidad de optimización futura para mejorar el posicionamiento en resultados de búsqueda.

- Aplicación Móvil

#### 3.1.2.4. Searching Systems

No se implementara sajnasjbsajnklas

#### 3.1.2.5. Navigation Systems

- Landing Page

El sistema de navegación se estructura mediante un header fijo que permanece visible durante el scroll, implementado con `position: fixed` y `z-index: 50`. El componente principal incluye un enlace de logo que redirige a la página inicial, acompañado de controles de navegación posicionados a la derecha. El selector de idioma se presenta como un menú desplegable activado por clic, mostrando opciones para español ("ES") e inglés ("EN") con estilos que incluyen backdrop-blur y transiciones suaves. El botón de cuenta de usuario se representa mediante un icono SVG con atributo `aria-label` para accesibilidad. Al hacer scroll, el header adquiere una clase `scrolled` que aplica un fondo semi-transparente (`rgba(23, 23, 23, 0.95)`) y efecto de desenfoque (`backdrop-filter: blur(12px)`), mejorando la legibilidad sobre contenido variable. La navegación interna se maneja mediante scroll suave a secciones ancladas, aunque no se implementan enlaces de menú tradicionales. El footer proporciona navegación secundaria con enlaces institucionales organizados en estructura de grid, manteniendo consistencia con la paleta de colores del sistema de diseño.

- Aplicación Móvil

### 3.1.3. Landing Page UI Design

#### 3.1.3.1. Landing Page Wireframe

#### 3.1.3.2. Landing Page Mock-up

### 3.1.4. Mobile Applications UX/UI Design

#### 3.1.4.1. Mobile Applications Wireframes



#### 3.1.4.2. Mobile Applications Wireflow Diagrams

#### 3.1.4.3. Mobile Applications Mock-ups

#### 3.1.4.4. Mobile Applications User Flow Diagrams

#### 3.1.4.5. Mobile Applications Prototyping