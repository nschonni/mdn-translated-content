---
title: '<canvas>: グラフィックキャンバス要素'
slug: Web/HTML/Element/canvas
---

{{HTMLSidebar}}

**HTML の `<canvas>` 要素** と [Canvas スクリプティング API](/ja/docs/Web/API/Canvas_API) や [WebGL API](/ja/docs/Web/API/WebGL_API) を使用して、グラフィックやアニメーションを描画することができます。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/HTML/Content_categories">コンテンツカテゴリ</a>
      </th>
      <td>
        <a href="/ja/docs/Web/HTML/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >,
        <a href="/ja/docs/Web/HTML/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >,
        <a href="/ja/docs/Web/HTML/Content_categories#埋め込みコンテンツ"
          >埋め込みコンテンツ</a
        >, 知覚可能コンテンツ
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        透過的コンテンツ、ただし子孫に<a
          href="/ja/docs/Web/HTML/Content_categories#対話型コンテンツ"
          >対話型コンテンツ</a
        >のうち {{HTMLElement("a")}} 要素,
        {{HTMLElement("button")}} 要素, {{HTMLElement("input")}}
        要素の {{htmlattrxref("type", "input")}} 属性が
        <code>checkbox</code>, <code>radio</code>,
        <code>button</code> のいずれか以外を含まないもの
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
      <td>{{domxref("HTMLCanvasElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

他のすべての HTML 要素と同様に、[グローバル属性](/ja/docs/Web/HTML/Global_attributes)を持ちます。

- {{htmlattrdef("height")}}
  - : CSS ピクセルで示した座標空間の高さ。既定では 150 ピクセルに設定されています。
- {{htmlattrdef("moz-opaque")}} {{non-standard_inline}} {{deprecated_inline}}
  - : canvas に半透明性がファクターになるかを知らせます。キャンバスは半透明性がないことがわかっていれば、描画パフォーマンスを最適化できます。これは Mozilla ベースのブラウザーしか対応していません。代わりに標準化された {{domxref("HTMLCanvasElement.getContext()", "canvas.getContext('2d', { alpha: false })")}} を使用してください。
- {{htmlattrdef("width")}}
  - : CSS ピクセルで示した座標空間の幅。既定では 300 ピクセルに設定されています。

## 使用上の注意

### 代替コンテンツ

`<canvas>` のブロックの中で、代替コンテンツを提供することが可能 (また、提供すべき) です。その内容物は、 canvas に対応しない古いブラウザーおよび JavaScript が無効であるブラウザーで描画されます。有用な代替テキストやサブ DOM のヘルプを提供すると、[キャンバスがよりアクセシブルになります](/ja/docs/Web/API/Canvas_API/Tutorial/Hit_regions_and_accessibility)。

### \</canvas> タグが必要

{{HTMLElement("img")}} 要素とは異なり、 {{HTMLElement("canvas")}} 要素は終了タグ (`</canvas>`) が**必要です**。

### CSS と HTML におけるキャンバスの寸法指定の違い

表示されるキャンバスの寸法は、スタイルシートを用いて変更できますが、そうすると画像はスタイルで設定した寸法に合うように拡大縮小され、最終的なグラフィックが歪んで表示されることがあります。

キャンバスの寸法は、 HTML または JavaScript を用いて `width` および `height` 属性を `<canvas>` 要素に直接設定するした方がいいでしょう。

### キャンバスの最大寸法

`<canvas>` 要素の最大寸法はとても広いのですが、正確な寸法はブラウザーに依存します。以下のものは様々なテストやその他の情報源 ([Stack Overflow](https://stackoverflow.com/questions/6081483/maximum-size-of-a-canvas-element) など) から収集したいくらかのデータです。

| ブラウザー | 最大高        | 最大幅        | 最大面積                                    |
| ---------- | ------------- | ------------- | ------------------------------------------- |
| Chrome     | 32,767 pixels | 32,767 pixels | 268,435,456 pixels (つまり 16,384 x 16,384) |
| Firefox    | 32,767 pixels | 32,767 pixels | 472,907,776 pixels (つまり 22,528 x 20,992) |
| Safari     | 32,767 pixels | 32,767 pixels | 268,435,456 pixels (つまり 16,384 x 16,384) |
| IE         | 8,192 pixels  | 8,192 pixels  | ?                                           |

> **メモ:** 寸法や面積の最大値を超えると、キャンバスが使用できなくなります。 — 描画コマンドが動作しなくなります。

## 例

### HTML

このコードスニペットは、 HTML 文書に canvas 要素を追加します。ブラウザーがキャンバスをレンダリングできない場合や、キャンバスを読み込めない場合には、代替テキストが提供されます。

```html
<canvas width="300" height="300">
  キャンバスの表示内容を説明する代替テキストです。
</canvas>
```

### JavaScript

それから JavaScript コード内で {{domxref("HTMLCanvasElement.getContext()")}} を呼び出して描画コンテキストを取得し、キャンバス上に描画を開始します。

```js
const canvas = document.querySelector('canvas');
const ctx = canvas.getContext('2d');
ctx.fillStyle = 'green';
ctx.fillRect(10, 10, 100, 100);
```

### 結果

{{EmbedLiveSample('Examples')}}

## アクセシビリティの考慮

### 代替コンテンツ

`canvas` 要素は単なるビットマップであり、描かれたオブジェクトに関する情報は提供しません。キャンバスのコンテンツには、セマンティック HTML のようなアクセシビリティツールには公開されていません。一般的に、アクセシビリティに配慮したウェブサイトやアプリではキャンバスを使用しないでください。アクセシビリティを改善するには、以下のガイドが役立ちます。

- [MDN ヒット領域とアクセシビリティ](/ja/docs/Web/API/Canvas_API/Tutorial/Hit_regions_and_accessibility)
- [Canvas accessibility use cases](https://www.w3.org/WAI/PF/HTML/wiki/Canvas_Accessibility_Use_Cases)
- [Canvas element accessibility issues](https://www.w3.org/html/wg/wiki/AddedElementCanvas)
- [HTML5 Canvas Accessibility in Firefox 13 – by Steve Faulkner](https://developer.paciellogroup.com/blog/2012/06/html5-canvas-accessibility-in-firefox-13/)
- [Best practices for interactive canvas elements](https://html.spec.whatwg.org/multipage/scripting.html#best-practices)

## 仕様書

| 仕様書                                                                                                                   | 状態                             | 備考     |
| ------------------------------------------------------------------------------------------------------------------------ | -------------------------------- | -------- |
| {{SpecName('HTML WHATWG', 'scripting.html#the-canvas-element', '&lt;canvas&gt;')}}             | {{Spec2('HTML WHATWG')}} |          |
| {{SpecName('HTML5 W3C', 'semantics-scripting.html#the-canvas-element', '&lt;canvas&gt;')}} | {{Spec2('HTML5 W3C')}}     | 初回定義 |

## ブラウザーの互換性

{{Compat("html.elements.canvas")}}

## 関連情報

- [MDN の canvas ポータル](/ja/docs/Web/API/Canvas_API)
- [Canvas チュートリアル](/ja/docs/Web/API/Canvas_API/Tutorial)
- [Canvas チートシート](https://simon.html5.org/dump/html5-canvas-cheat-sheet.html)
- [Canvas に関するデモ](/ja/demos/tag/tech:canvas)
- [Apple によるキャンバスの紹介](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/HTML-canvas-guide/Introduction/Introduction.html)
