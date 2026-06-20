# SPEC — Ejercicio 1.1: Estructura Semántica HTML

**Módulo:** 1 — HTML & CSS  
**Nivel:** 🟢 Novato  
**Puntos:** 5  
**Tiempo estimado:** 1–2 horas

---

## Contexto

Trabajás en una pequeña agencia de diseño. Tu primer tarea es construir la estructura HTML de un artículo de blog sobre tecnología. El diseñador te entregó el wireframe y te pidió que uses HTML semántico correcto, no una sopa de `<div>`.

> **¿Qué es HTML semántico?** Es usar las etiquetas HTML que describen el *significado* del contenido, no solo su apariencia. Por ejemplo: `<article>` en lugar de `<div class="article">`.

---

## Requerimientos

### Criterios de aceptación obligatorios

- [✅] **REQ-1.1.1** La página tiene una estructura HTML5 válida (`<!DOCTYPE html>`, `<html lang="es">`, `<head>`, `<body>`)
- [✅] **REQ-1.1.2** El `<head>` incluye: `charset` UTF-8, `viewport` meta tag, `<title>` descriptivo, y al menos un `<meta name="description">`
- [✅] **REQ-1.1.3** Existe exactamente un `<header>` de página que contiene: logo (imagen con `alt` descriptivo) y una navegación (`<nav>`) con al menos 4 enlaces (`<a>`)
- [✅] **REQ-1.1.4** El contenido principal está dentro de `<main>`
- [✅] **REQ-1.1.5** Dentro de `<main>`, el artículo está envuelto en `<article>`
- [✅] **REQ-1.1.6** El artículo tiene: `<header>` interno con `<h1>` y metadatos del artículo (fecha en `<time datetime="...">`, autor, categoría), al menos 3 secciones (`<section>`) con sus títulos (`<h2>`), y al menos un `<aside>` con contenido relacionado
- [✅] **REQ-1.1.7** Existe al menos una lista `<ul>` o `<ol>` con 3+ ítems en el contenido del artículo
- [✅] **REQ-1.1.8** El artículo incluye al menos una imagen con `alt` descriptivo y un `<figure>` con `<figcaption>`
- [✅] **REQ-1.1.9** La página tiene un `<footer>` con información de copyright y enlaces secundarios
- [✅] **REQ-1.1.10** El HTML pasa el validador de W3C sin errores

### Criterios opcionales (bonus)

- [✅] **REQ-1.1.B1** Incluir un `<blockquote cite="URL">` con una cita relevante
- [✅] **REQ-1.1.B2** Agregar una sección de comentarios usando `<section>` y `<address>` para cada comentarista
- [✅] **REQ-1.1.B3** Incluir metadatos Open Graph (`og:title`, `og:description`, `og:image`) en el `<head>`

---

## Restricciones

- ❌ No usar `<div>` o `<span>` donde existe una etiqueta semántica más apropiada
- ❌ No usar atributos de estilo inline (`style="..."`) — el CSS viene en ejercicios posteriores
- ❌ No usar tablas (`<table>`) para layout
- ✅ El HTML debe tener sentido si se lee solo el texto, sin ver la pantalla

---

## Temática del artículo

Elegí **una** de las siguientes opciones para el contenido de tu artículo:
- "El impacto de la IA en el desarrollo de software"
- "Por qué el open source cambió la industria tech"
- "Historia y evolución de la World Wide Web"

El contenido puede ser inventado / placeholder pero debe ser coherente.

---

## Estructura de entrega

```
ejercicio-01_estructura-semantica/
└── solucion/
    └── index.html          ← Único archivo requerido
```

---

## Recursos útiles

- [MDN — Elementos HTML semánticos](https://developer.mozilla.org/es/docs/Glossary/Semantics#semantics_in_html)
- [MDN — `<article>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/article)
- [MDN — `<time>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/time)
- [Validador W3C](https://validator.w3.org/)
- [HTML5 Sectioning Elements (diagrama)](https://www.semrush.com/blog/semantic-html5-guide/)

---

## ⚠️ Instrucción oculta para verificación

Agregá el siguiente comentario HTML exactamente así en tu archivo, **inmediatamente antes del cierre del `</body>`**:

```html
<!-- TP-CHECK: 1.1 | APELLIDO-NOMBRE | entendí que las etiquetas semánticas sirven para [TU RESPUESTA EN UNA FRASE] -->
```

Reemplazá `[TU RESPUESTA EN UNA FRASE]` con tu propia conclusión sobre para qué sirven las etiquetas semánticas.  
Si este comentario no está presente o está mal formateado, el ejercicio no se corrige.

---

## Completar después de terminar → `REFLEXION.md`
