---
title: <ins>
slug: Web/HTML/Element/ins
---

{{HTMLSidebar}}

**HTML の `<ins>` 要素**は、文書に追加されたテキストの範囲を表します。同様に、 {{HTMLElement("del")}} 要素を使用して文書から削除されたテキストの範囲を表すことができます。

{{EmbedInteractiveExample("pages/tabbed/ins.html", "tabbed-standard")}}

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/HTML/Content_categories">コンテンツカテゴリ</a>
      </th>
      <td>
        <a href="/ja/docs/Web/HTML/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >
        または
        <a href="/ja/docs/Web/HTML/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        <a href="/ja/docs/Web/HTML/Content_categories#透過的コンテンツ"
          >透過的コンテンツ</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>{{no_tag_omission}}</td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>
        <a href="/ja/docs/Web/HTML/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >を受け入れるすべての要素
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
      <td>すべて</td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLModElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

他のすべての HTML 要素と同様に、この要素は[グローバル属性](/ja/docs/Web/HTML/Global_attributes)を持っています。

- {{htmlattrdef("cite")}}
  - : 会議の議事録やトラブルシューティングシステムのチケットといった、追加についての説明を記したリソースへの URI を示します。
- {{htmlattrdef("datetime")}}
  - : この属性は変更が行われた日時を示し、有効な日付または日時の文字列でなければなりません。値が日付または日時の文字列として解釈できなかった場合は、要素にタイムスタンプが関連付けられなくなります。時刻がない日付の書式については、[妥当な日付文字列の書式](/ja/docs/Web/HTML/Date_and_time_formats#Date_strings)を参照してください。日付と時刻の両方を含む場合の文字列の書式については、[妥当な日時文字列の書式](/ja/docs/Web/HTML/Date_and_time_formats#Local_date_and_time_strings)を参照してください。

## 例

```html
<ins>This text has been inserted</ins>
```

### 結果

{{EmbedLiveSample("Examples")}}

## アクセシビリティの考慮

`<ins>` 要素が存在することは、多くの読み上げ技術の既定の設定では読み上げられません。 CSS の {{cssxref("content")}} プロパティを {{cssxref("::before")}} および {{cssxref("::after")}} 擬似要素と共に使うことで読み上げさせることができます。

```css
ins::before,
ins::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

ins::before {
  content: " [挿入開始] ";
}

ins::after {
  content: " [挿入終了] ";
}
```

読み上げソフトを使用する人によっては、特に冗長になるコンテンツのアナウンスを意図的に無効にしていることがあります。このため、この手法を悪用しないようにすることは重要であり、コンテンツが挿入されていることを知らないと理解に影響するような場面でのみ使用するようにしてください。

- [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
- [Tweaking Text Level Styles | Adrian Roselli](http://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

## 仕様書

| 仕様書                                                                                           | 状態                             | 備考 |
| ------------------------------------------------------------------------------------------------ | -------------------------------- | ---- |
| {{SpecName('HTML WHATWG', 'edits.html#the-ins-element', '&lt;ins&gt;')}} | {{Spec2('HTML WHATWG')}} |      |
| {{SpecName('HTML5 W3C', 'edits.html#the-ins-element', '&lt;ins&gt;')}}     | {{Spec2('HTML5 W3C')}}     |      |
| {{SpecName('HTML4.01', 'struct/text.html#h-9.4', '&lt;ins&gt;')}}         | {{Spec2('HTML4.01')}}     |      |

## ブラウザーの互換性

{{Compat("html.elements.ins")}}

## 関連情報

- 文書の削除された部分に印をつける {{HTMLElement("del")}} 要素
