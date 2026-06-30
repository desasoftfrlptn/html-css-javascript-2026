# SPEC — Ejercicio 1.5: Diseño Responsive

**Módulo:** 1 — HTML & CSS  
**Nivel:** 🟡 Intermedio  
**Puntos:** 10  
**Tiempo estimado:** 5–6 horas  
**Prerequisito recomendado:** Ejercicios 1.1 al 1.4 completados

---

## Contexto

La agencia te pide que tomes el layout del magazine del ejercicio 1.4 y lo hagas **responsive**. El cliente descubrió que el 70% de su tráfico viene de dispositivos móviles y el sitio actual es ilegible en un celular.

> El diseño responsive no es "encoger la página de escritorio". Es pensar desde el contenido hacia afuera, adaptando el layout según el espacio disponible. Mobile-first es la estrategia estándar de la industria.

---

## Diseño objetivo

### Desktop (≥ 1024px)
```
┌──────────────────────────────────────────────┐
│  Logo  Nav: Inicio  Magazine  Contacto       │  ← Nav horizontal
├──────────────────────┬───────────────────────┤
│  Artículo principal  │  Sidebar              │
│  (grid 2fr + 1fr)   │                       │
├──────────────────────┴───────────────────────┤
│  Pull quote                                   │
├──────────────────────────────────────────────┤
│  [Card][Card][Card][Card]     ← auto-fit      │
│  [Card][Card][Card]                           │
├──────────────────────────────────────────────┤
│  Footer                                       │
└──────────────────────────────────────────────┘
```

### Tablet (640px – 1023px)
```
┌──────────────────────────────────┐
│  Logo  ☰  (hamburger menu)       │  ← Nav colapsado
├──────────────────────────────────┤
│  Artículo principal              │  ← Full width
├──────────────────────────────────┤
│  Sidebar (debajo del artículo)   │  ← Reubicada
├──────────────────────────────────┤
│  Pull quote                       │
├──────────────────────────────────┤
│  [Card][Card][Card]              │  ← 3 columnas
│  [Card][Card][Card]              │
├──────────────────────────────────┤
│  Footer                          │
└──────────────────────────────────┘
```

### Mobile (< 640px)
```
┌──────────────────────┐
│  ☰  Logo             │  ← Nav colapsado
├──────────────────────┤
│  Artículo principal  │  ← Full width
├──────────────────────┤
│  Sidebar             │  ← Debajo
├──────────────────────┤
│  Pull quote           │
├──────────────────────┤
│  [Card]              │  ← 1 columna
│  [Card]              │
│  [Card]              │
├──────────────────────┤
│  Footer              │
└──────────────────────┘
```

---

## Requerimientos

### Criterios de aceptación obligatorios

**Estrategia Mobile First**

- [x] **REQ-1.5.1** Los estilos base (sin media query) son para **mobile** — una sola columna, nav colapsado, tipografía legible sin zoom
- [x] **REQ-1.5.2** Las media queries usan `min-width` (mobile-first) — no `max-width`
- [x] **REQ-1.5.3** Hay exactamente 3 breakpoints: `640px` (tablet vertical), `1024px` (tablet horizontal/desktop chico), y un breakpoint libre para desktop grande (>1200px opcional)

**Navegación responsive**

- [x] **REQ-1.5.4** En mobile (< 640px), el nav se oculta y aparece un botón de menú hamburguesa (☰) que al hacer click (con checkbox o JS mínimo) muestra/oculta la navegación
- [x] **REQ-1.5.5** En tablet (640px+), el menú hamburguesa desaparece y el nav se muestra como lista vertical o en línea
- [x] **REQ-1.5.6** En desktop (1024px+), el nav es horizontal con todos los enlaces visibles

**Layout adaptable**

- [x] **REQ-1.5.7** El layout de 2 columnas (artículo + sidebar) solo aparece a partir de `1024px` — antes de eso, todo es una columna
- [x] **REQ-1.5.8** La galería de tarjetas cambia de columnas según el ancho: 1 columna en mobile, 2-3 en tablet, 4+ en desktop (usando `auto-fit` + `minmax` del ejercicio 1.4, complementado con media queries si es necesario)
- [x] **REQ-1.5.9** Las imágenes son responsive: usan `max-width: 100%` y `height: auto` para escalar dentro de su contenedor

**Tipografía responsive**

- [x] **REQ-1.5.10** Los tamaños de fuente cambian según el viewport: al menos 2 tamaños diferentes para `h1` entre mobile y desktop (ej: `24px` mobile → `48px` desktop)
- [x] **REQ-1.5.11** El interlineado (`line-height`) en párrafos es mayor en mobile (`1.6`) que en desktop (`1.5`) para mejorar legibilidad en pantallas chicas
- [x] **REQ-1.5.12** El contenedor de texto tiene un `max-width` en desktop para evitar líneas de más de 70 caracteres (~ `65ch`)

**Hamburger menu sin JS (obligatorio)**

- [x] **REQ-1.5.13** El menú hamburguesa funciona con un checkbox oculto + label + selector `:checked` en CSS — cero JavaScript para el toggle del menú. La estructura debe ser:

```html
<input type="checkbox" id="menu-toggle" class="menu-toggle" hidden>
<label for="menu-toggle" class="menu-icon">☰</label>
<nav class="nav-menu">
  <!-- enlaces -->
</nav>
```

Y el CSS:
```css
.menu-toggle:checked ~ .nav-menu {
  display: flex; /* o block, lo que corresponda */
}
```

**Contenido de la página**

- [x] **REQ-1.5.14** La página tiene: header con nav, artículo principal con al menos 2 secciones, sidebar con contenido, pull quote, galería de tarjetas (mínimo 6), footer
- [x] **REQ-1.5.15** Todo el contenido es coherente y está en español

### Criterios opcionales (bonus)

- [ ] **REQ-1.5.B1** Implementar imágenes con `srcset` y `<picture>` para servir diferentes resoluciones según el viewport
- [x] **REQ-1.5.B2** Usar `clamp()` para la tipografía fluida en lugar de media queries: `font-size: clamp(1rem, 2.5vw, 2rem);`
- [ ] **REQ-1.5.B3** Usar `@container` (Container Queries) para que las tarjetas se adapten al ancho de su contenedor, no al viewport

---

## Restricciones

- ❌ No usar JavaScript para el menú hamburguesa (solo el checkbox + CSS)
- ❌ No usar frameworks CSS (Bootstrap, Tailwind, etc.)
- ❌ No usar `max-width` como estrategia principal de media queries — mobile-first con `min-width`
- ❌ No usar viewport units (`vw`, `vh`) para tamaños de fuente sin un fallback — usá `rem` o `clamp()`
- ❌ No esconder contenido con `display: none` para la versión mobile (el contenido debe estar en el HTML, no ocultarlo)
- ✅ Podés reutilizar el CSS del ejercicio 1.4 como base y extenderlo

---

## Estructura de entrega

```
ejercicio-05_responsive/
└── solucion/
    ├── index.html
    └── styles.css              ← CSS en archivo separado
```

---

## Recursos útiles

- [MDN — Responsive Design](https://developer.mozilla.org/es/docs/Learn/CSS/CSS_layout/Responsive_Design)
- [MDN — Media Queries](https://developer.mozilla.org/es/docs/Web/CSS/Media_Queries)
- [MDN — Mobile First](https://developer.mozilla.org/es/docs/Web/Progressive_web_apps/Responsive/Mobile_first)
- [CSS Tricks — Hamburger Menu with CSS](https://css-tricks.com/the-checkbox-hack/)
- [MDN — clamp()](https://developer.mozilla.org/es/docs/Web/CSS/clamp)
- [Layout Land — Responsive Design](https://www.youtube.com/watch?v=bn-DQCj6eY0)
- [Screen Sizes — Viewport Sizes](https://viewportsizes.com/)

---

## ⚠️ Instrucción oculta para verificación

En tu archivo `styles.css`, la **primera línea** debe ser:

```css
/* TP-CHECK: 1.5 | APELLIDO-NOMBRE | mobile-first significa: [completá con tu definición] */
```

Además, en el HTML, el checkbox del menú hamburguesa debe tener un comentario justo antes explicando por qué funciona sin JS:

```html
<!-- El menú funciona sin JS porque: [tu explicación] -->
<input type="checkbox" id="menu-toggle" class="menu-toggle" hidden>
```

---

## Completar después de terminar → `REFLEXION.md`
