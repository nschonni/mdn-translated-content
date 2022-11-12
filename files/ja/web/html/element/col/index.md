---
title: <col>
slug: Web/HTML/Element/col
---

{{HTMLSidebar}}

**HTML の `<col>` 要素**は、表内の列を定義して、すべての一般セルに共通の意味を定義するために使用します。この要素は通常、 {{HTMLElement("colgroup")}} 要素内にみられます。

{{EmbedInteractiveExample("pages/tabbed/col.html","tabbed-taller")}}

`<col>` では CSS を使用して列にスタイルを設定できますが、列に対して効果があるプロパティは限定されています ([CSS 2.1 仕様書](https://www.w3.org/TR/CSS21/tables.html#columns) をご覧ください)。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/HTML/Content_categories">コンテンツカテゴリ</a>
      </th>
      <td>なし</td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        なし。これは{{Glossary("empty element", "空要素")}}です。
      </td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>開始タグは必須ですが、終了タグを置いてはいけません。</td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>
        {{HTMLElement("colgroup")}}
        のみ。ただし開始タグが必須ではないため暗黙的に定義されることがあります。
        {{HTMLElement("colgroup")}} 要素は
        {{htmlattrxref("span", "colgroup")}}
        属性を持っていてはいけません。
      </td>
    </tr>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role"
          >対応するロールなし</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている ARIA ロール</th>
      <td>許可されている <code>role</code> なし</td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLTableColElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

この要素には[グローバル属性](/ja/docs/Web/HTML/Global_attributes)があります。

- {{htmlattrdef("span")}}
  - : この属性は正の整数で、 `<col>` 要素がまたがる列の数を示します。存在しない場合、既定値は `1` です。

### 非推奨の属性

以下の属性は非推奨であり、使用すべきではありません。これらの属性は、既存のコードを更新する際の参考として、また歴史的な興味のためだけに、以下に文書化されています。

- {{htmlattrdef("align")}} {{deprecated_inline}}

  - : この列挙属性は、各列の内容物の水平方向の配置方法を制御します。以下の値が指定可能です。

    - `left` : 内容物をセルの左側に揃えます。
    - `center` : 内容物をセル内で中央揃えにします。
    - `right` : 内容物をセルの右側に揃えます。
    - `justify`: 内容物がセル内で両端揃えになるように、テキストコンテンツに空白を挿入します。

    この属性が設定されていない場合、その値は `<col>` 要素が属する {{HTMLElement("colgroup")}} 要素の {{htmlattrxref("align", "colgroup")}} 属性から継承します。それも存在しない場合は、`left` 値であるものとします。

    > **補足:**
    >
    > - 値 `left`、`center`、`right`、`justify` と同じ効果を得る方法:
    > - {{cssxref("text-align")}} プロパティを `<col>` 要素を与えたセレクターに設定しようとしてはいけません。 {{HTMLElement("td")}} 要素は `<col>` 要素の子孫ではないため、プロパティを継承しません。
    > - 表で {{htmlattrxref("colspan", "td")}} 属性を使用していない場合は、`td:nth-child(an+b)` CSS セレクターを使用してください。 `a` を 0 に、`b` を表内の列の位置を示す序数にします。例えば `td:nth-child(2) { text-align: right; }` は、2 列目を右揃えにします。
    > - 表で {{htmlattrxref("colspan", "td")}} 属性を使用している場合は `[colspan=n]` のような、十分な CSS 属性セレクターの組み合わせで実現できますが、容易ではありません。

- {{htmlattrdef("bgcolor")}} {{Deprecated_inline}}

  - : 表の背景色です。この属性は、列の各セルの背景色を定義します。 [6 桁の 16 進数の RGB コード](/ja/docs/Web/CSS/color_value#RGB_colors)の前に '`#`' が付いた形です。定義済みの[色キーワード](/ja/docs/Web/CSS/color_value#Color_keywords)のうちの一つも使用できます。

    同様の効果を得るには、 CSS の {{cssxref("background-color")}} プロパティを使用してください。

- {{htmlattrdef("char")}} {{deprecated_inline}}
  - : この属性は、列内のセルで揃える文字を設定します。よく使用する値としては、数値や金額を揃えるときのピリオド (.) があります。 {{htmlattrxref("align", "col")}} 属性が `char` ではない場合は、この属性は無視されます。
- {{htmlattrdef("charoff")}} {{deprecated_inline}}
  - : この属性は、 `char` 属性で指定された揃え文字からその列のデータをオフセットする文字数を示します。
- {{htmlattrdef("valign")}} {{deprecated_inline}}

  - : この属性は、その列のそれぞれのセルの中にある内容物の垂直方向の配置方法を指定します。以下の値が指定可能です。

    - `baseline` : テキストを可能な限りセルの下端に近づけますが、下端ではなく文字の[ベースライン](https://en.wikipedia.org/wiki/Baseline_%28typography%29)に揃えます。文字がサイズ全体に渡る場合は、 `bottom` と同じ効果になります。
    - `bottom` : テキストを可能な限りセルの下端に近づけて配置します。
    - `middle` : テキストをセルの中央部に置きます。
    - and `top` : テキストを可能な限りセルの上端に近づけて配置します。

    > **メモ:** **補足:**- {{cssxref("vertical-align")}} プロパティを、 `<col>` 要素を与えたセレクターに設定しようとしてはいけません。{{HTMLElement("td")}} 要素は `<col>` 要素の子孫ではないため、プロパティを継承しません。
    >
    > - 表で {{htmlattrxref("colspan", "td")}} 属性を使用していない場合は、 CSS の `td:nth-child(an+b)` セレクターを使用してください。a は表内の列数、b は表内の列の位置を示す序数です。このセレクターの後でのみ `vertical-align` プロパティを使用することができます。
    > - 表で {{htmlattrxref("colspan", "td")}} 属性を使用している場合は `[colspan=n]` のような、十分な CSS 属性セレクターの組み合わせで実現できますが、容易ではありません。

- {{htmlattrdef("width")}} {{deprecated_inline}}
  - : この属性は、現在の列グループ内の各列に既定の幅を指定します。標準的なピクセル値やパーセント値に加えて、この属性は特別な書式である `0*` も使用できます。これはグループ内の各列の幅を、列の内容物を保持するのに必要最小限の幅にします。`5*` のような幅の相対値も使用できます。

## 例

{{HTMLElement("table")}} ページに `<col>` 要素の使用例があります。

## 仕様書

| 仕様書                                                                                                   | 状態                             | 備考     |
| -------------------------------------------------------------------------------------------------------- | -------------------------------- | -------- |
| {{SpecName('HTML WHATWG', 'tables.html#the-col-element', '&lt;col&gt;')}}         | {{Spec2('HTML WHATWG')}} |          |
| {{SpecName('HTML5 W3C', 'tabular-data.html#the-col-element', '&lt;col&gt;')}} | {{Spec2('HTML5 W3C')}}     |          |
| {{SpecName('HTML4.01', 'struct/tables.html#h-11.2.4.2', '&lt;col&gt;')}}         | {{Spec2('HTML4.01')}}     | 初回定義 |

## ブラウザーの互換性

{{Compat("html.elements.col")}}

## 関連情報

- `<col>` 要素のスタイル設定に特に役立つであろう CSS プロパティと擬似クラス:

  - 列の幅を制御するための {{cssxref("width")}} プロパティ
  - 列内のセルの配置を設定するための {{cssxref(":nth-child")}} 擬似クラス
  - すべてのセル内コンテンツを '.' などの同一文字で揃えるための {{cssxref("text-align")}} プロパティ
