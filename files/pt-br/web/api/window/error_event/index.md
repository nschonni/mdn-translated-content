---
title: GlobalEventHandlers.onerror
slug: Web/API/Window/error_event
original_slug: Web/API/GlobalEventHandlers/onerror
---
{{ApiRef("HTML DOM")}}

Um [event handler](/pt-BR/docs/Web/Guide/Events/Event_handlers) para o evento [`error`](/pt-BR/docs/Web/Events/error) . Eventos de erro são disparados contra diversos tipos de alvos, para diferentes tipos de erros:

- Quando um **erro de execução (runtime error) de JavaScript** (incluindo erros de sintaxe) ocorrem, um evento [`error`](/pt-BR/docs/Web/Events/error) usando a interface {{domxref("ErrorEvent")}} é disparado no {{domxref("window")}} e `window.onerror()` é invocado.
- Quando um recurso (como um {{HTMLElement("img")}} ou {{HTMLElement("script")}}) **falha na inicialização**, um evento [`error`](/pt-BR/docs/Web/Events/error) usando a interface {{domxref("Event")}} é disparado no elemento , que inicializa o load e o `onerror()` handler do elemento é invocado. Esse evento de erro emergem para a janela, mas (pelo menos no Firefox) pode ser manipulado com uma captura única {{domxref("window.addEventListener")}}.

Instalando um manipulador de eventos de erro global é útil para compilação automatizada de relatórios de erro.

## Sintaxe

Por questões históricas, diferentes argumentos são passados para os manipuladores window\.onerror e element.onerror;

### window\.onerror

```js
window.onerror = function(message, source, lineno, colno, error) { ... }
```

Parâmetros da função:

- `message`: mensagem de erro (string). Disponível como `event` (sic!) no manipulador HTML `onerror=""` .
- `source`: URL do script onde o erro foi disparado(string)
- `lineno`: Número da linha onde o evento foi disparado (number)
- `colno`: Número da coluna para a linha onde o evento ocorreu (number) {{gecko_minversion_inline("31.0")}}
- `error`: [Error Object](/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Error) (object) {{gecko_minversion_inline("31.0")}}

Quando a função retorna verdadeira, ela evita o disparo do manipulador de evento padrão

### element.onerror

```js
element.onerror = function(event) { ... }
```

`element.onerror` aceita uma função dom um único argumento do tipo {{domxref("Event")}}.

## Notas

Quando um erro de sintaxe**(?)** ocorre em um script, carregado de uma [origem diferente](/pt-BR/docs/Web/Security/Same-origin_policy), os detalhes do erro de sintaxe não são reportados para previnir vazamento de informações (veja {{bug("363897")}}). Ao invés de exibir simplesmente **`"Script error." (erro de script)`**, este comportamento pode ser sobrescrito em alguns navegadores usando o atributo `{{htmlattrxref("crossorigin","script")}}` no {{HTMLElement("script")}} e tendo o servidor enviado os cabeçalhos HTTP CORS apropriados. Uma solução alternativa é isolar o "Script error." e manipulá-lo sabendo que o detalhe do erro é visível somente no console do navegador e não acessível através do JavaScript.

```js
window.onerror = function (msg, url, lineNo, columnNo, error) {
    var string = msg.toLowerCase();
    var substring = "script error";
    if (string.indexOf(substring) > -1){
        alert('Script Error: See Browser Console for Detail');
    } else {
        alert(msg, url, lineNo, columnNo, error);
    }
  return false;
};
```

Quando usamos a marcação HTML inline (`<body onerror="alert('an error occurred')">`), a especificação HTML requer argumentos passados para o `onerror` identificados como `event`, `source`, `lineno`, `colno`, `error`. Os navegadors que não implementam este requerimento, podem ainda serem obtidos por `arguments[0]` até `arguments[2]`.

## Especificações

| Especificação                                                                                    | Status                           | Comentário |
| ------------------------------------------------------------------------------------------------ | -------------------------------- | ---------- |
| {{SpecName('HTML WHATWG','webappapis.html#handler-onerror','onerror')}} | {{Spec2('HTML WHATWG')}} |            |

## Compatibilidade com navegadores

Antes do Firefox 14, quando um {{HTMLElement("script")}} falhava na inicialização, `window.onerror` era invocada com a mensagem **"Error loading script"(erro de leitura de script)**. Isto foi corrigido no {{bug("737087")}}, agora `scriptElement.onerror` é chamado ao invés disto.

Desde o Firefox 31, os últimos 2 argumentos (`colno` and `error`) foram adicionados, o que significa que você tem acesso a pilha de rastreamento de um erro de script através do `window.onerror` por intermédio do `Error` object ({{bug("355430")}}.)

## Veja também

- [Capture e reporte erros JavaScript com window.onerror (blog.getsentry.com, 2016)](http://blog.getsentry.com/2016/01/04/client-javascript-reporting-window-onerror.html)
- [Como capturar erros JavaScript com window.onerror (mesmo no Chrome ou Firefox) (danlimerick.wordpress.com, 2014)](https://danlimerick.wordpress.com/2014/01/18/how-to-catch-javascript-errors-with-window-onerror-even-on-chrome-and-firefox/)
