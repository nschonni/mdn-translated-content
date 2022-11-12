---
title: '<td>: 表データセル要素'
slug: Web/HTML/Element/td
---

{{HTMLSidebar}}

**`<td>`** は [HTML](/ja/docs/Web/HTML) の要素で、表でデータを包含するセルを定義します。これは*モデル*に関与します。

{{EmbedInteractiveExample("pages/tabbed/td.html","tabbed-taller")}}

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/Guide/HTML/Content_categories"
          >コンテンツカテゴリー</a
        >
      </th>
      <td>区分化ルート</td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#フローコンテンツ">フローコンテンツ</a>
      </td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>
        開始タグは必須です。<br>直後に {{HTMLElement("th")}} 要素または {{HTMLElement("td")}} 要素がある場合、または親要素内で以降のデータがない場合は終了タグを省略可能。
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>{{HTMLElement("tr")}} 要素</td>
    </tr>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <code
          ><a href="/ja/docs/Web/Accessibility/ARIA/Roles/Cell_Role"
            >cell</a
          ></code
        > ({{HTMLElement("table")}} 要素の子孫である場合)
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている ARIA ロール</th>
      <td>すべて</td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLTableCellElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

この要素には[グローバル属性](/ja/docs/Web/HTML/Global_attributes)があります。

- {{htmlattrdef("colspan")}}
  - : この属性はセルをいくつの列に広げるかを示す、負でない整数を持ちます。既定値は `1` です。1000 を超える値は正しくないとみなされ、既定値 (1) が設定されるでしょう。
- {{htmlattrdef("headers")}}
  - : この属性は、空白文字で区切られた文字列のリストを持ちます。各々の文字列は、この要素に当てはめる {{HTMLElement("th")}} 要素の **id** 属性と対応します。
- {{htmlattrdef("rowspan")}}
  - : この属性はセルをいくつの行に広げるかを示す、負でない整数を持ちます。既定値は `1` です。`0` を設定した場合は、セルが属する表セクション ({{HTMLElement("thead")}}, {{HTMLElement("tbody")}}, {{HTMLElement("tfoot")}}) の終端 (暗黙的に定義されるものであっても) まで拡張します。65534 より大きな値は、65534 に切り詰めます。

### 非推奨の属性

- {{htmlattrdef("abbr")}} {{deprecated_inline}}

  - : この属性は、セルの内容の簡潔な説明を持ちます。読み上げソフトなど一部のユーザーエージェントは、内容自体の前にこの説明を提供することがあります。

    > **メモ:** この属性は最新の標準で廃止されているため、使用しないでください。あるいは、省略した説明をセル内に置き、長い内容を **title** 属性に置くこともできます。

- {{htmlattrdef("align")}} {{deprecated_inline}}

  - : この列挙属性は各セルの中身について、水平方向の配置方法を制御します。以下の値を指定可能です。

    - `left`: 中身をセルの左側に揃えます。
    - `center`: 中身をセル内で中央揃えにします。
    - `right`: 中身をセルの右側に揃えます。
    - `justify` (テキストのみ): 中身がセル内で両端揃えになるように、テキストコンテンツに空白を挿入します。
    - `char` (テキストのみ): テキストコンテンツを特定の文字に対して、最小のオフセットで揃えます。特定の文字は {{htmlattrxref("char", "td")}} 属性および {{htmlattrxref("charoff", "td")}} 属性で定義します。{{unimplemented_inline(2212)}}

    この属性を設定しない場合は、値が `left` であるとみなされます。

    > **メモ:**
    >
    > - `left`, `center`, `right`, `justify` の値と同様の効果を得るには、 CSS の {{cssxref("text-align")}} プロパティを使用してください。
    > - 同様の効果を得るには、 {{cssxref("text-align")}} プロパティの値 {{htmlattrxref("char", "td")}} を使用できます。 CSS3 では {{unimplemented_inline}} です。

- {{htmlattrdef("axis")}} {{deprecated_inline}}
  - : この属性は、空白文字で区切られた文字列のリストを持ちます。各文字列は、このヘッダーを適用するセルグループの `id` です。
- {{htmlattrdef("bgcolor")}} {{deprecated_inline}}

  - : この属性は、列の各セルの背景色を定義します。値は [sRGB](https://www.w3.org/Graphics/Color/sRGB) で定義された 6桁の 16 進数値のいずれかで、先頭に '`#`' が付きます。定義済みの[色キーワード](/ja/docs/Web/CSS/color_value#color_keywords)の一つを使うこともできます。

    同様の効果を与えるには、 CSS の {{ cssxref("background-color") }} プロパティを使用してください。

- {{htmlattrdef("char")}} {{deprecated_inline}}
  - : この属性は、列内のセルで揃える文字を設定します。典型的な値に、数値や金額を揃えようとするときのピリオド (.) があります。 {{htmlattrxref("align", "td")}} 属性が `char` に設定されていない場合、この属性は無視されます。
- {{htmlattrdef("charoff")}} {{deprecated_inline}}
  - : この属性は、 **char** 属性で指定した揃え文字から列のデータをオフセットする文字数を示します。
- {{htmlattrdef("height")}} {{deprecated_inline}}
  - : この属性はセルの高さの推奨値を定義するために使用されます。代わりの CSS の {{cssxref("height")}} プロパティを使用してください。
- {{htmlattrdef("scope")}} {{deprecated_inline}}
  - : これは列挙型の属性で、この ({{HTMLElement("th")}} で定義されている) 見出し要素が関連するセルを定義します。この属性は `<th>` 要素のみに、行と列のどちらの見出しであるかを定義するために使用してください。
- {{htmlattrdef("valign")}} {{deprecated_inline}}

  - : この属性は、表本体の各行のセルにおける垂直方向のテキスト配置方法を指定します。以下の値が指定可能です。

    - `baseline`: テキストを可能な限りセルの下端に近づけますが、下端ではなく文字の[ベースライン](https://en.wikipedia.org/wiki/Baseline_%28typography%29)に揃えます。文字がサイズ全体に渡る場合は、 `bottom` と同じ効果になります。
    - `bottom`: テキストを可能な限りセルの下端に近づけて配置します。
    - `middle`: テキストをセル内の中央に置きます。
    - `top`: テキストを可能な限りセルの上端に近づけて配置します。

    同様の効果を実現するには、代わりに CSS の {{cssxref("vertical-align")}} プロパティを使用してください。

- {{htmlattrdef("width")}} {{deprecated_inline}}
  - : この属性は、セルの推奨する幅を定義します。代わりに CSS の {{cssxref("width")}} プロパティを使用してください。

## 例

`<td>` 要素の例については、 {{HTMLElement("table")}} を参照してください。

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}
