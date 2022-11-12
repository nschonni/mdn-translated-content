---
title: GlobalEventHandlers.onfocus
slug: Web/API/Window/focus_event
translation_of: Web/API/GlobalEventHandlers/onfocus
original_slug: Web/API/GlobalEventHandlers/onfocus
---

{{ApiRef("HTML DOM")}}

La propiedad **onfocus** devuelve un manejador de eventos para el evento onFocus en el elemento actual.

## Sintaxis

```js
element.onfocus = event handling code
```

## Notas

El evento focus se dispara cuando el usuario establece el foco en el elemento.

Para que el evento `onfocus` se dispare en elementos que no sean inputs, los mismos deben establecerse con el atributo {{htmlattrxref("tabindex")}} (vea [Building keyboard accessibility back in](/es/docs/Learn/Accessibility/HTML#Building_keyboard_accessibility_back_in) para mas detalles).

A diferencia de MSIE, en que casi toda clase de elemento puede recibir el evento focus, en los navegadores Gecko en los que casi todos los elementos NO reciben este evento.

## Especificaciones

| Specification                                                                                    | Status                           | Comment |
| ------------------------------------------------------------------------------------------------ | -------------------------------- | ------- |
| {{SpecName('HTML WHATWG','webappapis.html#handler-onfocus','onfocus')}} | {{Spec2('HTML WHATWG')}} |         |

## Compatibilidad con los Navegadores

{{Compat("api.GlobalEventHandlers.onfocus")}}
