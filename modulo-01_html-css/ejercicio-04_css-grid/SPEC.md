# SPEC — Ejercicio 1.4: Layout con CSS Grid

**Módulo:** 1 — HTML & CSS  
**Nivel:** 🟡 Intermedio  
**Puntos:** 10  
**Tiempo estimado:** 4–5 horas  
**Prerequisito recomendado:** Ejercicios 1.1, 1.2 y 1.3 completados

---

## Contexto

La agencia consiguió un cliente editorial que quiere un **magazine digital** con un diseño de grilla complejo: artículo principal destacado, artículos secundarios, sidebar con contenido relacionado, y una sección de tarjetas. El diseñador entregó el layout con áreas bien definidas.

> Mientras Flexbox es unidimensional (fila O columna), CSS Grid es bidimensional (filas Y columnas a la vez). Elegir la herramienta correcta para cada layout es parte del oficio.

---

## Diseño objetivo

```
┌──────────────────────────────────────────────────┐
│  LOGO                 Nav: Inicio Magazine ...   │  ← Header (sticky, flexbox)
├──────────────────────┬───────────────────────────┤
│                      │                           │
│   Artículo Principal │   Sidebar                 │  ← Grid de 2 columnas
│   (ocupa 2 filas)    │   • Artículos recientes   │     (aside)
│                      │   • Newsletter form       │
│   ┌──────────────┐   │   • Redes sociales        │
│   │   imagen     │   │                           │
│   └──────────────┘   │                           │
│                      │                           │
├──────────────────────┴───────────────────────────┤
│   "La frase destacada de la semana"               │  ← Pull quote (full width)
├──────────────────────────────────────────────────┤
│                                                    │
│  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐         │
│  │ Card │  │ Card │  │ Card │  │ Card │         │  ← Grid de tarjetas
│  └──────┘  └──────┘  └──────┘  └──────┘         │     auto-fit
│  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐         │
│  │ Card │  │ Card │  │ Card │  │ Card │         │
│  └──────┘  └──────┘  └──────┘  └──────┘         │
│                                                    │
├──────────────────────────────────────────────────┤
│  FOOTER                                          │
└──────────────────────────────────────────────────┘
```

---

## Requerimientos

### Criterios de aceptación obligatorios

**Layout general con Grid**

- [x] **REQ-1.4.1** El layout general de la página usa `display: grid` en el `<body>` o contenedor principal, con `grid-template-areas` nombrando las regiones: `header`, `main-content`, `sidebar`, `quote`, `cards`, `footer`
- [x] **REQ-1.4.2** El `header` usa Flexbox (está bien mezclar — Grid para macro-layout, Flexbox para micro-layout), sticky como en el ejercicio 1.3

**Grid principal (artículo + sidebar)**

- [x] **REQ-1.4.3** El contenido principal (`<article>`) y la barra lateral (`<aside>`) están en un grid de 2 columnas usando `grid-template-columns: 2fr 1fr` (el artículo ocupa el doble que la sidebar)
- [x] **REQ-1.4.4** El artículo principal ocupa 2 filas de altura con `grid-row: span 2` (o usando áreas explícitas)
- [x] **REQ-1.4.5** El `gap` entre filas y columnas es uniforme usando `gap` (no margin en los hijos)

**Pull quote (cita destacada)**

- [x] **REQ-1.4.6** La cita destacada ocupa el ancho completo, rompiendo las 2 columnas — implementado con `grid-column: 1 / -1` o asignándola a un área que cruce todo el ancho

**Galería de tarjetas con auto-fit**

- [x] **REQ-1.4.7** Las tarjetas de artículos secundarios están en un grid usando `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))` — esto hace que las tarjetas se adapten automáticamente al ancho disponible SIN media queries
- [x] **REQ-1.4.8** Hay mínimo 6 tarjetas con contenido diferente
- [x] **REQ-1.4.9** Cada tarjeta tiene: imagen, título, fecha, categoría/tag, extracto de texto, y enlace "Leer más"

**Uso de grid features**

- [x] **REQ-1.4.10** Hay al menos un caso donde un elemento ocupa un área más grande que una celda usando `grid-column` o `grid-row` con span (además del artículo principal)
- [x] **REQ-1.4.11** El orden visual de los elementos NO depende del orden en el HTML — usá `order` de grid o la posición por áreas para demostrar que grid separa el orden visual del markup

**Estilo general**

- [x] **REQ-1.4.12** La página tiene un sistema de colores coherente con al menos 3 variables CSS (como en el ejercicio 1.3)
- [x] **REQ-1.4.13** La sidebar incluye: lista de artículos recientes, un formulario de newsletter chico (email + botón), y enlaces a redes sociales

### Criterios opcionales (bonus)

- [ ] **REQ-1.4.B1** Implementar un layout de "masonry" aproximado usando `grid-template-rows: masonry` (verificar soporte en navegador) o una alternativa con filas explícitas de diferentes alturas
- [x] **REQ-1.4.B2** Usar `grid-auto-flow: dense` para llenar espacios vacíos automáticamente en la galería de tarjetas
- [x] **REQ-1.4.B3** Implementar un "featured card" que ocupe 2 columnas en la grilla de tarjetas

---

## Restricciones

- ❌ No usar Flexbox para el layout principal de la página (solo para micro-layouts como nav, contenido interno de tarjetas)
- ❌ No usar floats para layout
- ❌ No usar tablas para layout
- ❌ No usar media queries para hacer responsive el grid de tarjetas — usar `auto-fit` + `minmax`
- ✅ Podés (y debés) usar Flexbox para el header nav y componentes internos

---

## Estructura de entrega

```
ejercicio-04_css-grid/
└── solucion/
    ├── index.html
    └── styles.css              ← CSS en archivo separado
```

---

## Recursos útiles

- [CSS Tricks — A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Grid Garden](https://cssgridgarden.com/#es) — Juego interactivo para practicar
- [MDN — CSS Grid Layout](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Grid_Layout)
- [MDN — grid-template-areas](https://developer.mozilla.org/es/docs/Web/CSS/grid-template-areas)
- [MDN — auto-fit / auto-fill](https://developer.mozilla.org/es/docs/Web/CSS/repeat#auto-fit_vs_auto-fill)
- [Layout Land — CSS Grid videos](https://www.youtube.com/playlist?list=PLUS3uVC08YaqGbzYHY_d2T9nS3z01FOaf)

---

## ⚠️ Instrucción oculta para verificación

En tu archivo `styles.css`, la **primera línea** debe ser:

```css
/* TP-CHECK: 1.4 | APELLIDO-NOMBRE | grid-template-areas hace: [completá con tu definición] */
```

Además, en el HTML, en el contenedor que tiene `display: grid`, agregá un comentario justo antes de la apertura del contenedor explicando la diferencia entre `auto-fit` y `auto-fill`:

```html
<!-- auto-fit vs auto-fill: [tu explicación] -->
<div class="grid-contenedor">
```

---

## Completar después de terminar → `REFLEXION.md`
