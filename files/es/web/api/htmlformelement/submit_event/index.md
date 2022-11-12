---
title: GlobalEventHandlers.onsubmit
slug: Web/API/HTMLFormElement/submit_event
translation_of: Web/API/GlobalEventHandlers/onsubmit
original_slug: Web/API/GlobalEventHandlers/onsubmit
---

{{ApiRef("HTML DOM")}}

Manejador de eventos del evento submit para el objeto window.

## Sintaxis

```
window.onsubmit = funcRef;
```

### Parametros

- `funcRef` es una referencia a una función.

## Ejemplo

```
<html>
<script>
function reg() {
  window.captureEvents(Event.SUBMIT);
  window.onsubmit = hit;
}

function hit() {
  console.log('hit');
}
</script>

<body onload="reg();">
<form>
  <input type="submit" value="submit" />
</form>
<div id="d"> </div>
</body>
</html>
```

## Notas

El evento submit se genera cuando el usuario hace click en el boton submit en un formulario (`<input type="submit"/>`).

El evento submit no se genera cuando el usuario llama a la función `form.submit()` directamente.

## Especificaciones

| Specification                                                                                    | Status                           | Comment |
| ------------------------------------------------------------------------------------------------ | -------------------------------- | ------- |
| {{SpecName('HTML WHATWG','webappapis.html#handler-onsubmit','onsubmit')}} | {{Spec2('HTML WHATWG')}} |         |

## Browser Compatibility

{{Compat("api.GlobalEventHandlers.onsubmit")}}
