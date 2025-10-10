# Capítulo III: Solution UI/UX Design

## 3.1. Product design

### 3.1.1. Style Guidelines

Esta sección define la identidad visual y los patrones de diseño que aseguran consistencia en la landing page de Level Up Journey. Se estructura en torno a los principios de tipografía, color, iconografía, componentes interactivos y lineamientos gráficos generales, implementados mediante Tailwind CSS y Astro framework.

3.1.1.1. Tipografía

a. Tipografía para Landing Page

La landing page utiliza un sistema tipográfico basado en Tailwind CSS con las siguientes especificaciones:

- **Fuentes primarias:** Sistema de fuentes web por defecto de Tailwind (inter, sans-serif)
- **Jerarquía tipográfica:**
  - Títulos principales (H1): `text-5xl` a `text-7xl` (48px-72px), `font-bold` (700)
  - Subtítulos (H2): `text-3xl` a `text-5xl` (30px-48px), `font-bold` (700)
  - Texto de párrafo: `text-base` a `text-xl` (16px-20px), `font-normal` (400)
  - Texto secundario: `text-sm` (14px), `text-gray-400`
- **Espaciado y legibilidad:**
  - Interlineado: `leading-relaxed` (1.625) para párrafos
  - Márgenes: Sistema de espaciado consistente (`mb-4`, `mb-6`, `mb-12`)
- **Pesos tipográficos:** `font-normal` (400), `font-semibold` (600), `font-bold` (700)

b. Tipografía para Aplicación Móvil

Aunque la implementación actual se centra en la landing page web, se contemplan las siguientes consideraciones para futura adaptación móvil:

- **Fuentes optimizadas:** SF Pro Display o Roboto para mejor legibilidad en pantallas pequeñas
- **Escala responsiva:** Tamaños adaptativos mediante breakpoints de Tailwind (`sm:`, `md:`, `lg:`)
- **Contraste garantizado:** Texto blanco sobre fondos oscuros (`neutral-950`) con ratio de contraste mínimo 4.5:1
- **Tamaño mínimo:** 14px para texto de lectura, 16px para elementos interactivos

3.1.1.2. Guía de Color (Color Guide)

a. Paleta de colores para Landing Page

La paleta de colores se basa en un esquema oscuro con acentos rojos:

- **Color primario (Primary):** `red-600` (#DC2626) - Botones principales y elementos de acción
- **Color secundario (Secondary):** `neutral-700` (#404040) - Bordes y elementos decorativos
- **Color de fondo principal:** `neutral-950` (#0A0A0A) - Fondo general de la página
- **Color de fondo secundario:** `neutral-900` (#171717) - Tarjetas, formularios y secciones destacadas
- **Color de texto primario:** `white` (#FFFFFF) - Títulos y texto principal
- **Color de texto secundario:** `gray-400` (#9CA3AF) - Descripciones y texto complementario
- **Color de acento:** `red-600` (#DC2626) - Elementos interactivos y llamadas a acción

b. Paleta de colores para Aplicación Móvil

Para futuras implementaciones móviles, se propone:

- **Adaptación Material Design:** Colores equivalentes en formato ARGB para Android
- **Modo oscuro nativo:** Aprovechamiento del sistema de colores del dispositivo
- **Colores de estado:** Success (`green-500`), Warning (`yellow-500`), Error (`red-500`)

c. Reglas de contraste y accesibilidad

- **Ratio de contraste:** Mínimo 4.5:1 para texto normal, 3:1 para texto grande (WCAG AA)
- **Texto sobre fondo oscuro:** Blanco (#FFFFFF) sobre neutral-950 (#0A0A0A) = ratio 15.8:1 ✓
- **Texto secundario:** gray-400 (#9CA3AF) sobre neutral-950 = ratio 5.2:1 ✓
- **Elementos interactivos:** Asegurar foco visible con outline o border

d. Estados interactivos (hover, focus, active, disabled)

- **Hover:** `hover:bg-red-700` para botones, `hover:border-gray-600` para tarjetas
- **Focus:** `focus:ring-2 focus:ring-red-600` con outline visible
- **Active:** `active:scale-95` para feedback táctil simulado
- **Disabled:** `opacity-50 cursor-not-allowed` con pointer-events deshabilitados

Logotipo y Elementos de Marca

a. Versiones y proporciones del logotipo

- **Logotipo principal:** Imagen SVG `level-up-cat-happy.svg` como favicon

![level-up-cat-happy](./assets/Style-Guidelines/level-up-cat-happy.svg)

- **Título de marca:** "Level Up Journey" con fuente bold y jerarquía visual
- **Proporciones:** Logotipo circular con relación de aspecto 1:1

b. Área de seguridad y restricciones de uso

- **Área protegida:** Mínimo 8px de espacio alrededor del logotipo
- **Restricciones:** No distorsionar proporciones, mantener colores originales
- **Uso en fondos:** Optimizado para fondos oscuros (neutral-950)

c. Iconografía institucional y favicons

- **Iconos de sección:** SVG optimizados en `/assets/section2/icons/`
  - `code.svg` - Editor de código
  ![code](./assets/Style-Guidelines/code.svg)
  - `calendar-check.svg` - Retos semanales
  ![calendar-check](./assets/Style-Guidelines/calendar-check.svg)
  - `hammer.svg` - Retroalimentación
  ![hammer](./assets/Style-Guidelines/hammer.svg)
- **Iconos de navegación:** `i18n.svg`, `account.svg` en `/assets/header/`
![i18n](./assets/Style-Guidelines/i18n.svg)
![account](./assets/Style-Guidelines/account.svg)

- **Favicon:** `level-up-cat-happy.svg` (versión optimizada 32x32px)
![level-up-cat-happy](./assets/Style-Guidelines/level-up-cat-happy.svg)

Imágenes e Ilustraciones

. Estilo y tratamiento fotográfico

- **Estilo visual:** Fotografía oscura con overlays para mejorar legibilidad
- **Tratamiento:** Overlay negro con opacidad 50% sobre imágenes de fondo

b. Ilustraciones y gráficos vectoriales

- **Iconos de lenguajes:** SVG en `/assets/section1/programming-languages/`
  - C++, Java, JavaScript, Python

![c++](./assets/Style-Guidelines/c++.svg)
![java](./assets/Style-Guidelines/java.svg)
![javascript](./assets/Style-Guidelines/javascript.svg)
![python](./assets/Style-Guidelines/python.svg)

- **Gráficos vectoriales:** Optimizados para escalabilidad

c.  resolución y formato

- **Formato preferido:** SVG para iconos, WebP/PNG para fotografías
- **Resolución:** Mínimo 2x para retina displays
- **Compresión:** Optimización automática vía Astro

d. Lineamientos específicos para web y móvil

- **Web:** Imágenes de fondo full-width con `bg-cover`
- **Móvil:** Adaptación responsiva con `bg-center` y overlays ajustados

3.1.1.5. Botones y Componentes Interactivos

a. Tipos de botones (Primario, Secundario, Outline, Ghost, FAB)

- **Primario:** `bg-red-600 hover:bg-red-700 text-white` - Llamadas a acción principales
- **Secundario:** `bg-neutral-900 border border-neutral-700` - Acciones secundarias
- **Outline:** `border border-red-600 text-red-600 hover:bg-red-600` - Acciones alternativas
- **Ghost:** `text-white hover:bg-white/10` - Acciones sutiles

b. Estados de interacción y retroalimentación visual

- **Hover:** Cambio de color de fondo con transición `duration-200`
- **Focus:** Ring visible `focus:ring-2 focus:ring-red-600`
- **Active:** Efecto de escala `active:scale-95`
- **Loading:** Opacidad reducida durante procesos asíncronos

c. Dimensiones y márgenes táctiles mínimos

- **Botones principales:** `px-8 py-4` (128px x 64px)
- **Botones pequeños:** `px-6 py-3` (96px x 48px)
- **Margen táctil:** Mínimo 44px de altura para accesibilidad móvil

d. Iconografía asociada a botones

- **Botón de idioma:** `i18n.svg` (24x24px)
- **Botón de cuenta:** `account.svg` (28x28px)
- **Botones de sección:** Iconos contextuales en tarjetas

e. Componentes derivados (Inputs, Cards, Modals, Tabs, Snackbars, Progress Indicators)

- **Inputs:** `bg-neutral-900/80 border border-neutral-700 rounded-lg` con placeholder
- **Cards:** `.card` class con `border border-gray-700 rounded-lg p-6 lg:p-8`
- **Modals:** Futura implementación con overlays oscuros
- **Tabs:** Sistema de navegación horizontal
- **Snackbars:** Notificaciones temporales (planeadas)
- **Progress Indicators:** Barras de progreso para carga

Elementos Específicos por Tipo de Producto

a. Layout y sistema de cuadrícula

- **Sistema de cuadrícula:** 12 columnas con Tailwind Grid
- **Breakpoints:** `sm:` (640px), `md:` (768px), `lg:` (1024px)
- **Container:** `max-w-7xl mx-auto` para contenido centrado

b. Navegación y estructura

- **Header fijo:** `fixed top-0` con backdrop-blur al scroll
- **Secciones:** `min-h-screen` para hero, `py-16 lg:py-20` para secciones
- **Footer:** Enlaces organizados en grid

c. Comportamientos y microinteracciones

- **Scroll effects:** Header con `scrolled` class y blur effect
- **Hover animations:** `transition-colors duration-200`
- **Floating elements:** Componente `FloatingLanguages` con física de burbujas

d. Adaptabilidad entre web y móvil

- **Responsive images:** `w-full` con aspect ratios
- **Flexible layouts:** `grid-cols-1 md:grid-cols-2 lg:grid-cols-3`
- **Touch targets:** Mínimo 44px para elementos interactivos

Consistencia y Adaptabilidad del Sistema de Diseño

a. Coherencia entre plataformas

- **Variables CSS:** Sistema de design tokens en `:root`
- **Clases reutilizables:** `.section`, `.container-custom`, `.card`
- **Naming convention:** BEM-like con Tailwind utilities

b. Librería de componentes reutilizables

- **Componentes base:** Header, Footer, Section components

- **Utilidades:** Classes globales en `global.css`

- **Modularidad:** Separación por funcionalidad

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

c. Versionado y documentación del Design System

- **Documentación:** Este documento como guía de estilos
- **Versionado:** Control de versiones con Git
- **Consistencia:** Revisiones regulares de implementación

#### 3.1.1.1. General Style Guidelines

### 3.1.2. Information Architecture

#### 3.1.2.1. Organization Systems

#### 3.1.2.2. Labelling Systems

#### 3.1.2.3. SEO Tags and Meta Tags

#### 3.1.2.4. Searching Systems

#### 3.1.2.5. Navigation Systems

### 3.1.3. Landing Page UI Design

#### 3.1.3.1. Landing Page Wireframe

#### 3.1.3.2. Landing Page Mock-up

### 3.1.4. Mobile Applications UX/UI Design

#### 3.1.4.1. Mobile Applications Wireframes



#### 3.1.4.2. Mobile Applications Wireflow Diagrams

#### 3.1.4.3. Mobile Applications Mock-ups

#### 3.1.4.4. Mobile Applications User Flow Diagrams

#### 3.1.4.5. Mobile Applications Prototyping