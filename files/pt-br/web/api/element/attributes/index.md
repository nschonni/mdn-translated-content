---
title: Element.attributes
slug: Web/API/Element/attributes
---
{{ APIRef("DOM") }}

A propriedade **`Element.attributes`** retorna uma coleção de todos os atributos registrados para um nó especificado. É um {{domxref("NamedNodeMap")}}, e não um `Array`, então não há os métodos de um {{jsxref("Array")}} e os nós indexados {{domxref("Attr")}} podem ser diferentes entre os navegadores. Para ser mais específico, `attributes` é um par de chave/valor de strings que representa qualquer informação relacionada ao atributo.

## Sintaxe

```
var attr = element.attributes;
```

## Exemplo

### Exemplos básicos

```js
// Obtem o primeiro elemento <p> no documento
var para = document.getElementsByTagName("p")[0];
var atts = para.attributes;
```

### Listando os atributos dos elementos

Indexadores numéricos são úteis para percorrer através de todos os atributos de um elemento.
O exemplo a seguir percorre através dos nós dos atributos do elemento no documento que tenha o id de "p1", e imprime o valor de cada atributo.

```html
<!DOCTYPE html>

<html>

 <head>
  <title>Exemplo com atributos</title>
  <script type="text/javascript">
   function listAttributes() {
     var paragraph = document.getElementById("paragraph");
     var result = document.getElementById("result");

     // Antes, vamos verificar se o paragrafo tem algum atributo
     if (paragraph.hasAttributes()) {
       var attrs = paragraph.attributes;
       var output = "";
       for(var i = attrs.length - 1; i >= 0; i--) {
         output += attrs[i].name + "->" + attrs[i].value;
       }
       result.value = output;
     } else {
       result.value = "Nenhum atributo para mostrar";
     }
   }
  </script>
 </head>

<body>
 <p id="paragraph" style="color: green;">Paragrafo de exemplo</p>
 <form action="">
  <p>
    <input type="button" value="Mostra o nome e o valor do atributo"
      onclick="listAttributes();">
    <input id="result" type="text" value="">
  </p>
 </form>
</body>
</html>
```

## Especificações

| Especificação                                                                                        | Status                           | Comentário                                                                                                |
| ---------------------------------------------------------------------------------------------------- | -------------------------------- | --------------------------------------------------------------------------------------------------------- |
| {{SpecName('DOM WHATWG', '#dom-element-attributes', 'Element.attributes')}} | {{Spec2('DOM WHATWG')}} | Da {{SpecName('DOM3 Core')}}, movido de {{domxref("Node")}} para {{domxref("Element")}} |
| {{SpecName('DOM3 Core', 'core.html#ID-84CF096', 'Element.attributes')}}     | {{Spec2('DOM3 Core')}}     | Nenhuma alteração a partir da {{SpecName('DOM2 Core')}}                                            |
| {{SpecName('DOM2 Core', 'core.html#ID-84CF096', 'Element.attributes')}}     | {{Spec2('DOM2 Core')}}     | Nenhuma alteração a partir da {{SpecName('DOM1')}}                                                |
| {{SpecName('DOM1', 'level-one-core.html#ID-84CF096', 'Element.attributes')}} | {{Spec2('DOM1')}}         | Definição inicial.                                                                                        |

## Compatibilidade com navegadores

{{Compat("api.Element.attributes")}}

## Veja também

- {{domxref("NamedNodeMap")}}, a interface do objeto retornado
- Considerações sobre a compatibilidade entre os navegadores: em [quirksmode](http://www.quirksmode.org/dom/w3c_core.html#attributes)
