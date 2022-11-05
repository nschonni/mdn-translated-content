---
title: display
slug: Web/CSS/display
---
{{CSSRef}}

## Resumo

A propriedade CSS `display` especifica o tipo de caixa de renderização usada por um elemento. No HTML, os valores padrões da propriedade `display` são feitas a partir do comportamento descrito nas especificações HTML ou da folha de estilo padrão do navegador/usuário. O valor padrão em XML é inline.

Além dos muitos tipos diferentes de exibição de caixa, o valor `none` permite desativar a exibição de um elemento; quando você usa `none`, todos os elementos descendentes também tem a sua exibição desativada. O documento é renderizado como se o elemento não existisse na árvore do documento.

{{cssinfo}}

## Sintaxe

```
Sintaxe formal: {{csssyntax("display")}}
```

```
display: none

display: inline
display: block
display: list-item
display: inline-block
display: inline-table
display: table
display: table-cell
display: table-column
display: table-column-group
display: table-footer-group
display: table-header-group
display: table-row
display: table-row-group
display: flex
display: inline-flex
display: grid
display: inline-grid
display: run-in

display: inherit
```

### Valores

_**display-value**_

É a palavra-chave para definir tipo de renderização que será usada no elemento. Os valores possiveis e seus significados são:

<table class="standard-table" style="width: 100%">
  <thead>
    <tr>
      <td class="header" colspan="1">Value set</td>
      <td class="header">Value</td>
      <td class="header">Description</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="1" rowspan="4">Valores Básicos (CSS 1)</td>
      <td><code>none</code></td>
      <td>
        <p>
          Desabilita a exibição do elemento (sem afetar o layout); todos os
          elementos filhos também tem sua exibição desabilitada. O documento é
          renderizado como se o elemento não existisse.
        </p>
        <p>
          Para renderizar as dimensões de caixa do elemento, tendo ainda seu
          conteúdo "invisivel", veja a propriedade
          {{cssxref("visibility")}}.
        </p>
      </td>
    </tr>
    <tr>
      <td><code>inline</code></td>
      <td>O elemento gera uma ou mais caixas de elementos inline.</td>
    </tr>
    <tr>
      <td><code>block</code></td>
      <td>O elemento gera uma caixa de elemento de bloco.</td>
    </tr>
    <tr>
      <td><code>list-item</code></td>
      <td>
        O elemento gera uma caixa de bloqueio para o conteúdo e uma caixa
        embutida de item de lista separada.
      </td>
    </tr>
    <tr>
      <td>Valores estendidos(CSS 2.1)</td>
      <td><code>inline-block</code></td>
      <td>
        O elemento gera uma caixa de elemento de bloco que fluirá com o conteúdo
        circundante, como se fosse uma única caixa embutida (se comportando como
        um elemento substituído)
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="10">Valores do modelo de tabela(CSS 2.1)</td>
      <td><code>inline-table</code></td>
      <td>
        O<code> inline-table </code>O valor não possui um mapeamento direto em
        HTML. Se comporta como um{{HTMLElement("table")}} HTML elemento,
        mas como uma caixa embutida, em vez de uma caixa no nível do bloco.
        Dentro da caixa da tabela há um contexto em nível de bloco.
      </td>
    </tr>
    <tr>
      <td><code>table</code></td>
      <td>
        Comporta-se como o{{HTMLElement("table")}} HTML elemento. Ele
        define uma caixa no nível do bloco.
      </td>
    </tr>
    <tr>
      <td><code>table-caption</code></td>
      <td>
        Comporta-se como o{{HTMLElement("caption")}} HTML elemento.
      </td>
    </tr>
    <tr>
      <td><code>table-cell</code></td>
      <td>Comporta-se como o {{HTMLElement("td")}} HTML elemento</td>
    </tr>
    <tr>
      <td><code>table-column</code></td>
      <td>
        Esses elementos se comportam como o correspondente
        {{HTMLElement("col")}} HTML elementos.
      </td>
    </tr>
    <tr>
      <td><code>table-column-group</code></td>
      <td>
        Esses elementos se comportam como o
        correspondente{{HTMLElement("colgroup")}} HTML elementos.
      </td>
    </tr>
    <tr>
      <td><code>table-footer-group</code></td>
      <td>
        Esses elementos se comportam como o correspondente
        {{HTMLElement("tfoot")}} HTML elementos
      </td>
    </tr>
    <tr>
      <td><code>table-header-group</code></td>
      <td>
        Esses elementos se comportam como o
        correspondente{{HTMLElement("thead")}} HTML elementos
      </td>
    </tr>
    <tr>
      <td><code>table-row</code></td>
      <td>Comporta-se como o {{HTMLElement("tr")}} HTML elemento</td>
    </tr>
    <tr>
      <td><code>table-row-group</code></td>
      <td>
        Esses elementos se comportam como o correspondente
        {{HTMLElement("tbody")}} HTML elementos
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="2">
        Valores do modelo Flexbox (<a href="/pt-BR/docs/CSS/CSS3"
          >CSS3</a
        >)
      </td>
      <td><code>flex</code></td>
      <td>
        O elemento se comporta como um elemento de bloco e apresenta seu
        conteúdo de acordo com o modelo flexbox.
      </td>
    </tr>
    <tr>
      <td><code>inline-flex</code></td>
      <td>
        O elemento se comporta como um elemento embutido e apresenta seu
        conteúdo de acordo com o modelo flexbox.
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="2">
        Valores do modelo de caixa de grade (<a
          href="/pt-BR/docs/CSS/CSS3"
          >CSS3</a
        >) {{experimental_inline}}
      </td>
      <td><code>grid</code></td>
      <td>
        <p>
          O elemento se comporta como um elemento de bloco e apresenta seu
          conteúdo de acordo com o modelo de grade.
        </p>
        <div class="note">
          Como isso é experimental, a maioria dos navegadores não suporta.
          Preste atenção especialmente que <code>-moz-grid</code> não é a versão
          prefixada disso, mas um modelo de layout XUL que não deve ser usado em
          um site.
        </div>
      </td>
    </tr>
    <tr>
      <td><code>inline-grid</code></td>
      <td>
        O elemento se comporta como um elemento embutido e apresenta seu
        conteúdo de acordo com o modelo de grade.
      </td>
    </tr>
    <tr>
      <td>Valores experimentais {{experimental_inline}}</td>
      <td><code>run-in</code></td>
      <td>
        <ul>
          <li>
            Se a caixa de entrada contiver uma caixa de bloco, o mesmo que
            bloco.
          </li>
          <li>
            Se uma caixa de bloco segue a caixa de introdução, a caixa de
            introdução torna-se a primeira caixa embutida da caixa de bloco.
          </li>
          <li>
            Se uma caixa embutida se seguir, a caixa de introdução se tornará
            uma caixa de bloco.
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Exemplos

[Ver exemplos ao vivo](/samples/cssref/display.html)

```css
p.secret  { display: none }
<p style="display:none"> invisible text </p>
```

## Especificações

| Specification                                                                        | Status                           | Comment                                                            |
| ------------------------------------------------------------------------------------ | -------------------------------- | ------------------------------------------------------------------ |
| {{SpecName('CSS3 Box', '#display', 'display')}}                     | {{Spec2('CSS3 Box')}}     | Adicionado o `run-in` valor.                                       |
| {{SpecName('CSS3 Grid', '#grid-declaration0', 'display')}}         | {{Spec2('CSS3 Grid')}}     | Adicionado os valores do modelo da caixa de grade.                 |
| {{SpecName('CSS3 Flexbox', '#flex-containers', 'display')}}     | {{Spec2('CSS3 Flexbox')}} | Adicionado os valores do modelo de caixa flexível.                 |
| {{SpecName('CSS2.1', 'visuren.html#display-prop', 'display')}} | {{Spec2('CSS2.1')}}         | Foram adicionados os valores do modelo de tabela e `inline-block`. |
| {{SpecName('CSS1', '#display', 'display')}}                             | {{Spec2('CSS1')}}         | Valores básicos: `none`, `block`, `inline`, e `list-item`.          |

## Navegadores compatíveis

{{Compat("css.properties.display")}}

## Veja mais

- {{Cssxref("visibility")}}, {{Cssxref("float")}}, {{Cssxref("position")}}
