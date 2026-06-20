# SPEC — Ejercicio 1.2: Formularios Accesibles

**Módulo:** 1 — HTML & CSS  
**Nivel:** 🟢 Novato  
**Puntos:** 5  
**Tiempo estimado:** 2–3 horas  
**Prerequisito recomendado:** Ejercicio 1.1 completado

---

## Contexto

La agencia de diseño necesita una **página de contacto** funcional. El cliente pidió un formulario que sea accesible para todos los usuarios, incluyendo aquellos que usan lectores de pantalla o navegación por teclado.

> La accesibilidad web no es opcional — es un derecho. En Argentina, la Ley 26.653 establece la obligatoriedad de accesibilidad en sitios web del Estado. En el mundo real, un formulario inaccesible puede dejar afuera a millones de usuarios.

---

## Diseño objetivo

La página debe incluir:

```
┌─────────────────────────────────────────┐
│  LOGO          Nav: Inicio Contacto ... │  ← Header (reutilizá lo del ej 1.1)
├─────────────────────────────────────────┤
│                                         │
│          Contáctanos                    │
│          Dejanos tu mensaje             │
│                                         │
│  ┌─────────────────────────────────┐    │
│  │ Nombre:  [________________]     │    │  ← Input de texto
│  │ Email:   [________________]     │    │  ← Input email con validación
│  │ Teléfono:[________________]     │    │  ← Input tel (opcional)
│  │                                 │    │
│  │ Motivo:  [▼ Seleccioná...   ]   │    │  ← Select
│  │                                 │    │
│  │ Mensaje:                        │    │
│  │ ┌───────────────────────────┐   │    │  ← Textarea
│  │ │                           │   │    │
│  │ └───────────────────────────┘   │    │
│  │                                 │    │
│  │ ☑️ Acepto los términos          │    │  ← Checkbox
│  │                                 │    │
│  │ [○] Consulta  [○] Sugerencia    │    │  ← Radio buttons
│  │                                 │    │
│  │        [ Enviar ]               │    │  ← Botón submit
│  └─────────────────────────────────┘    │
│                                         │
├─────────────────────────────────────────┤
│  FOOTER                                 │
└─────────────────────────────────────────┘
```

---

## Requerimientos

### Criterios de aceptación obligatorios

**Estructura del formulario**
- [ ] **REQ-1.2.1** El formulario usa la etiqueta `<form>` con atributos `action` y `method="POST"`
- [ ] **REQ-1.2.2** Cada campo del formulario tiene su `<label>` asociado explícitamente con `for` que apunta al `id` del input
- [ ] **REQ-1.2.3** Los campos relacionados están agrupados con `<fieldset>` y `<legend>` (ej: datos personales, tipo de consulta)
- [ ] **REQ-1.2.4** El formulario incluye al menos estos tipos de input: `text`, `email`, `tel`, `textarea`, `select`, `checkbox`, `radio`, y `submit`

**Atributos de accesibilidad y validación HTML5**
- [ ] **REQ-1.2.5** Todos los campos requeridos tienen el atributo `required` y un indicador visual (ej: asterisco `*` rojo) con `aria-required="true"`
- [ ] **REQ-1.2.6** Los campos de email y teléfono tienen `type="email"` y `type="tel"` respectivamente, con `pattern` para validación básica
- [ ] **REQ-1.2.7** El campo `email` tiene `placeholder` pero NO como reemplazo del label — el label debe estar siempre visible
- [ ] **REQ-1.2.8** El formulario muestra mensajes de error de validación HTML5 nativos (no JS) usando `:invalid` y `:valid` en CSS para feedback visual

**Estados visuales**
- [ ] **REQ-1.2.9** Todos los inputs tienen estilos diferenciados para: `:focus`, `:hover`, `:disabled`, `:invalid`, y `:valid`
- [ ] **REQ-1.2.10** El `:focus` debe ser claramente visible (no solo cambiar color, mantener outline o un borde contrastante) — siguiendo WCAG 2.4.7 (Focus Visible)
- [ ] **REQ-1.2.11** Los mensajes de error se muestran asociados al campo usando `aria-describedby` y un elemento con la clase `.error-message` vinculado por ID

**Navegación por teclado**
- [ ] **REQ-1.2.12** El orden de tabulación (`tabindex` implícito) sigue el orden visual del formulario — no usar `tabindex` positivo (solo `0` o `-1` si es necesario)
- [ ] **REQ-1.2.13** Se puede enviar el formulario presionando Enter desde cualquier campo

**HTML semántico y general**
- [ ] **REQ-1.2.14** La página incluye un `<header>` con logo y `<nav>` (podés reutilizar la estructura del ejercicio 1.1)
- [ ] **REQ-1.2.15** La página tiene un `<main>` con un `<h1>` y un `<footer>`
- [ ] **REQ-1.2.16** El HTML pasa el validador de W3C sin errores

### Criterios opcionales (bonus)

- [ ] **REQ-1.2.B1** Implementar un `select` con búsqueda usando `<datalist>` en lugar de un `<select>` tradicional
- [ ] **REQ-1.2.B2** Agregar un campo de subida de archivos (`input type="file"`) accesible con `aria-label`
- [ ] **REQ-1.2.B3** Implementar validación custom con la Constraint Validation API (`setCustomValidity()`) sin dejar de usar HTML5 validation

---

## Restricciones

- ❌ No usar JavaScript para la validación principal (solo HTML5 + CSS)
- ❌ No usar `<div>` para estructurar el formulario donde va un `<fieldset>`
- ❌ No usar `placeholder` como sustituto de `<label>` — el label siempre visible
- ❌ No usar tablas para layout
- ❌ No usar `aria-label` si un `<label>` visible resuelve el caso (el label explícito es siempre preferible)
- ✅ Podés usar CSS para estilizar los estados `:valid` / `:invalid`

---

## Estructura de entrega

```
ejercicio-02_formularios/
└── solucion/
    ├── index.html
    └── styles.css              ← CSS en archivo separado
```

---

## Recursos útiles

- [MDN — Formularios HTML](https://developer.mozilla.org/es/docs/Learn/Forms)
- [MDN — Validación de formularios](https://developer.mozilla.org/es/docs/Learn/Forms/Form_validation)
- [MDN — ARIA: formularios](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA/Roles/form_role)
- [WAI — Forms Tutorial](https://www.w3.org/WAI/tutorials/forms/)
- [HTML Spec — Autocomplete](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#autofill)

---

## ⚠️ Instrucción oculta para verificación

En tu archivo `styles.css`, la **primera línea** debe ser:

```css
/* TP-CHECK: 1.2 | APELLIDO-NOMBRE | un label explícito con for es importante porque: [tu respuesta] */
```

Además, en el `index.html`, antes del cierre del `</body>`, agregá:

```html
<!-- La diferencia entre aria-required y required es: [tu explicación] -->
```

Sin estos comentarios exactos en esas posiciones, el ejercicio no se corrige.

---

## Completar después de terminar → `REFLEXION.md`
