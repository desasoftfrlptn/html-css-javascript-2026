# REFLEXION — Ejercicio 1.5: Diseño Responsive

> **Instrucciones:** Reemplazá `[NÚMERO]` y `[NOMBRE]` con el número y nombre del ejercicio correspondiente. Completá este archivo DESPUÉS de terminar tu solución. Escribí con tus propias palabras.

---

## Sección 1 — Explicación de mi solución

*Describí en 150–250 palabras qué hace tu solución y cuáles fueron las decisiones principales que tomaste.*

> Partí del magazine del ejercicio 1.4 y lo hice responsive con estrategia mobile-first. Reutilicé el CSS del 1.4 como base (misma paleta y mismos componentes) y lo mejoré: los estilos base, sin media query, son ahora para celular (una sola columna, nav colapsado y tipografía legible), y desde ahí fui sumando mejoras para pantallas grandes con media queries de `min-width`.
>
> Usé tres breakpoints: en 640px el menú hamburguesa desaparece y el nav pasa a estar en línea; en 1024px recién aparece el layout de dos columnas con `grid-template-columns: 2fr 1fr` (artículo + sidebar), igual que en el 1.4; y en 1280px doy un poco más de aire y tarjetas más anchas.
>
> El menú hamburguesa lo hice sin JavaScript con el "checkbox hack": un checkbox oculto, un `<label>` asociado a su id, y el selector `.menu-toggle:checked ~ .nav-menu` que muestra el nav cuando el checkbox está marcado.
>
> Para la tipografía usé `clamp()` así el `h1` escala fluido entre mobile y desktop. Las imágenes son responsive con `max-width: 100%` y `height: auto`, la galería de tarjetas se adapta sola con `auto-fit` + `minmax`, el interlineado es 1.6 en mobile y 1.5 en desktop, y el texto tiene un `max-width` en `ch` para no pasar las ~70 caracteres por línea.

---

## Sección 2 — Preguntas conceptuales

*Las preguntas conceptuales específicas de este ejercicio están en el `SPEC.md`. Respondé cada una aquí.*

### 2.1 — ¿Qué significa "mobile-first" y por qué se usa `min-width` en lugar de `max-width`?

> Mobile-first significa escribir primero los estilos pensados para pantallas chicas y después ir sumando complejidad para pantallas grandes, en lugar de empezar por el desktop y achicar. Se usa `min-width` porque las media queries van agregando estilos a medida que la pantalla crece: el estilo base es el del celular y cada breakpoint de `min-width` "mejora" el layout para más ancho. Con `max-width` sería al revés (desktop-first), que va en contra de la estrategia.

### 2.2 — ¿Cómo funciona el menú hamburguesa sin JavaScript?

> Funciona con el "checkbox hack". Hay un `<input type="checkbox">` oculto que guarda el estado abierto/cerrado, y un `<label>` asociado a ese checkbox por su `id`: al tocar el label se marca o desmarca el checkbox. En el CSS, el selector `.menu-toggle:checked ~ .nav-menu` aplica `display: flex` al nav solo cuando el checkbox está marcado. Todo el toggle lo resuelve el navegador con CSS, sin una sola línea de JS.

### 2.3 — ¿Por qué `clamp()` puede reemplazar media queries para la tipografía?

> `clamp(min, ideal, max)` define un valor mínimo, uno preferido (normalmente en `vw`, que depende del ancho del viewport) y uno máximo. El navegador calcula el tamaño de fuente de forma fluida entre el mínimo y el máximo según el ancho de la pantalla, sin saltos bruscos. Así no necesito una media query para cada tamaño de `h1`: con una sola línea la fuente crece gradualmente, pero nunca se hace más chica ni más grande que los límites que puse.

---

## Sección 3 — Decisiones técnicas

### 3.1 — ¿Qué fue lo más difícil de este ejercicio y cómo lo resolviste?

> Lo que más me costó fue darle vuelta la cabeza al CSS del 1.4, que estaba pensado desktop-first, y reorganizarlo mobile-first. Tenía que decidir qué iba en los estilos base (celular) y qué dejaba dentro de cada media query. Lo resolví probando en el navegador, achicando y agrandando la ventana, hasta que cada breakpoint hacía lo que esperaba.

### 3.2 — ¿Qué cambiarías si tuvieras que hacerlo de nuevo?

> Le agregaría una animación al desplegar el menú hamburguesa para que no aparezca de golpe, y probaría el bonus de `srcset` / `<picture>` para servir imágenes más livianas en mobile. También revisaría mejor los tamaños de fuente en tablet, que es donde a veces quedan a mitad de camino.

### 3.3 — ¿Qué alternativas consideraste y por qué las descartaste?

> Para el menú consideré usar JavaScript con un `addEventListener` para el toggle, pero la consigna pedía cero JS, así que usé el checkbox hack con CSS puro. Para la tipografía pensé en hacer dos o tres media queries con tamaños fijos, pero preferí `clamp()` porque queda más fluido y necesita menos código.

---

## Sección 4 — Declaración de uso de IA

```
[ ] Resolví el ejercicio completamente sin ayuda de IA
[ ] Usé IA para entender algún concepto, pero escribí el código yo
[x] Usé IA para generar un borrador que luego modifiqué y entendí
[ ] Usé IA extensamente y completé la reflexión para entender lo que hice
```

*Si usaste IA, describí brevemente cómo:*

> Usé IA para armar un borrador de la versión mobile-first a partir del CSS del 1.4 y para entender bien el checkbox hack del menú. Después fui modificando el código (los breakpoints, los tamaños con `clamp()`) y lo probé en el navegador a distintos anchos para asegurarme de entender cómo se comportaba cada parte.

---

## Sección 5 — Autoevaluación

En una escala del 1 al 5, ¿cuánto entendés ahora el concepto central de este ejercicio?

```
[ ] 1 — Muy poco, necesito repasar
[ ] 2 — Entiendo lo básico
[x] 3 — Lo entiendo bien
[ ] 4 — Lo entiendo bien y puedo explicárselo a otro
[ ] 5 — Podría dar una clase sobre esto
```
