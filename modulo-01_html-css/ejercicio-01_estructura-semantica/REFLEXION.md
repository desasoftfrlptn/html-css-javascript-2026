# REFLEXION — Ejercicio 1.1: Estructura Semántica HTML

> **Instrucciones:** Completá este archivo DESPUÉS de terminar tu solución. Escribí con tus propias palabras. Respuestas copiadas de internet o generadas por IA sin elaboración propia no son válidas.
>
> Tiempo esperado para completar esta reflexión: 20–30 minutos.

---

## Sección 1 — Explicación de mi solución

*Describí en 150–250 palabras qué hace tu archivo HTML y cuáles fueron las decisiones de estructura que tomaste. No copies el código, explicá el razonamiento.*

> ✏️ **Tu respuesta aquí:**
>
> Para llevar a cabo la solucion de este apartado aproveche que hace poco hice un resumen para la materia tecnologia y gestion web y me ayude con eso para generar el contenido de la pagina. Estructuralmente hablando, decidi hacer una navegacion para ir a los diferentes sectores de la pagina, en cada uno te cuenta sobre una etapa especifica de la web, use imagenes y le agregue el reconocimiento al autor de la misma, como corresponde. Es una pagina web que cuenta un poco la historia de la web, aproveche para intentar implementar la mayoria de las nuevas etiquetas para poder entenderlas y aprender a usarlas al 100%.

---

## Sección 2 — Preguntas conceptuales

Respondé cada pregunta. Las respuestas deben ser tuyas. Podés investigar, pero explicá con tus palabras.

### 2.1 — ¿Cuál es la diferencia entre `<section>` y `<article>`? ¿Cuándo usarías cada uno?

> La principal diferencia es que section se encarga de dividir el contenido de una pagina, puede ser para organizar temas o que sea mas visible, en cambio article es de contenido independiente, es decir, se refiere al contenido de una pagina, puede ser un blog, comentario, informacion etc.

---

### 2.2 — ¿Por qué es importante el atributo `datetime` en la etiqueta `<time>`? ¿Quién lo usa?

> El atributo datetime dentro de time sirve para la computadora, no es algo que el usuario vea y sirve para que la misma entienda el contenido y sea universal, ya que la descripcion puede tener distintos formatos, pero al agregarle el datetime respeta el formato aa/mm/dd 

---

### 2.3 — Tu página tiene `<header>` en dos lugares: uno para la página y uno dentro del `<article>`. ¿Eso es válido? ¿Por qué?

> Si, es completamente valido porque cada uno tiene una funcion distinta, uno representa el header de la pagina completa y el otro el header del articulo, con los datos del mismo.

---

### 2.4 — Un motor de búsqueda como Google lee tu HTML. ¿Qué ventaja le da usar etiquetas semánticas versus usar solo `<div>` con clases?

> La ventaja principal es que puede entender mejor el contenido y no lo ve como algo generico con divs, si manejas el contenido de la pagina solo con divs y clases, el motor de busqueda no logra entender bien el contenido de la pagina y lo ve como algo generico, con las estiquetas semanticas le estamos dando mas informacion, como que contiene un articulo, una seccion o un aside 

---

### 2.5 — Encontrá **un error semántico** en el siguiente fragmento y explicá cómo lo corregirías:

```html
<div class="navigation">
  <div class="nav-item"><a href="/home">Inicio</a></div>
  <div class="nav-item"><a href="/about">Nosotros</a></div>
</div>

<div class="main-content">
  <div class="post-title">Mi primer artículo</div>
  <div class="post-body">
    <p>Contenido del artículo...</p>
  </div>
</div>
```

> El error semnatico que veo es que se maneja todo con divs cuando se pueden manejar con eqtiquetas especificas, como por ejemplo en div class="navigation" se puede reemplazar con la etiqueta nav mas especifica o div class="main-content" con la etiqueta article


---

## Sección 3 — Decisiones técnicas

### 3.1 — ¿Qué etiqueta usaste para el logo y por qué? ¿Hay alternativas?

> Para le logo utilice la etiqueta img ya que la funcion es mostrar una imagen dentro de la pagina, hay algunas alternativas, como la etiqueta picture que sirve para mostrar distintas versiones del logo segun el dispositivo

---

### 3.2 — ¿Elegiste `<ul>` u `<ol>` para tu lista? ¿Por qué esa y no la otra?

> elegi ul ya que la lista que cree no tiene ningun orden significativo, solo se encarga de mostrar el contenido separado, en formato de lista, sin ningun orden especifico.

---

### 3.3 — Si alguien accede a tu página solo con un lector de pantalla (sin ver el HTML), ¿podría navegar y entender el contenido? ¿Qué cambiarías para mejorar la experiencia?

> Si, alguien que navege la pagina con un lector de pantalla podria entender el contenido ya que intente utiliazar la mayor cantidad de etiquetas especificas siempre y cuando sea necesario, la pagina esta ordenada y bien declarado cada sector. siempre se puede mejorar, en este caso, podria Hacer que el logo sea un enlace a la página principal,asi genera mas accesibilidad para el usuario o mejorar algunos textos.

---

## Sección 4 — Declaración de uso de IA

Marcá con una `x` lo que corresponda:

```
[ ] Resolví el ejercicio completamente sin ayuda de IA
[x] Usé IA para entender algún concepto, pero escribí el código yo
[ ] Usé IA para generar un borrador que luego modifiqué y entendí
[ ] Usé IA extensamente y completé la reflexión para entender lo que hice
```

*Si usaste IA, describí brevemente cómo:*

> si, utilice inteligencia artificial, pero para entender cosas que no sabia, como algunas etiquetas que nunca habia implementado antes, me ayudaba con la ia para entenderlas y saber como aplicarlas, luego las aplicaba en mi codigo yo. al final, cuando ya termine el codigo, se lo pase para que revise algun error de sintaxis, me corrigio algunas cosas como etiquetas que me habian quedado mal cerradas, errores de sintaxis

---

## Sección 5 — Autoevaluación

En una escala del 1 al 5, ¿cuánto entendés ahora el concepto de HTML semántico?

```
[ ] 1 — Muy poco, necesito repasar
[ ] 2 — Entiendo lo básico
[ ] 3 — Lo entiendo bien
[x] 4 — Lo entiendo bien y puedo explicárselo a otro
[ ] 5 — Podría dar una clase sobre esto
```

*¿Qué parte te resultó más difícil?*

> Me resulto mas dificil cuando tocaba implementar alguna etiqueta que nunca habia visto, como fue el caso del figure para añadir el autor de la imagen, ya que nunca habia utilizado esta etiqueta y tuve muchos errores que fui corrigiendo con ayuda de la IA.
