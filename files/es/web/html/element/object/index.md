---
title: <object>
slug: Web/HTML/Element/object
tags:
  - Contenido incrustado
  - Elemento
  - HTML
  - Referencia
  - Web
  - incrustar
translation_of: Web/HTML/Element/object
original_slug: Web/HTML/Elemento/object
---
{{HTMLSidebar}}

El **elemento HTML `<object>`** representa un recurso externo, que puede ser tratado como una imagen, un contexto de navegación anidado, o como un recurso que debe ser manejado por un plugin.

{{EmbedInteractiveExample("pages/tabbed/object.html", "tabbed-standard")}}

La fuente original de este ejemplo interactivo está almacenada en un repositorio de GitHub. Si quieres contribuir al proyecto de ejemplos interactivos, por favor clona [https://github.com/mdn/interactive-examples](https://github.com/mdn/interactive-examples)y envíanos un pull request.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Content_categories">Content categories</a>
      </th>
      <td>
        <a href="/en-US/docs/Web/HTML/Content_categories#Flow_content"
          >Flow content</a
        >;
        <a href="/en-US/docs/Web/HTML/Content_categories#Phrasing_content"
          >phrasing content</a
        >;
        <a href="/en-US/docs/Web/HTML/Content_categories#Embedded_content"
          >embedded content</a
        >, palpable content; if the element has a
        {{htmlattrxref("usemap","object")}} attribute,
        <a href="/en-US/docs/Web/HTML/Content_categories#Interactive_content"
          >interactive content</a
        >;
        <a href="/en-US/docs/Web/HTML/Content_categories#Form_listed">listed</a
        >,
        <a href="/en-US/docs/Web/HTML/Content_categories#Form_submittable"
          >submittable</a
        >
        <a
          href="/en-US/docs/Web/HTML/Content_categories#Form-associated_content"
          >form-associated</a
        >
        element.
      </td>
    </tr>
    <tr>
      <th scope="row">Contenido permitido</th>
      <td>
        cero o más elementos {{HTMLElement("param")}} , luego
        <a
          href="/en-US/docs/Web/HTML/Content_categories#Transparent_content_model"
          >transparent</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">Tag omission</th>
      <td>{{no_tag_omission}}</td>
    </tr>
    <tr>
      <th scope="row">Padres permitidos</th>
      <td>
        Cualquier elemento que acepte
        <a href="/en-US/docs/Web/HTML/Content_categories#Embedded_content"
          >embedded content</a
        >
        (contenido incrustado).
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>
        {{ARIARole("application")}}, {{ARIARole("document")}},
        {{ARIARole("image")}}
      </td>
    </tr>
    <tr>
      <th scope="row">Interfaz DOM</th>
      <td>{{domxref("HTMLObjectElement")}}</td>
    </tr>
  </tbody>
</table>

## Atributos

Este elemento incluye los [global attributes](/es/docs/Web/HTML/Global_attributes).

- {{HTMLAttrDef("archive")}} only {{Obsolete_Inline("HTML5")}}
  - : Una lista separada por espacios de las URl's de archivos o recursos para el objeto.
- {{HTMLAttrDef("border")}}{{Deprecated_Inline("HTML4.01")}}{{Obsolete_Inline("HTML5")}}
  - : El grosor de una línea de margen alrededor del control, en pixeles.
- {{HTMLAttrDef("classid")}} only {{Obsolete_Inline("HTML5")}}
  - : The URI of the object's implementation. It can be used together with, or in place of, the **data** attribute.
- {{HTMLAttrDef("codebase")}} only {{Obsolete_Inline("HTML5")}}
  - : The base path used to resolve relative URIs specified by **classid**, **data**, or **archive**. If not specified, the default is the base URI of the current document.
- {{HTMLAttrDef("codetype")}} only {{Obsolete_Inline("HTML5")}}
  - : The content type of the data specified by **classid**.
- {{HTMLAttrDef("data")}}
  - : La dirección de la fuente, escrita como una URL válida. Al menos uno de los dos atributos, **data** o **type**, deben estar definidos.
- {{HTMLAttrDef("declare")}} only {{Obsolete_Inline("HTML5")}}
  - : The presence of this Boolean attribute makes this element a declaration only. The object must be instantiated by a subsequent `<object>` element. In HTML5, repeat the \<object> element completely each that that the resource is reused.
- {{HTMLAttrDef("form")}}
  - : El elemento form, si es que hay alguno, al que el objeto está asociado (su _form propietario_). El valor de este atributo debe ser el ID de un elemento {{HTMLElement("form")}} del mismo documento.
- {{HTMLAttrDef("height")}}
  - : La altura del recurso mostrado, en [CSS pixels](https://drafts.csswg.org/css-values/#px). -- (Valores absolutos unicamente. [NO percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes))
- {{HTMLAttrDef("name")}}
  - : El nombre de un contexto de navegación válido (HTML5), o el nombre del control (HTML4).
- {{HTMLAttrDef("standby")}} only {{Obsolete_Inline("HTML5")}}
  - : A message that the browser can show while loading the object's implementation and data.
- {{HTMLAttrDef("tabindex")}} only {{Obsolete_Inline("HTML5")}}
  - : The position of the element in the tabbing navigation order for the current document.
- {{HTMLAttrDef("type")}}
  - : El [content type](/es/docs/Glossary/Content_type) del recurso especificado mediante **data**. Al menos uno de los dos atributos, **data** o **type**, deben estar definidos.
- {{HTMLAttrDef("typemustmatch")}}
  - : Este valor booleano indica si el atributo **type** y el [content type](/es/docs/Glossary/Content_type) real del recurso deben coincidir para porder ser usados.
- {{HTMLAttrDef("usemap")}}
  - : Una refercia hash-name a un elemento {{HTMLElement("map")}}; es decir un '#' seguido del valor de un {{htmlattrxref("name", "map")}} de un elemento map.
- {{HTMLAttrDef("width")}}
  - : El ancho del recurso mostrado, en [CSS pixels](https://drafts.csswg.org/css-values/#px). -- (Valores absolutos unicamente. [NO percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes))

## Ejemplos

### Incrustar una película flash

```html
<!-- Incrustar una película flash -->
<object data="movie.swf"
  type="application/x-shockwave-flash"></object>

<!-- Incrustar una película flash con parámetros -->
<object data="movie.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```

## Especificaciones

| Especificación                                                                                                           | Estado                           | Comentario |
| ------------------------------------------------------------------------------------------------------------------------ | -------------------------------- | ---------- |
| {{SpecName("HTML WHATWG", "embedded-content.html#the-object-element", "&lt;object&gt;")}} | {{Spec2("HTML WHATWG")}} |            |
| {{SpecName("HTML5 W3C", "embedded-content-0.html#the-object-element", "&lt;object&gt;")}} | {{Spec2("HTML5 W3C")}}     |            |
| {{SpecName("HTML4.01", "struct/objects.html#h-13.3", "&lt;object&gt;")}}                         | {{Spec2("HTML4.01")}}     |            |

## Compatibilidad con Navegadores

{{Compat("html.elements.object")}}

## See also

- {{HTMLElement("applet")}} {{Obsolete_Inline}}
- {{HTMLElement("embed")}}
- {{HTMLElement("param")}}
