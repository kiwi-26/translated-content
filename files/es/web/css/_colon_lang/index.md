---
title: ':lang'
slug: Web/CSS/:lang
tags:
  - CSS
  - Pseudo-clase
  - Web
translation_of: Web/CSS/:lang
---

{{CSSRef}}

La [pseudo-clase](/es/docs/Web/CSS/Pseudo-classes) **`:lang()`** de [CSS](/es/docs/Web/CSS) es utilizada para modificar elementos en función del idioma en el que se determina que están.

```css
/* Selecciona cualquier <p> en inglés (en) */
p:lang(en) {
  quotes: '\201C' '\201D' '\2018' '\2019';
}
```

> **Nota:** En HTML, el lenguaje está determinado por una combinación del atributo {{htmlattrxref("lang")}}, el elemento {{HTMLElement("meta")}} y posiblemente por la información del protocolo (como los encabezados HTTP). Para otros tipos de documentos, puede haber otros métodos de documentos para determinar el idioma.

## Sintaxis

### Sintaxis formal

{{csssyntax}}

### Parámetro

- `<language-code>`
  - : Un {{cssxref("&lt;string&gt;")}} que representa el idioma que desea orientar. Los valores aceptables se especifican en las especificaciones [HTML](/es/docs/Web/HTML).

## Ejemplo

En este ejemplo, la pseudo-clase `:lang()` se usa para hacer coincidir los elementos primarios de los elementos de cita ({{htmlElement("q")}}) utilizando [selectores de hijo](/es/docs/Web/CSS/Child_selectors). Tenga en cuenta que esto no ilustra la única manera de hacerlo, y que el mejor método para usar depende del tipo de documento. También tenga en cuenta que los valores de {{glossary("Unicode")}} se utilizan para especificar algunos de los caracteres de comillas especiales.

### HTML

```html
<div lang="en"><q>Esta cita en inglés tiene una cita <q>anidada</q> adentro.</q></div>
<div lang="fr"><q>Esta cita en francés tiene una cita <q>anidada</q> adentro.</q></div>
<div lang="de"><q>Esta cita en aleman tiene una cita <q>anidada</q> adentro.</q></div>
```

### CSS

```css
:lang(en) > q { quotes: '\201C' '\201D' '\2018' '\2019'; }
:lang(fr) > q { quotes: '« ' ' »'; }
:lang(de) > q { quotes: '»' '«' '\2039' '\203A'; }
```

### Resultado

{{EmbedLiveSample('Ejemplo', 350)}}

## Especificaciones

| Especificación                                                               | Estado                               | Comentarios                  |
| ---------------------------------------------------------------------------- | ------------------------------------ | ---------------------------- |
| {{SpecName('CSS4 Selectors', '#lang-pseudo', ':lang()')}} | {{Spec2('CSS4 Selectors')}} | Ningún cambio.               |
| {{SpecName('CSS3 Selectors', '#lang-pseudo', ':lang()')}} | {{Spec2('CSS3 Selectors')}} | Ningún cambio significativo. |
| {{SpecName('CSS2.1', 'selector.html#lang', ':lang()')}}     | {{Spec2('CSS2.1')}}             | Definición Inicial.          |

## Compatibilidad con navegadores

{{Compat("css.selectors.lang")}}

## Ver también

- Pseudo-clases relacionadas con el lenguaje: {{cssxref(":lang")}}, {{cssxref(":dir")}}
- Atributo HTML {{htmlattrxref("lang")}}
- [BCP 47 - Etiquetas para identificar idiomas](https://tools.ietf.org/html/bcp47)
