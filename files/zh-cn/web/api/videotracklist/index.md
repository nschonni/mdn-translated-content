---
title: VideoTrackList
slug: Web/API/VideoTrackList
---

{{APIRef("HTML DOM")}}

The **`VideoTrackList`** interface is used to represent a list of the video tracks contained within a {{HTMLElement("video")}} element, with each track represented by a separate {{domxref("VideoTrack")}} object in the list.

Retrieve an instance of this object with {{domxref('HTMLMediaElement.VideoTracks')}}. The individual tracks can be accessed using array syntax or functions such as {{jsxref("Array.forEach", "forEach()")}} for example.

## Properties

_This interface also inherits properties from its parent interface, {{domxref("EventTarget")}}._

- {{domxref("VideoTrackList.length", "length")}} {{ReadOnlyInline}}
  - : The number of tracks in the list.
- {{domxref("VideoTrackList.selectedIndex", "selectedIndex")}} {{ReadOnlyInline}}
  - : The index of the currently selected track, if any, or `−1` otherwise.

## Event handlers

- {{domxref("VideoTrackList.onaddtrack", "onaddtrack")}}
  - : An event handler to be called when the {{event("addtrack")}} event is fired, indicating that a new video track has been added to the media element.
- {{domxref("VideoTrackList.onchange", "onchange")}}
  - : An event handler to be called when the [`change`](/zh-CN/docs/Web/API/HTMLElement/change_event) event occurs — that is, when the value of the {{domxref("VideoTrack.selected", "selected")}} property for a track has changed, due to the track being made active or inactive.
- {{domxref("VideoTrackList.onremovetrack", "onremovetrack")}}
  - : An event handler to call when the {{event("removetrack")}} event is sent, indicating that a video track has been removed from the media element.

## Methods

_This interface also inherits methods from its parent interface, {{domxref("EventTarget")}}._

- {{domxref("VideoTrackList.getTrackById", "getTrackById()")}}
  - : Returns the {{domxref("VideoTrack")}} found within the `VideoTrackList` whose {{domxref("VideoTrack.id", "id")}} matches the specified string. If no match is found, `null` is returned.

## Events

- [`addtrack`](/zh-CN/docs/Web/API/VideoTrackList/addtrack_event)
  - : Fired when a new video track has been added to the media element.
    Also available via the [`onaddtrack`](/zh-CN/docs/Web/API/VideoTrackList/onaddtrack) property.
- [`change`](/zh-CN/docs/Web/API/VideoTrackList/change_event)
  - : Fired when a video track has been made active or inactive.
    Also available via the [`onchange`](/zh-CN/docs/Web/API/VideoTrackList/onchange) property.
- [`removetrack`](/zh-CN/docs/Web/API/VideoTrackList/removetrack_event)
  - : Fired when a new video track has been removed from the media element.
    Also available via the [`onremovetrack`](/zh-CN/docs/Web/API/VideoTrackList/onremovetrack) property.

## Usage notes

In addition to being able to obtain direct access to the video tracks present on a media element, `VideoTrackList` lets you set event handlers on the {{event("addtrack")}} and {{event("removetrack")}} events, so that you can detect when tracks are added to or removed from the media element's stream. See {{domxref("VideoTrackList.onaddtrack", "onaddtrack")}} and {{domxref("VideoTrackList.onremovetrack", "onremovetrack")}} for details and examples.

## Examples

### Getting a media element's video track list

To get a media element's {{domxref("VideoTrackList")}}, use its {{domxref("HTMLMediaElement.videoTracks", "videoTracks")}} property.

```js
var videoTracks = document.querySelector("video").videoTracks;
```

### Monitoring track count changes

In this example, we have an app that displays information about the number of channels available. To keep it up to date, handlers for the {{event("addtrack")}} and {{event("removetrack")}} events are set up.

```js
videoTracks.onaddtrack = updateTrackCount;
videoTracks.onremovetrack = updateTrackCount;

function updateTrackCount(event) {
  trackCount = videoTracks.length;
  drawTrackCountIndicator(trackCount);
}
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
