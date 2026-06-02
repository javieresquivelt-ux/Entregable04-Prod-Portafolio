# Portafolio Personal — javieresquivel

Portafolio personal desarrollado como proyecto entregable del Magíster Desarrollo Fullstack de Conquer Block. Muestra las habilidades técnicas, proyectos realizados y un formulario de contacto.

## Objetivos

Este proyecto practica los siguientes conceptos:

- **HTML semántico** — Estructura clara con `<header>`, `<main>`, `<section>`, `<article>`, `<figure>`, `<footer>`, etc.
- **Arquitectura Sass 7-1** — Organización modular de estilos con `@use`/`@forward`, nunca `@import`.
- **BEM plano** — Nomenclatura de clases legible y escalable (`.hero__title`, `.projects__card`).
- **Mobile-First Responsive** — Diseño adaptable con breakpoints progresivos (768px / 1024px / 1200px / 1400px / 1700px).
- **Vite como bundler** — Entorno de desarrollo rápido con recarga en caliente y build optimizado.
- **Flexbox y Grid** — Layouts modernos sin frameworks CSS externos.
- **Accesibilidad** — Meta tags, atributos `aria-label`, `alt` descriptivos, navegación por teclado.

## Estructura de archivos

```
├── agent/                        # Habilidades técnicas del agente (skills)
│   ├── skill.md                  # Guía maestra (arquitectura, patrones, antipatrones)
│   ├── skill_header.md           # Framework para headers responsive
│   └── skill-responsive.md       # Framework responsive Mobile-First
├── public/                       # Archivos estáticos servidos en la raíz
│   ├── favicon.svg               # Favicon personalizado "JE"
│   └── icons.svg                 # Sprite de iconos SVG (no utilizado)
├── src/
│   ├── assets/
│   │   ├── icon/                 # Iconos SVG (redes sociales)
│   │   └── img/                  # Imágenes (foto de perfil, proyectos, decoraciones)
│   ├── scss/
│   │   ├── abstracts/            # Variables, mixins, funciones
│   │   │   ├── _index.scss       # @forward de abstracts
│   │   │   ├── _variables.scss   # Colores, tipografías
│   │   │   └── _mixins.scss      # Breakpoints mixins
│   │   ├── base/                 # Reset, tipografía, estilos base
│   │   │   ├── _index.scss       # @forward de base
│   │   │   ├── _reset.scss       # Normalización CSS
│   │   │   └── _typography.scss  # Estilos de texto y clases utilitarias
│   │   ├── layout/               # Estilos de secciones
│   │   │   ├── _index.scss       # @forward de layout
│   │   │   ├── _container.scss   # Contenedor fluido centrado
│   │   │   ├── _header.scss      # Cabecera con logo y redes sociales
│   │   │   ├── _hero.scss        # Presentación principal
│   │   │   ├── _skills.scss      # Habilidades técnicas
│   │   │   ├── _projects.scss    # Galería de proyectos
│   │   │   ├── _contact.scss     # Formulario de contacto
│   │   │   └── _footer.scss      # Pie de página
│   │   ├── components/           # Componentes reutilizables
│   │   │   └── _buttons.scss     # Botones y enlaces con subrayado
│   │   └── app.scss              # Archivo central con @use de todas las capas
│   └── main.js                   # JavaScript vanilla (mínimo)
├── template/                     # Archivos de diseño (referencia)
│   └── converted/                # PNG convertidos de los PDFs
├── index.html                    # Archivo HTML principal
├── README.md                     # Esta documentación
├── agents.md                     # Metodología de trabajo del agente
├── specs.md                      # Especificaciones del proyecto
├── memory.md                     # Memoria del proyecto (historial de cambios)
├── task.md                       # Plan de trabajo actual
├── init.sh                       # Script de validación de integridad
├── vite.config.js                # Configuración de Vite
├── package.json                  # Dependencias y scripts
└── .gitignore                    # Archivos ignorados por git
```

## Secciones del sitio

### Header
- Cabecera con posicionamiento absoluto flotante sobre el Hero.
- Logo textual "javieresquivel" a la izquierda.
- Redes sociales a la derecha (GitHub, LinkedIn, X, Frontend Mentor) con efecto hover que cambia el color del icono a verde acento mediante filtro CSS.
- **CSS:** Flexbox, `position: absolute`, transiciones en hover.

### Hero
- Presentación principal con foto de perfil, título ("Nice to meet you! I'm **Javier Esquivel**"), descripción profesional y CTA "CONTACT ME".
- Layout apilado en mobile y fila (imagen a la derecha, texto a la izquierda) en tablet/desktop mediante `flex-direction: row-reverse`.
- Decoraciones SVG absolutas (anillos concéntricos y óvalo cortado) posicionadas con `z-index`.
- Imagen con `aspect-ratio` y `object-fit: cover` para encuadre preciso.
- **CSS:** Flexbox, `flex-direction: row-reverse`, `position: relative/absolute`, pseudo-elemento `::after` para subrayado verde del CTA.

### Skills
- Lista semántica de 6 habilidades técnicas (HTML, CSS, JavaScript, Accesibilidad, React, Sass) con años de experiencia.
- Grid responsive: 1 columna en mobile, 2 en tablet, 3 en desktop.
- Línea divisoria horizontal superior e inferior (`border-top` / `border-bottom`).
- Decoración SVG absoluta (círculos) en la esquina inferior derecha.
- **CSS:** Grid, `grid-template-columns`, `border-top/bottom`, `position: absolute`.

### Projects
- Galería de 6 proyectos reales con imagen, título, tecnologías y enlaces.
- **Mobile/Tablet:** Botones "VIEW CODE" y "VIEW PROJECT" visibles debajo de cada tarjeta con subrayado verde.
- **Desktop:** Overlay oscuro con los mismos botones que aparece al hacer hover sobre la imagen.
- Layout grid: 1 columna en mobile, 2 en tablet y desktop.
- **CSS:** Grid, `position: relative/absolute`, overlay con `rgba()`, transiciones, pseudo-elemento `::after` para subrayado.

### Contact
- Formulario de contacto con campos: nombre, email, mensaje.
- Estilo minimalista: inputs con solo `border-bottom`, sin bordes laterales.
- Botón "SEND MESSAGE" con subrayado verde.
- Layout: columnas en mobile, fila (información + formulario) en desktop.
- Decoración SVG absoluta (círculos) en la esquina inferior izquierda del campo de mensaje, oculta en desktop-hd (1700px+).
- **CSS:** Flexbox, `border-bottom`, `position: relative/absolute`, `display: none` en breakpoint.

### Footer
- Separador horizontal, logo textual, redes sociales (mismas que el Header).
- Mismo diseño que el Header: logo + iconos sociales con hover verde.
- **CSS:** Flexbox, `border-top`, mismas clases de redes sociales.

## Tecnologías, Instalación y uso

### Stack
- **HTML5** — Estructura semántica
- **Sass/SCSS** — Preprocesador CSS con arquitectura 7-1
- **JavaScript vanilla** — Interactividad mínima
- **Vite** — Bundler y servidor de desarrollo

### Instalación

```bash
# Clonar el repositorio
git clone <url-del-repositorio>
cd dev_Portafolio

# Instalar dependencias
npm install
```

### Uso

```bash
# Entorno de desarrollo (servidor local con recarga en caliente)
npm run dev

# Build de producción
npm run build

# Vista previa del build
npm run preview
```

## Paleta de colores

| Color | Código | Propósito |
|---|---|---|
| Negro profundo | `#151515` | Fondo principal |
| Verde acento | `#4EE1A0` | Detalles interactivos, hover, subrayados |
| Gris superficie | `#242424` | Fondos de tarjetas, secciones alternas |
| Gris claro | `#d9d9d9` | Texto de cuerpo y descripciones |
| Blanco | `#FFFFFF` | Texto de títulos y headings |

## Tipografías

| Fuente | Uso | Pesos |
|---|---|---|
| **Space Grotesk** | Títulos (headings) y cuerpo general | 400 (Regular), 700 (Bold) |

### Tamaños destacados

| Elemento | Mobile | Tablet | Desktop |
|---|---|---|---|
| Título Hero | 2.2rem | 3.3rem | 5.5rem |
| Nombre destacado | Mismo que título | 4rem | 5.5rem |
| Descripción Hero | 1rem | 1.06rem | 1.125rem |
| Título secciones | 2.5rem | 4.5rem | — |
| Nombre de proyecto | 1.5rem | — | — |
| Logo (header/footer) | 1.5rem | — | — |

## Aprendizajes clave

- **Flexbox `row-reverse`:** Útil para cambiar el orden visual de elementos sin modificar el DOM (crítico para mantener la semántica HTML y la accesibilidad).
- **Mobile-First Responsive:** Partir del diseño mobile y escalar hacia arriba con `min-width` evita sobreescrituras innecesarias y obliga a priorizar el contenido esencial.
- **Overlay con hover en Projects:** Combinar `position: absolute` con `opacity` y `transition` permite crear efectos de superposición elegantes sin JavaScript.
- **Decoraciones SVG absolutas:** Posicionar imágenes decorativas con `position: absolute` y `pointer-events: none` evita que interfieran con la interacción del usuario.
- **Breakpoint personalizado `desktop-hd`:** Agregar un breakpoint extra (1700px+) permite ocultar decoraciones que en pantallas muy anchas pierden sentido visual.
- **Vite plugin `closeBundle`:** Útil para copiar archivos adicionales al directorio de build (`dist/`) sin necesidad de herramientas externas.
