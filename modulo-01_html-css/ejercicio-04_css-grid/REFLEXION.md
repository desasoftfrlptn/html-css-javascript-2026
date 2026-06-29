# REFLEXION — Ejercicio 1.4: Layout con CSS Grid

> **Instrucciones:** Reemplazá `[NÚMERO]` y `[NOMBRE]` con el número y nombre del ejercicio correspondiente. Completá este archivo DESPUÉS de terminar tu solución. Escribí con tus propias palabras.

---

## Sección 1 — Explicación de mi solución

*Describí en 150–250 palabras qué hace tu solución y cuáles fueron las decisiones principales que tomaste.*

> Armé un magazine digital para un cliente editorial usando CSS Grid para el layout general. El `<body>` es el grid principal: con `grid-template-areas` dibujé el mapa de la página nombrando las regiones (header, main-content, sidebar, quote, cards, footer) y después asigné cada elemento a su área con `grid-area`. Las columnas son `2fr 1fr`, así el artículo principal ocupa el doble que la sidebar, y le di al área del artículo dos filas de alto.
>
> Para el header y los componentes internos (nav, newsletter, footer) usé Flexbox, porque Grid me sirve para el macro-layout y Flexbox para los micro-layouts de una sola dirección.
>
> La cita destacada rompe las dos columnas con `grid-column: 1 / -1` para ocupar el ancho completo. La galería de tarjetas usa `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))`, que adapta la cantidad de columnas al ancho disponible sin necesidad de media queries.
>
> Como decisión clave, en el HTML puse el `<aside>` antes del `<article>` pero por las áreas el artículo se ve a la izquierda: eso muestra que Grid separa el orden visual del orden del markup. Sumé bonus: una featured card que ocupa 2 columnas (`grid-column: span 2`) y `grid-auto-flow: dense` para rellenar los huecos. Usé variables CSS para mantener la paleta editorial coherente.

---

## Sección 2 — Preguntas conceptuales

*Las preguntas conceptuales específicas de este ejercicio están en el `SPEC.md`. Respondé cada una aquí.*

### 2.1 — ¿Cuál es la diferencia entre `auto-fit` y `auto-fill` en `repeat()`?

> Los dos crean tantas columnas como entren según el `minmax`. La diferencia aparece cuando sobra espacio: `auto-fill` deja columnas vacías reservadas (como fantasmas) y los items mantienen su ancho mínimo, mientras que `auto-fit` colapsa esas columnas vacías y estira los items existentes para que llenen todo el ancho. Usé `auto-fit` porque quería que las tarjetas se expandieran y no quedara espacio muerto a la derecha.

### 2.2 — ¿Cuándo conviene usar CSS Grid y cuándo Flexbox?

> Grid es bidimensional: maneja filas y columnas a la vez, ideal para el layout general de una página con áreas definidas como este magazine. Flexbox es unidimensional: distribuye elementos en una sola dirección (fila o columna), perfecto para micro-layouts como el nav del header, la barra de la newsletter o el contenido interno de una tarjeta. En la práctica los combiné: Grid para el esqueleto de la página y Flexbox para los componentes chicos adentro.

### 2.3 — ¿Cómo logra Grid separar el orden visual del orden del HTML?

> Porque con `grid-template-areas` (o con `grid-column` / `grid-row` / `order`) vos decidís en qué celda se ubica cada elemento, sin importar en qué orden esté escrito en el HTML. En mi solución puse el `<aside>` antes del `<article>` en el markup, pero como el artículo está asignado al área `main-content` (columna izquierda), visualmente aparece primero. El HTML mantiene un orden lógico/semántico y Grid se encarga del orden visual por separado.

---

## Sección 3 — Decisiones técnicas

### 3.1 — ¿Qué fue lo más difícil de este ejercicio y cómo lo resolviste?

> La verdad me costó bastante entender Grid en general. Venía de Flexbox del ejercicio anterior y me costaba pensar en filas y columnas a la vez en lugar de una sola dirección. Lo de `grid-template-areas`, que la cantidad de nombres de cada fila tenía que coincidir, y el `fr`, `span` y `minmax` me confundían. Me apoyé mucho en la IA para armarlo y después fui leyendo y probando para entender qué hacía cada parte.

### 3.2 — ¿Qué cambiarías si tuvieras que hacerlo de nuevo?

> Haría la sidebar sticky para que acompañe el scroll del artículo, y probaría el bonus de masonry de verdad en vez de simularlo con la tarjeta ancha. También agregaría más breakpoints intermedios para que la transición a una columna en mobile sea más gradual.

### 3.3 — ¿Qué alternativas consideraste y por qué las descartaste?

> Consideré hacer el layout principal con Flexbox y `flex-wrap` como en el ejercicio 1.3, pero la consigna pedía Grid y además tenía más sentido: el magazine es claramente bidimensional (artículo y sidebar lado a lado, con la cita y las tarjetas cruzando todo el ancho), y eso con Flexbox hubiera necesitado contenedores anidados y cálculos de ancho. Con `grid-template-areas` quedó mucho más declarativo y fácil de leer.

---

## Sección 4 — Declaración de uso de IA

```
[ ] Resolví el ejercicio completamente sin ayuda de IA
[ ] Usé IA para entender algún concepto, pero escribí el código yo
[ ] Usé IA para generar un borrador que luego modifiqué y entendí
[x] Usé IA extensamente y completé la reflexión para entender lo que hice
```

*Si usaste IA, describí brevemente cómo:*

> Usé IA bastante para hacer todo el ejercicio porque me costaba entender CSS Grid. La IA me armó el layout con `grid-template-areas`, la grilla de tarjetas con `auto-fit` y el resto del CSS, y yo después fui leyendo el código y completando esta reflexión para entender qué hacía cada parte y por qué funcionaba.

---

## Sección 5 — Autoevaluación

En una escala del 1 al 5, ¿cuánto entendés ahora el concepto central de este ejercicio?

```
[ ] 1 — Muy poco, necesito repasar
[x] 2 — Entiendo lo básico
[ ] 3 — Lo entiendo bien
[ ] 4 — Lo entiendo bien y puedo explicárselo a otro
[ ] 5 — Podría dar una clase sobre esto
```
