---
title: <input type="checkbox">
slug: Web/HTML/Element/input/checkbox
translation_of: Web/HTML/Element/input/checkbox
original_slug: Web/HTML/Elemento/input/checkbox
---

El elemento HTML **`<input type="checkbox">`** es un elemento de entrada que te permite insertar un vector o array de valores. El atributo **value** es usado para definr el valor enviado por el **checkbox**. El atributo **checked** se usa para indicar que el elemento está seleccionado. El atributo **indeterminate** se usa para indicar que el **checkbox** esta en un estado indeterminado (en la mayoria de las plataformas, esto dibuja una linea horizontal que atraviesa el **checkbox**).

## Atributos

Este elemento posee los "[atributos globales](/es/docs/HTML/Global_attributes)".

- {{htmlattrdef("checked")}}
  - : Cuando el valor del atributo **type** es **`checkbox`**, la presencia de este atributo booleano indica que el control se selecciona de forma predeterminada; de lo contrario, se ignora.
- {{htmlattrdef("value")}}
  - : El valor inicial de control. Si se omite la propiedad **value**, el **resultado devuelto** al leer esta propiedad será la cadena **on**.
    Tenga en cuenta que al volver a cargar la pagina, Gecko y IE [ignorarán el valor especificado en el código HTML](https://bugzilla.mozilla.org/show_bug.cgi?id=46845#c186), si el valor se cambió antes de la recarga.
- {{htmlattrdef("indeterminate")}}
  - : Indica que la casilla de verificación está en un estado indeterminado (en la mayoría de las plataformas, dibuja una línea horizontal a través del checkbox).

## Ejemplo

```html
<label><input type="checkbox" id="cbox1" value="first_checkbox"> Este es mi primer checkbox</label><br>

<input type="checkbox" id="cbox2" value="second_checkbox"> <label for="cbox2">Este es mi segundo checkbox</label>
```

Esto crea dos casillas de verificación, que se ven así:

{{EmbedLiveSample("Ejemplo")}}

## Especificaciones

| Especificación                                                                                                               | Estatus                          |     |
| ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- | --- |
|                                                                                                                              |                                  |     |
| {{SpecName('HTML WHATWG', 'forms.html#checkbox-state-(type=checkbox)', '&lt;checkbox&gt;')}} | {{Spec2('HTML WHATWG')}} |     |
| {{SpecName('HTML5 W3C', 'forms.html#checkbox-state-(type=checkbox)', '&lt;checkbox&gt;')}}     | {{Spec2('HTML5 W3C')}}     |     |
| {{SpecName('HTML4.01', 'interact/forms.html#checkbox', '&lt;checkbox&gt;')}}                         | {{Spec2('HTML4.01')}}     |     |

## Compatibilidad en navegadores

{{Compat("html.elements.input.input-checkbox")}}
