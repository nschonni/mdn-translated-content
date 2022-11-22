---
title: Storage.key()
slug: Web/API/Storage/key
---

{{APIRef}}

{{domxref("Storage")}} インターフェイスの `key()` メソッドは数値 n を渡すと、ストレージ内で n 番目のキーの名称を返します。キーの順序はユーザエージェント依存であり、この順序に頼るべきではありません。

## 構文

```js
var aKeyName = storage.key(index);
```

### 引数

- `index`
  - : 名称を取得したいキーの番号を表す整数。これは 0 から始まるインデックスです。

### 返値

キーの名称を持つ {{domxref("DOMString")}}。該当のインデックスが存在しない場合は `null` が返ります。

## 例

以下の関数は、ローカルストレージのキー全体に対して反復処理を行います。

```js
function forEachKey(callback) {
  for (var i = 0; i < localStorage.length; i++) {
    callback(localStorage.key(i));
  }
}
```

> **メモ:** 実際の例として、[Web Storage Demo](https://github.com/mdn/web-storage-demo) をご覧ください。

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat("api.Storage.key")}}

## 関連情報

- [Web Storage API を使用する](/ja/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API)
