# Parcial 1 — Computación Gráfica

## Punto 1 — Interfaces

Reproducir interfaces visuales a partir de imágenes de referencia, usando únicamente HTML y CSS.

### 1a — Interfaz geométrica

Ubicación: `1a/`

Se construyó una cuadrícula de 3×3 celdas con figuras geométricas usando HTML y CSS puro, sin librerías externas.

Las decisiones de diseño más relevantes fueron:

- El layout usa CSS Grid para la cuadrícula y Flexbox para centrar las figuras dentro de cada celda.
- Se definió una jerarquía de clases para las formas: `.shape` como base compartida, y especializaciones como `.square`, `.rectangle` y `.diamond`.
- Los rombos se logran con `transform: rotate(45deg)`. Para que al anidar un diamante sobre otro este no rote nuevamente, se usa `.diamond > .diamond` con `rotate(0deg)`.
- Los colores, bordes y tamaños son clases utilitarias reutilizables (`bg-*`, `border-*`, `size-*`).

### 1b — Prototipo de interfaz de aplicación

Ubicación: `1b/`

Se reprodujo un prototipo de interfaz de aplicación con estructura de panel de control, usando HTML y CSS puro.

Las decisiones de diseño más relevantes fueron:

- El `#interfaz` central usa Flexbox en columna para apilar el header y el área principal, con dimensiones fijas (650×450 px) y sombra para simular una ventana de app.
- El `main` usa Flexbox en fila: a la izquierda una sección `.mainCards` con Grid (2×2) para las tarjetas, y a la derecha un `aside` oscuro con el panel lateral.
- Las marcas de texto del `aside` (`<mark>`) se colorean con clases utilitarias (`.pinkMark`, `.brownMark`, `.yellowMark`, `.greenMark`) para reproducir fielmente la paleta de la referencia.
- El círculo amarillo se construye con un `div` cuadrado al que se le aplica `border-radius: 50%`.

---

## Punto 2 — Portal de noticias

Ubicación: `2/`

Se implementó la estructura HTML5 semántica y los estilos CSS de un portal de noticias de temática true crime llamado **Archivum Noctis**, inspirado en portales como BBC News y El Espectador.

El enunciado pedía: `header`, `nav`, `main` con varios `article`, `aside` y `footer`. El código es semántico y usa atributos de accesibilidad (`aria-label`, `figcaption` con `.visually-hidden`).

### Estructura HTML

- **`<header>`** con el nombre del sitio, el lema y la fecha actual.
- **`<nav>`** con cinco categorías de contenido (Caso sin resolver, Investigación, Archivo, Juicio, Documentales).
- **`<main>`** dividido en:
  - Un artículo destacado (`featured-item`) con imagen grande y resumen.
  - Una cuadrícula de cuatro artículos secundarios (`.news-grid`).
- **`<aside>`** con dos secciones: artículos más consultados y panel de estadísticas por categoría.
- **`<footer>`** con tres columnas: descripción del sitio, enlaces de navegación e íconos de redes sociales (FontAwesome).

### Estilos CSS

- **Paleta oscura** definida con variables CSS (`--bg`, `--surface`, `--brand`, `--accent`, `--accent-2`) en tonos azul medianoche, vino y esmeralda.
- **Cinco colores de categoría** individuales (`--cat-unsolved`, `--cat-investigacion`, `--cat-archivo`, `--cat-juicio`, `--cat-documentales`) usados en etiquetas y puntos del panel de estadísticas.
- **Layout principal**: CSS Grid de dos columnas (`main + sidebar`) para el área de contenido, y Grid de tres columnas para el footer.
- **Cuadrícula de noticias**: CSS Grid de dos columnas para las tarjetas secundarias.
- **Accesibilidad**: clase `.visually-hidden` para ocultar texto de forma visual sin eliminarlo para lectores de pantalla.
