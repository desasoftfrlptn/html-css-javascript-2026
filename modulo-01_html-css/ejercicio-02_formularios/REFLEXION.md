# REFLEXION — Ejercicio 1.2: Formularios Accesibles

> **Instrucciones:** Reemplazá `[NÚMERO]` y `[NOMBRE]` con el número y nombre del ejercicio correspondiente. Completá este archivo DESPUÉS de terminar tu solución. Escribí con tus propias palabras.

---

## Sección 1 — Explicación de mi solución

*Describí en 150–250 palabras qué hace tu solución y cuáles fueron las decisiones principales que tomaste.*

> Hice una página de contacto con un formulario accesible para una agencia de diseño. La estructura la dividí en dos `<fieldset>`: uno para los datos personales (nombre, email, teléfono) y otro para los detalles del mensaje (motivo, tipo de consulta, mensaje y archivo adjunto). Cada campo tiene su `<label>` vinculado explícitamente con `for` e `id`.
>
> Para la accesibilidad usé `aria-required="true"` en los campos obligatorios junto con el atributo nativo `required`, y marqué los campos con un asterisco rojo para el indicador visual. Los mensajes de error los conecté con `aria-describedby` para que los lectores de pantalla los anuncien cuando el campo es inválido.
>
> Para los estados visuales usé `:user-invalid` y `:user-valid` en lugar de `:invalid` y `:valid` porque así el error solo aparece después de que el usuario interactúa con el campo, no apenas carga la página. El foco lo hice visible con un outline azul contrastante siguiendo WCAG 2.4.7.
>
> En lugar de un `<select>` tradicional usé `<datalist>` (bonus B1) que permite escribir o elegir de una lista, y no necesité JavaScript porque toda la validación la hace el navegador con los atributos HTML5 nativos como `required`, `type="email"` y `pattern`.

---

## Sección 2 — Preguntas conceptuales

*Las preguntas conceptuales específicas de este ejercicio están en el `SPEC.md`. Respondé cada una aquí.*

### 2.1 — ¿Por qué es importante el atributo `for` en el `<label>`? ¿Qué pasa si no lo ponés?

> El `for` vincula el label con el input que tiene el mismo `id`. Si no lo ponés, el lector de pantalla no sabe qué texto corresponde a qué campo — el usuario escucha "campo de texto vacío" sin saber qué tiene que escribir. Además, sin `for`, hacer clic en el label no enfoca el input, lo que perjudica a usuarios con dificultades motrices que necesitan zonas de clic más grandes.

### 2.2 — ¿Cuál es la diferencia entre `aria-required` y el atributo `required` nativo de HTML5?

> `required` es HTML5 puro: el navegador lo usa para validar y bloquear el envío si el campo está vacío. `aria-required` es ARIA y solo sirve para comunicarle a los lectores de pantalla que el campo es obligatorio — no afecta la validación del navegador para nada. Se usan juntos porque algunos lectores de pantalla antiguos no leen el `required` nativo, y así cubrís los dos casos.

### 2.3 — ¿Por qué usamos `:user-invalid` en lugar de `:invalid` para mostrar errores visuales?

> Porque `:invalid` se aplica apenas carga la página, entonces todos los campos obligatorios aparecen en rojo desde el principio aunque el usuario todavía no haya escrito nada. `:user-invalid` solo se activa después de que el usuario interactuó con el campo y lo dejó inválido, que es el comportamiento que tiene sentido visualmente.

---

## Sección 3 — Decisiones técnicas

### 3.1 — ¿Qué fue lo más difícil de este ejercicio y cómo lo resolviste?

> Lo más difícil fue entender la diferencia entre `aria-required` y `required` y cuándo usar cada uno. Lo resolví probando en el navegador y buscando en MDN cómo los lectores de pantalla interpretan cada atributo.

### 3.2 — ¿Qué cambiarías si tuvieras que hacerlo de nuevo?

> Agregaría más estilos al formulario para que visualmente sea más atractivo, y también haría el layout responsive para que se vea bien en celular. Por ahora funciona pero se ve bastante básico en pantallas chicas.

### 3.3 — ¿Qué alternativas consideraste y por qué las descartaste?

> Consideré usar un `<select>` tradicional para el motivo de contacto pero preferí el `<datalist>` porque permite que el usuario escriba libremente o elija de la lista, es más flexible. Para los mensajes de error usé `:user-invalid ~ .error-message` en CSS puro, que es lo que la SPEC pedía — validación solo con HTML5 y CSS, sin JavaScript.

---

## Sección 4 — Declaración de uso de IA

```
[ ] Resolví el ejercicio completamente sin ayuda de IA
[x] Usé IA para entender algún concepto, pero escribí el código yo
[ ] Usé IA para generar un borrador que luego modifiqué y entendí
[ ] Usé IA extensamente y completé la reflexión para entender lo que hice
```

*Si usaste IA, describí brevemente cómo:*

> Usé IA para entender cómo funcionan `:user-invalid` y `:user-valid` porque no los conocía, y para ver cómo conectar `aria-describedby` con los mensajes de error. El código lo escribí yo y lo fui revisando para asegurarme de entender qué hacía cada parte.

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
