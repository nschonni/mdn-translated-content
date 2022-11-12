---
title: '<body>: 文書の本文要素'
slug: Web/HTML/Element/body
---

{{HTMLSidebar}}

**`<body>`** は [HTML](/ja/docs/Web/HTML) の要素で、 HTML 文書のコンテンツを示す要素です。 `<body>` 要素は文書中に一つだけ配置できます。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/Guide/HTML/Content_categories"
          >コンテンツカテゴリー</a
        >
      </th>
      <td>
        <a href="/ja/docs/Web/HTML/Element/Heading_Elements#sectioning_roots"
          >区分化ルート</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>
        開始タグは、内容の先頭が空白文字、コメント、 {{HTMLElement("script")}} 要素、 {{HTMLElement("style")}} 要素でない場合は省略可能です。終了タグは、 <code>&#x3C;body></code> 要素に内容または開始タグがあり、かつ、直後のノードがコメントでない場合は省略可能です。
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>
        {{HTMLElement("html")}} 要素の子要素でなければなりません。
      </td>
    </tr>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <code
          ><a href="/ja/docs/Web/Accessibility/ARIA/Roles/Generic_role"
            >generic</a
          ></code
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている ARIA ロール</th>
      <td>許可されている <code>role</code> なし</td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>
        {{domxref("HTMLBodyElement")}}
        <ul>
          <li>
            <code>&#x3C;body></code> 要素は {{domxref("HTMLBodyElement")}} インターフェイスを提供します。
          </li>
          <li>
            <code>&#x3C;body></code> 要素は {{domxref("document.body")}} プロパティからアクセス可能です。
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## 属性

この要素には[グローバル属性](/ja/docs/Web/HTML/Global_attributes)があります。

- {{htmlattrdef("alink")}} {{deprecated_inline}}
  - : ハイパーリンクの選択時の文字色です。**この属性を使用しないでください。代わりに CSS の {{cssxref("color")}} プロパティを {{cssxref(":active")}} 擬似クラスで使用してください。**
- {{htmlattrdef("background")}} {{deprecated_inline}}
  - : 背景画像の URI です。**この属性を使用しないでください。代わりに CSS の {{cssxref("background")}} プロパティを使用してください。**
- {{htmlattrdef("bgcolor")}} {{deprecated_inline}}
  - : 文書の背景色です。**この属性を使用しないでください。代わりに CSS の {{cssxref("background-color")}} プロパティを使用してください。**
- {{htmlattrdef("bottommargin")}} {{deprecated_inline}}
  - : body の下マージンです。**この属性を使用しないでください。代わりに CSS の {{cssxref("margin-bottom")}} プロパティを使用してください。**
- {{htmlattrdef("leftmargin")}} {{deprecated_inline}}
  - : body の左マージンです。**この属性を使用しないでください。代わりに CSS の {{cssxref("margin-left")}} プロパティを使用してください。**
- {{htmlattrdef("link")}} {{deprecated_inline}}
  - : 未訪問のハイパーリンクの文字色です。**この属性を使用しないでください。代わりに CSS の {{cssxref("color")}} プロパティを {{cssxref(":link")}} 擬似クラスで使用してください。**
- {{htmlattrdef("onafterprint")}}
  - : ユーザーによる印刷データ作成直後に呼び出す関数
- {{htmlattrdef("onbeforeprint")}}
  - : ユーザーによるブラウザーへの印刷指示直後に呼び出す関数
- {{htmlattrdef("onbeforeunload")}}
  - : 文書のアンロードの直前に呼び出す関数
- {{htmlattrdef("onblur")}}
  - : 文書からフォーカスが外されたときに呼び出す関数
- {{htmlattrdef("onerror")}}
  - : 文書を正常にロードできなかった際に呼び出す関数
- {{htmlattrdef("onfocus")}}
  - : 文書にフォーカスが当たった際に呼び出す関数
- {{htmlattrdef("onhashchange")}}
  - : 文書の現在のアドレスのフラグメント識別子 (ハッシュ文字 `'#'` から始まる部分) が変更された際に呼び出す関数
- {{htmlattrdef("onlanguagechange")}}
  - : 言語が変更された際に呼び出す関数
- {{htmlattrdef("onload")}}
  - : 文書の読み込み完了時に呼び出す関数
- {{htmlattrdef("onmessage")}}
  - : 文書が API からメッセージを受信した際に呼び出す関数
- {{htmlattrdef("onoffline")}}
  - : ネットワークとの交信が不能になった際に呼び出す関数
- {{htmlattrdef("ononline")}}
  - : ネットワークとの交信が発生あるいは回復した際に呼び出す関数
- {{htmlattrdef("onpopstate")}}
  - : ユーザーによるセッション履歴のナビゲート時に呼び出す関数
- {{htmlattrdef("onredo")}}
  - : ユーザーがトランザクション履歴を元に戻した際に呼び出す関数
- {{htmlattrdef("onresize")}}
  - : 文書を表示するウィンドウがリサイズされた際に呼び出す関数
- {{htmlattrdef("onstorage")}}
  - : ストレージ領域が変化した際に呼び出す関数
- {{htmlattrdef("onundo")}}
  - : ユーザーがトランザクション履歴をさかのぼることによって後方へ移動した際に呼び出す関数
- {{htmlattrdef("onunload")}}
  - : 文書からの離脱時に呼び出す関数
- {{htmlattrdef("rightmargin")}} {{deprecated_inline}}
  - : body の右マージンです。**この属性を使用しないでください。代わりに CSS の {{cssxref("margin-right")}} プロパティを使用してください。**
- {{htmlattrdef("text")}} {{deprecated_inline}}
  - : 基本文字色です。**この属性を使用しないでください。代わりに CSS の {{cssxref("color")}} プロパティを使用してください。**
- {{htmlattrdef("topmargin")}} {{deprecated_inline}}
  - : body の上マージンです。**この属性を使用しないでください。代わりに CSS の {{cssxref("margin-top")}} プロパティを使用してください。**
- {{htmlattrdef("vlink")}} {{deprecated_inline}}
  - : 訪問済みのハイパーリンクの文字色です。**この属性を使用しないでください。代わりに CSS の {{cssxref(":visited")}} 擬似クラスで {{cssxref("color")}} プロパティを使用してください。**

## 例

```html
<html>
  <head>
    <title>Document title</title>
  </head>
  <body>
    <p>This is a paragraph</p>
  </body>
</html>
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- {{HTMLElement("html")}}
- {{HTMLElement("head")}}
