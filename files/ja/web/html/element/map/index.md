---
title: '<map>: イメージマップ要素'
slug: Web/HTML/Element/map
---

{{HTMLSidebar}}

**`<map>`** は [HTML](/ja/docs/Web/HTML) の要素で、イメージマップ（クリック可能なリンク領域）を定義するために {{HTMLElement("area")}} 要素とともに使用します。

{{EmbedInteractiveExample("pages/tabbed/map.html", "tabbed-standard")}}

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/Guide/HTML/Content_categories">コンテンツカテゴリー</a>
      </th>
      <td>
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#フローコンテンツ">フローコンテンツ</a>、
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#記述コンテンツ">記述コンテンツ</a>、
        知覚可能コンテンツ
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        すべての<a href="/ja/docs/Web/Guide/HTML/Content_categories#透過的コンテンツ">透過的</a>要素
      </td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>{{no_tag_omission}}</td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#記述コンテンツ">記述コンテンツ</a>を受け入れるすべての要素
      </td>
    </tr>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">対応するロールなし</a>
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている ARIA ロール</th>
      <td>許可されている <code>role</code> なし</td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLMapElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

この要素は[グローバル属性](/ja/docs/Web/HTML/Global_attributes)を持っています。

- {{htmlattrdef("name")}}
  - : `name` 属性は、マップを参照できるようにするための名前を指定します。この属性は必ず存在する必要があり、空白文字を含まない空でない値を持たなければなりません。 `name` 属性の値は、同じ文書内の他の `<map>` 要素の `name` 属性の値と同じであってはいけません。もし {{htmlattrxref("id")}} 属性も指定されている場合は、両方の属性が同じ値でなければなりません。

## 例

### 2 つの領域があるイメージマップ

左側のオウムをクリックすると JavaScript に、右のオウムをクリックすると CSS に飛びます。

#### HTML

```html
<!-- Photo by Juliana e Mariana Amorim on Unsplash -->
<map name="primary">
  <area shape="circle" coords="75,75,75"
        href="https://developer.mozilla.org/docs/Web/JavaScript"
        target="_blank" >
  <area shape="circle" coords="275,75,75"
        href="https://developer.mozilla.org/docs/Web/CSS"
        target="_blank" >
</map>
<img usemap="#primary" src="/en-us/docs/Web/HTML/Element/map/parrots.jpg" alt="350 x 150 pic">
```

#### 結果

{{ EmbedLiveSample('Image map with two areas', '', '250') }}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- {{HTMLElement("a")}}
- {{HTMLElement("area")}}
