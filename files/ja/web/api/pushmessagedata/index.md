---
title: PushMessageData
slug: Web/API/PushMessageData
---

{{APIRef("Push API")}}{{SeeCompatTable()}}

[Push API](/ja/docs/Web/API/Push_API) の **`PushMessageData`** インターフェイスは、さまざまなフォーマットでサーバーから送信されるプッシュテータを取得する方法を提供します。

[Fetch API](/ja/docs/Web/API/Fetch_API) の同様のメソッドが 1 回しか呼び出せないのと異なり、これらは複数回呼び出せます。

Push API を通して受け取ったメッセージはプッシュサービスによって暗号化されて送信され、`PushMessageData` インターフェースのメソッドで利用可能になる前にブラウザーによって自動的に 復号化されます。

## インスタンスプロパティ

なし。

## インスタンスメソッド

- {{domxref("PushMessageData.arrayBuffer()")}}
  - : データを {{jsxref("ArrayBuffer")}} オブジェクトとして抜き出します。
- {{domxref("PushMessageData.blob()")}}
  - : データを {{domxref("Blob")}} オブジェクトとして抜き出します。
- {{domxref("PushMessageData.json()")}}
  - : データを [JSON](/ja/docs/Web/JavaScript/Reference/Global_Objects/JSON) オブジェクトとして抜き出します。
- {{domxref("PushMessageData.text()")}}
  - : データをプレーンテキスト文字列として抜き出します。

## 例

```js
self.addEventListener('push', function(event) {
  var obj = event.data.json();

  if(obj.action === 'subscribe' || obj.action === 'unsubscribe') {
    fireNotification(obj, event);
    port.postMessage(obj);
  } else if(obj.action === 'init' || obj.action === 'chatMsg') {
    port.postMessage(obj);
  }
});
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat("api.PushMessageData")}}
