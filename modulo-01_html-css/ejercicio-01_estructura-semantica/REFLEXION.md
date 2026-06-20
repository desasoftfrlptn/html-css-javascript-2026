# REFLEXION — Ejercicio 1.1: Estructura Semántica HTML

> **Instrucciones:** Completá este archivo DESPUÉS de terminar tu solución. Escribí con tus propias palabras. Respuestas copiadas de internet o generadas por IA sin elaboración propia no son válidas.
>
> Tiempo esperado para completar esta reflexión: 20–30 minutos.

---

## Sección 1 — Explicación de mi solución

*Describí en 150–250 palabras qué hace tu archivo HTML y cuáles fueron las decisiones de estructura que tomaste. No copies el código, explicá el razonamiento.*

> 
> Yo al ver los temas para hablar me parecieron propios monotos y aburridos, siempre ia, siempre evolucion tecnologica, etc etc, lo que hice fue hablando algo que me encanta que es la musica y hablando sobre una de mis bandas favortias organizando el contenido como lo queria la catedra.
>Poner un HEADER principal, un MENU (<NAV>) y despues viene el MAIN donde esta el ARTICLE, asi separe bien todo para que sea mas legible y no hacer un monton de DIVs

---

## Sección 2 — Preguntas conceptuales

Respondé cada pregunta. Las respuestas deben ser tuyas. Podés investigar, pero explicá con tus palabras.

### 2.1 — ¿Cuál es la diferencia entre `<section>` y `<article>`? ¿Cuándo usarías cada uno?

> El article se usa cuando lo que esta dentro se entiende bien de lo que habla, y se puede poner en cualquier parte de la pagina, mientras que el SECTION se usa para agrupar un contenido en partes tematicas pero siempre hablando de lo mismo y componen el contenido principal
> 
---

### 2.2 — ¿Por qué es importante el atributo `datetime` en la etiqueta `<time>`? ¿Quién lo usa?

> El datetime sirve para decirle a la computadora de forma estandar el horario, el browser para saber la hora

---

### 2.3 — Tu página tiene `<header>` en dos lugares: uno para la página y uno dentro del `<article>`. ¿Eso es válido? ¿Por qué?

> Si es valido, porque el HEADER es la cabecera del contenedor en el que está metido, podes usar muchos HEDERS si estos sirvan para agrupar elementos introducidos

---

### 2.4 — Un motor de búsqueda como Google lee tu HTML. ¿Qué ventaja le da usar etiquetas semánticas versus usar solo `<div>` con clases?

> Usar etiquetas semánticas como <header>, <main> o <article> ayuda a que Google entienda mejor la estructura y el contenido de la página. Con solo <div>, el buscador tiene menos información sobre qué representa cada sección.

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

> Usan <div> para elementos que tienen etiquetas especificas 
<nav>
  <a href="/home">Inicio</a>
  <a href="/about">Nosotros</a>
</nav>

<main>
  <h1>Mi primer artículo</h1>
  <p>Contenido del artículo...</p>
</main>

---

## Sección 3 — Decisiones técnicas

### 3.1 — ¿Qué etiqueta usaste para el logo y por qué? ¿Hay alternativas?

<a href="index.html">
    <img src="images/tool-logo.png" alt="Logotipo oficial de la banda Tool">
</a>

>Lo use porque todas las paginas lo hacen y hay alternativas, nose cuales son
---

### 3.2 — ¿Elegiste `<ul>` u `<ol>` para tu lista? ¿Por qué esa y no la otra?

> Use el <ul> porque la lista no tiene que estar ordenada y no hay un orden jerarquico para ordenarla, si tendria que estar ordenada usaria un <ol>

---

### 3.3 — Si alguien accede a tu página solo con un lector de pantalla (sin ver el HTML), ¿podría navegar y entender el contenido? ¿Qué cambiarías para mejorar la experiencia?

>Si, alguien podria ver y entender la pagina, la hice muy bien creo. Si podria cambiar algo seria agregarle estilos con css para que quede mas lindo

---

## Sección 4 — Declaración de uso de IA

Marcá con una `x` lo que corresponda:

```
[ ] Resolví el ejercicio completamente sin ayuda de IA
[❌] Usé IA para entender algún concepto, pero escribí el código yo
[ ] Usé IA para generar un borrador que luego modifiqué y entendí
[ ] Usé IA extensamente y completé la reflexión para entender lo que hice
```

*Si usaste IA, describí brevemente cómo:*

> Use para entender bien el orden semantico y tambien me ayudo con los links al momento de presionarlos y llevarme a mi seccion, tambien me ayudo a correjir mi redaccion en el contenido de la pagina

---

## Sección 5 — Autoevaluación

En una escala del 1 al 5, ¿cuánto entendés ahora el concepto de HTML semántico?

```
[ ] 1 — Muy poco, necesito repasar
[ ] 2 — Entiendo lo básico
[ ] 3 — Lo entiendo bien
[❌] 4 — Lo entiendo bien y puedo explicárselo a otro
[ ] 5 — Podría dar una clase sobre esto
```

*¿Qué parte te resultó más difícil?*

> Separar la pagina en secciones
