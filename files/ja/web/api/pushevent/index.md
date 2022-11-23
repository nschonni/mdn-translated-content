---
title: PushEvent
slug: Web/API/PushEvent
---

{{APIRef("Push API")}}{{SeeCompatTable()}}

[Push API](/ja/docs/Web/API/Push_API) の **`PushEvent`** インターフェイスは、受け取ったプッシュメッセージを表します。このイベントは、{{domxref("ServiceWorker")}} の [グローバルスコープ](/ja/docs/Web/API/ServiceWorkerGlobalScope)に送信されます。これは、アプリケーションサーバーから {{domxref("PushSubscription")}} に送信された情報を含みます。

## コンストラクター

- {{domxref("PushEvent.PushEvent()")}}
  - : 新しい `PushEvent` オブジェクトを生成します。

## インスタンスプロパティ

_親である {{domxref("ExtendableEvent")}} からプロパティを継承しています。追加プロパティ：_

- {{domxref("PushEvent.data")}} {{readonlyinline}}
  - : {{domxref("PushSubscription")}} に送信されたデータを含む {{domxref("PushMessageData")}} オブジェクトへの参照を返します。

## インスタンスメソッド

_親である {{domxref("ExtendableEvent")}} からメソッドを継承しています。_

## 例

次の例は、`PushEvent` からデータを取得して、すべてのサービスワーカークライアントで表示しています。

```js
self.addEventListener('push', function(event) {
  if (!(self.Notification && self.notification.permission === 'granted')) {
   return;
 }

 var data = {};
 if (event.data) {
   data = event.data.json();
 }
 var title = data.title || "Something Has Happened";
 var message = data.message || "Here's something you might want to check out.";
 var icon = "images/new-notification.png";

 var notification = new self.Notification(title, {
   body: message,
   tag: 'simple-push-demo-notification',
   icon: icon
 });

 notification.addEventListener('click', function() {
   if (clients.openWindow) {
     clients.openWindow('https://example.blog.com/2015/03/04/something-new.html');
   }
 });
});
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat("api.PushEvent")}}

## 関連項目

- [Push API](/ja/docs/Web/API/Push_API)
- [Service Worker API](/ja/docs/Web/API/Service_Worker_API)
