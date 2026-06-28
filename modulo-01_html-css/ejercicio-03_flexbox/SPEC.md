# SPEC — Ejercicio 1.3: Layout con Flexbox

**Módulo:** 1 — HTML & CSS  
**Nivel:** 🟡 Intermedio  
**Puntos:** 10  
**Tiempo estimado:** 3–4 horas  
**Prerequisito recomendado:** Ejercicios 1.1 y 1.2 completados

---

## Contexto

Continuás en la agencia de diseño. Ahora te piden construir la página de **galería de proyectos** del portfolio de la agencia. El diseñador te pasó el mockup y la consigna es clara: **solo Flexbox**, sin librerías externas como Bootstrap.

El cliente vio un sitio con una galería de tarjetas que se adaptan al espacio disponible y quiere algo similar.

---

## Diseño objetivo

La página debe verse así (describido textualmente, vos implementás el visual):

```
┌─────────────────────────────────────────┐
│  LOGO          Nav: Inicio Proyectos ... │  ← Header sticky
├─────────────────────────────────────────┤
│                                         │
│   Nuestros Proyectos                    │  ← Hero section
│   Subtitle text                         │
│                                         │
├─────────────────────────────────────────┤
│ [Filtro: Todos] [Web] [Mobile] [Branding]│  ← Barra de filtros (solo visual)
├─────────────────────────────────────────┤
│                                         │
│  ┌────────┐  ┌────────┐  ┌────────┐    │
│  │ img    │  │ img    │  │ img    │    │  ← Grid de tarjetas
│  │ Título │  │ Título │  │ Título │    │     (mínimo 6 tarjetas)
│  │ Desc   │  │ Desc   │  │ Desc   │    │
│  │ [Tags] │  │ [Tags] │  │ [Tags] │    │
│  └────────┘  └────────┘  └────────┘    │
│                                         │
│  ┌────────┐  ┌────────┐  ┌────────┐    │
│  │ img    │  │ img    │  │ img    │    │
│  └────────┘  └────────┘  └────────┘    │
│                                         │
├─────────────────────────────────────────┤
│  FOOTER                                 │
└─────────────────────────────────────────┘
```

---

## Requerimientos

### Criterios de aceptación obligatorios

**Layout general**
- [x] **REQ-1.3.1** El `<header>` usa Flexbox para alinear logo y nav en los extremos opuestos (`justify-content: space-between`)
- [x] **REQ-1.3.2** El `<header>` es `sticky` (se queda arriba al hacer scroll)
- [x] **REQ-1.3.3** El `<nav>` usa Flexbox para distribuir sus enlaces horizontalmente con un `gap` entre ellos

**Barra de filtros**
- [x] **REQ-1.3.4** Los botones de filtro están en una fila usando Flexbox, centrada horizontalmente en la página
- [x] **REQ-1.3.5** Los botones tienen un estado visual diferenciado (`:hover` y una clase `.activo` o `:focus-visible`)

**Galería de tarjetas**
- [x] **REQ-1.3.6** El contenedor de tarjetas usa `display: flex`, `flex-wrap: wrap` y un `gap` uniforme
- [x] **REQ-1.3.7** Cada tarjeta ocupa aproximadamente 1/3 del ancho del contenedor (`flex-basis` o `flex: 0 0 calc(...)`)
- [x] **REQ-1.3.8** Dentro de cada tarjeta, el contenido usa Flexbox en dirección columna con el espacio distribuido para que el botón/CTA siempre quede pegado al fondo de la tarjeta (`margin-top: auto` o `justify-content: space-between`)
- [x] **REQ-1.3.9** Hay mínimo 6 tarjetas con contenido diferente cada una
- [x] **REQ-1.3.10** Cada tarjeta tiene: imagen placeholder (`background-color` o `<img>` con placeholder URL), título, descripción corta, al menos 2 etiquetas/tags, y un botón o enlace de "Ver más"

**Estilo general**
- [x] **REQ-1.3.11** La página tiene un sistema de colores coherente usando al menos 3 variables CSS (`--color-primario`, `--color-fondo`, `--color-texto`)
- [x] **REQ-1.3.12** Las tarjetas tienen un efecto visual al hacer hover (elevación con `box-shadow`, transform, o similar)

### Criterios opcionales (bonus)

- [ ] **REQ-1.3.B1** El header cambia de apariencia al hacer scroll (usando JS o CSS `:has()` / scroll-driven animations)
- [x] **REQ-1.3.B2** Las tarjetas tienen una animación de entrada con `@keyframes`
- [x] **REQ-1.3.B3** Implementar un "featured card" que ocupe el ancho completo de la primera fila

---

## Restricciones

- ❌ No usar CSS Grid (eso es para el ejercicio 1.4)
- ❌ No usar librerías de UI (Bootstrap, Tailwind, etc.)
- ❌ No usar floats para layout
- ❌ No usar tablas para layout
- ✅ Podés usar Google Fonts o fuentes del sistema
- ✅ Podés usar placeholder images de [picsum.photos](https://picsum.photos/) o [placehold.co](https://placehold.co/)

---

## Estructura de entrega

```
ejercicio-03_flexbox/
└── solucion/
    ├── index.html
    └── styles.css          ← CSS en archivo separado (no inline, no en <style>)
```

---

## Recursos útiles

- [CSS Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/#es) — Juego interactivo para practicar
- [MDN — flex-wrap](https://developer.mozilla.org/es/docs/Web/CSS/flex-wrap)
- [MDN — CSS Custom Properties](https://developer.mozilla.org/es/docs/Web/CSS/Using_CSS_custom_properties)

---

## ⚠️ Instrucción oculta para verificación

En tu archivo `styles.css`, agregá este comentario al principio del archivo, **en la primera línea**:

```css
/* TP-CHECK: 1.3 | APELLIDO-NOMBRE | flex-wrap hace: [completá con tu definición] */
```

Reemplazá `[completá con tu definición]` con tu explicación de qué hace la propiedad `flex-wrap`.

---

## Completar después de terminar → `REFLEXION.md`
