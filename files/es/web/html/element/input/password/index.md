---
title: <input type="password">
slug: Web/HTML/Element/input/password
tags:
  - Element
  - HTML
  - Reference
translation_of: Web/HTML/Element/input/password
original_slug: Web/HTML/Elemento/input/password
---

{{HTMLSidebar}}

Los elementos `<input>` de tipo **`"password"`** proporcionan una forma para que el usuario ingrese una contraseña de forma segura. El elemento se presenta como un control de editor de texto, sin formato, de una línea, en el que el texto está oculto para que no pueda leerse, generalmente reemplazando cada carácter con un símbolo como el asterisco ("\*") o un punto ("•"). Este carácter variará dependiendo del {{Glossary("user agent")}} y del {{Glossary("OS")}}.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/HTML/Content_categories">Content categories</a>
      </th>
      <td>
        <a href="/en-US/docs/HTML/Content_categories#Flow_content"
          >Flow content</a
        >, listado, tabla enviable, reseteable, elementos de forma asociada,
        <a href="/en-US/docs/HTML/Content_categories#Phrasing_content"
          >phrasing content</a
        >, elementos etiquetables, contenido palpable.
      </td>
    </tr>
    <tr>
      <th scope="row">Contenido permitido</th>
      <td>Ninguno, es un {{Glossary("empty element")}}.</td>
    </tr>
    <tr>
      <th scope="row">Omisión de etiquetas</th>
      <td>
        Tiene que tener una etiqueta al inicio y no tener una etiqueta final.
      </td>
    </tr>
    <tr>
      <th scope="row">Elementos de parentescos</th>
      <td>
        Cualquier elemento que accepta
        <a href="/en-US/docs/HTML/Content_categories#Phrasing_content"
          >phrasing content</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">Interfaz DOM</th>
      <td>{{domxref("HTMLInputElement")}}</td>
    </tr>
  </tbody>
</table>

## Atributos

Además de los atributos listados abajo, este elemento puede tener cualquier [global attributes](/es/docs/HTML/Global_attributes).

- {{htmlattrdef("autocomplete")}}
  - : Establece el valor del atributo de autocompletado en el campo de una contraseña. En caso de ser cierto, automaticamente se rellena con el valor previamente almacenado.
- {{htmlattrdef("autofocus")}}
  - : Este atributo Booleano te permite especificar que la página ponga el foco en un campo a menos que el usuario lo revoque, por ejemplo, escribir en un campo diferente. Solo un elemento en el documento puede tener el atributo Booleano **autofocus**.
- {{htmlattrdef("disabled")}}
  - : Este atributo Booleano indica que el campo de la contraseña no está disponible. Además, deshabilita los valores que no son enviados por el campo.
- {{htmlattrdef("defaultvalue")}}
  - : Define un valor predeterminado en el campo de la contraseña.
- {{htmlattrdef("inputmode")}}

  - : Le da proporciona información al buscador sobre que teclado mostrar. Los valores posibles son:

    - `verbatim`: Alfanumérico, contenido no verbla tales como usuarios y contraseñas.
    - `latin`: Introducción de texto en el lenguaje preferido del usuario con ayudas de escritura, como predicción de texto. Se usa para comunicación de usuario a ordenador en, por ejemplo, campos de búsqueda.
    - `latin-name`: Como _latin_, pero para nombres de personas.
    - `latin-prose`: Como _latin_, pero con unas ayudas de escritura más activas. Para comunicación de usuario a usuario como por ejemplo, mensajería instantanea o emails.
    - `full-width-latin`: Como _latin-prose_, pero para lenguajes secundarios del usuario.
    - `kana`: Entrada de texto Kana o romaji, normalmente entrada hiragana, usa carácteres con ancho completo, con soporte para converstirse a kanji. Establecido para la entrada de texto Japonés.
    - `katakana`: Katakana input, using full-width characters, with support for converting to kanji. Intended for Japanese text input.

- {{htmlattrdef("maxlength")}}
  - : Establece el valor del atributo maxlength en el campo de una contraseña.
- {{htmlattrdef("minlength")}}
  - : Establece el valor del atributo minlength en el campo de una contraseña.
- {{htmlattrdef("name")}}
  - : Nombre del campo, usado para datos enviados desde formulario.
- {{htmlattrdef("pattern")}}
  - : Establece el valor del atributo pattern del campo de una contraseña.
- {{htmlattrdef("placeholder")}}
  - : Establece el valor del atributo placeholder del campo de una contraseña.
- {{htmlattrdef("readonly")}}
  - : Este atributo Booleano indica que el usuario no puede modificar el valor del campo de una contraseña.
- {{htmlattrdef("required")}}
  - : Este atributo Booleano especifica que el usuario debe rellenar con un valor antes de enviar un formulario.
- {{htmlattrdef("size")}}
  - : Establece el valor del atributo size del campo de una contraseña.

## Ejemplos

Para crear un widget que muestre una constraseña, use:

```html
<input type="password">
```

Para crear un widget que muestre una contraseña con un patrón o diseño, use:

```html
<input type="password" pattern=".{6,}">
```

El ejemplo de arriba creará un elemento password que deberá contener 6 o más carácteres.

## Especificaciones

| Especificacion                                                                                                       | Status                           | Comentario |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------- | ---------- |
| {{SpecName('HTML WHATWG', 'the-input-element.html#the-input-element', '&lt;input&gt;')}} | {{Spec2('HTML WHATWG')}} |            |
| {{SpecName('HTML5 W3C', 'forms.html#the-input-element', '&lt;input&gt;')}}                 | {{Spec2('HTML5 W3C')}}     |            |
| {{SpecName('HTML4.01', 'interact/forms.html#h-17.4', '&lt;form&gt;')}}                         | {{Spec2('HTML4.01')}}     |            |

> **Nota:** **Fix me:** Insert Browser Compatibility table here.
