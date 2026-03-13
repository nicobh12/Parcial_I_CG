# Parcial 1 — Computación Gráfica

## Punto 1 — Interfaz geométrica

Reproducir una interfaz visual a partir de una imagen de referencia, usando únicamente HTML y CSS.

### 1a — Figura geométrica estática

Ubicación: `1a/`

Se construyó una cuadrícula de 3×3 celdas con figuras geométricas usando HTML y CSS puro, sin librerías externas.

Las decisiones de diseño más relevantes fueron:

- El layout usa CSS Grid para la cuadrícula y Flexbox para centrar las figuras dentro de cada celda.
- Se definió una jerarquía de clases para las formas: `.shape` como base compartida, y especializaciones como `.square`, `.rectangle` y `.diamond`.
- Los rombos se logran con `transform: rotate(45deg)`. Para que al anidar un diamante sobre otro este no rote nuevamente, se usa `.diamond > .diamond` con `rotate(0deg)`.
- Los colores, bordes y tamaños son clases utilitarias reutilizables (`bg-*`, `border-*`, `size-*`).
