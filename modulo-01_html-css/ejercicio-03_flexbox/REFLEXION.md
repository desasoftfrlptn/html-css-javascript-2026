# REFLEXION — Ejercicio 1.3: Layout con Flexbox

> **Instrucciones:** Reemplazá `[NÚMERO]` y `[NOMBRE]` con el número y nombre del ejercicio correspondiente. Completá este archivo DESPUÉS de terminar tu solución. Escribí con tus propias palabras.

---

## Sección 1 — Explicación de mi solución

*Describí en 150–250 palabras qué hace tu solución y cuáles fueron las decisiones principales que tomaste.*

> Armé la página de galería de proyectos de la agencia usando solo Flexbox, sin Grid ni librerías. La estructura tiene un `<header>` sticky con el logo y el nav en los extremos opuestos usando `justify-content: space-between`, un hero, una barra de filtros centrada y la galería de tarjetas.
>
> Para la galería usé `display: flex` con `flex-wrap: wrap` y un `gap` uniforme en el contenedor. Cada tarjeta ocupa aproximadamente un tercio del ancho con `flex: 0 0 calc((100% - 48px) / 3)`, donde resto los dos gaps de 24px para que las tres entren justas en la fila.
>
> La decisión que más me gustó fue cómo dejar el botón "Ver más" siempre pegado al fondo de la tarjeta: puse cada tarjeta en `flex-direction: column`, le di `flex: 1` al cuerpo y al botón le puse `margin-top: auto`. Así, sin importar si una descripción es más larga que otra, todos los botones quedan alineados abajo.
>
> Usé variables CSS (`--color-primario`, `--color-fondo`, `--color-texto`, etc.) para mantener la paleta coherente. Como bonus agregué una tarjeta destacada a ancho completo en la primera fila (`flex: 0 0 100%`), una animación de entrada con `@keyframes` y el efecto de elevación con `box-shadow` y `transform` al hacer hover.

---

## Sección 2 — Preguntas conceptuales

*Las preguntas conceptuales específicas de este ejercicio están en el `SPEC.md`. Respondé cada una aquí.*

### 2.1 — ¿Qué hace `flex-wrap: wrap` y por qué es clave en una galería de tarjetas?

> `flex-wrap: wrap` permite que los items pasen a una nueva línea cuando ya no entran en el ancho disponible, en vez de comprimirse en una sola fila. En la galería es clave porque las tarjetas tienen un ancho fijo de un tercio: sin `wrap` se aplastarían todas en una fila, pero con `wrap` cuando se llena el ancho del contenedor las siguientes saltan automáticamente a la fila de abajo. Eso es lo que hace que la galería se adapte sola al espacio.

### 2.2 — ¿Cómo lograste que el botón "Ver más" quede siempre pegado al fondo de la tarjeta?

> Puse cada tarjeta como un contenedor flex en dirección columna (`flex-direction: column`) y le di al cuerpo de la tarjeta `flex: 1` para que ocupe todo el alto sobrante. Después al botón le puse `margin-top: auto`, que empuja ese margen hasta absorber todo el espacio libre y deja el botón abajo. Así, aunque las descripciones tengan distinto largo, todos los botones quedan alineados al fondo.

### 2.3 — ¿Qué diferencia hay entre `justify-content` y `align-items` en Flexbox?

> `justify-content` alinea los items a lo largo del eje principal (el eje en el que se ordenan los items, horizontal si la dirección es `row`) y `align-items` los alinea en el eje cruzado (perpendicular al principal). Por ejemplo, en el header con `flex-direction: row` usé `justify-content: space-between` para separar logo y nav horizontalmente, y `align-items: center` para centrarlos verticalmente. Si cambiás la dirección a `column`, los ejes se invierten y cada propiedad pasa a actuar en el sentido contrario.

---

## Sección 3 — Decisiones técnicas

### 3.1 — ¿Qué fue lo más difícil de este ejercicio y cómo lo resolviste?

> Lo más difícil fue calcular el ancho de las tarjetas para que entraran tres por fila con el `gap`. Al principio puse `flex-basis: 33.33%` pero con el `gap` de 24px se desbordaban a la fila siguiente. Lo resolví usando `flex: 0 0 calc((100% - 48px) / 3)`, que descuenta los dos espacios de 24px antes de dividir por tres, y ahí entraron justas.

### 3.2 — ¿Qué cambiarías si tuvieras que hacerlo de nuevo?

> Para una galería de tarjetas con varias filas iguales, CSS Grid hubiera sido más cómodo porque no tendría que andar calculando el ancho con `calc()` a mano. Pero como la consigna pedía Flexbox sí o sí, lo dejé así. También haría los filtros funcionales con JavaScript en vez de que sean solo visuales.

### 3.3 — ¿Qué alternativas consideraste y por qué las descartaste?

> Consideré usar `flex: 1 1 300px` para que las tarjetas crecieran solas y llenaran el espacio, pero el problema es que la última fila incompleta queda con tarjetas estiradas de distinto ancho que las de arriba, y no me gustaba cómo se veía. Por eso preferí el ancho fijo de un tercio con `calc()`, que mantiene todas las tarjetas iguales aunque la última fila quede a la izquierda.

---

## Sección 4 — Declaración de uso de IA

```
[ ] Resolví el ejercicio completamente sin ayuda de IA
[x] Usé IA para entender algún concepto, pero escribí el código yo
[ ] Usé IA para generar un borrador que luego modifiqué y entendí
[ ] Usé IA extensamente y completé la reflexión para entender lo que hice
```

*Si usaste IA, describí brevemente cómo:*

> Usé IA para entender por qué las tarjetas se me desbordaban con el `gap` y cómo descontar los espacios con `calc()`. También para repasar cómo funciona `margin-top: auto` dentro de un flex column. El código lo escribí y fui probando en el navegador para ver que cada cambio hiciera lo que esperaba.

---

## Sección 5 — Autoevaluación

En una escala del 1 al 5, ¿cuánto entendés ahora el concepto central de este ejercicio?

```
[ ] 1 — Muy poco, necesito repasar
[ ] 2 — Entiendo lo básico
[ ] 3 — Lo entiendo bien
[x] 4 — Lo entiendo bien y puedo explicárselo a otro
[ ] 5 — Podría dar una clase sobre esto
```
