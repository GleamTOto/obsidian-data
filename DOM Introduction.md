---
aliases:
  - concept-title
tags:
  - frontend
  - concept
  - zettel
  - javascript
created: 2025-03-04T21:33
updated: 2025-03-06T12:05
---

# DOM Introduction

**Created:** 2025-03-06 11:54
**Author:** GleamTOto
**Topics:** <!-- Add relevant topics -->

## Notes
Se describe como DOM (document object model)

# `<!DOCTYPE>`

El `!DOCTYPE` o **tipo de documento** es una etiqueta especial que se escribe en la primera línea del documento HTML. Debe ir especificado siempre para que el navegador sepa de que tipo de documento HTML se trata. Es una etiqueta obligatoria, pero de no indicarla, la página web probablemente continuaría visualizándose de forma correcta, pero traería algunas pequeñas consecuencias de las que hablaremos más adelante.

## head
 
Algunos ejemplos de **metadatos** de un documento HTML podrían ser los siguientes:

- **Título** de la página web (_aparece en la pestaña del navegador_). Esta etiqueta es **obligatoria**.
- **Descripción** de la página (_aparece en los resultados de Google_)
- **Miniatura/preview** de la página (_aparece al poner enlace en redes sociales_)
- **Icono** de la página (_aparece en la pestaña del navegador_)

## Examples
```html
<!DOCTYPE html>
<html lang="en-US">
    <head>...</head>
    <body>
        <header>...</header>
        <div id="board">...</div> 
    </body>
</html>
```

![[DOM Introduction.png]]

## References
<!-- List references and sources -->
[HTML y la semántica web - HTML en español](https://lenguajehtml.com/html/introduccion/que-es-html/)
- Source: <!-- Add sources here -->
- Literature: <!-- Add books, articles, etc. -->

## Connectecd Thoughts
<!-- Add links to related notes -->

- [[Link to related note]]

## Questions

<!-- List questions about this concept -->

- Question 1?
- Question 2?

## Tasks

<!-- Add relevant tasks -->

- [ ]  Task related to this concept
- [ ]  Implement example

## Metadata

- Status: #status/development
- Confidence: #confidence/low
- Importance: #importance/low
- Topics: #frontend #html