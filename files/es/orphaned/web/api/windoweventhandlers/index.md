---
title: WindowEventHandlers
slug: orphaned/Web/API/WindowEventHandlers
tags:
  - API
translation_of: Web/API/WindowEventHandlers
original_slug: Web/API/WindowEventHandlers
---

{{APIRef("HTML DOM")}}

**`WindowEventHandlers`** describes the event handlers common to several interfaces like {{domxref("Window")}}, or {{domxref("HTMLBodyElement")}} and {{domxref("HTMLFrameSetElement")}}. Each of these interfaces can implement more event handlers.

`WindowEventHandlers` is a not an interface and no object of this type can be created.

## Properties

_The events properties, of the form `onXYZ`, are defined on the {{domxref("WindowEventHandlers")}}, and implemented by {{domxref("Window")}}, and {{domxref("WorkerGlobalScope")}} for Web Workers._

- {{domxref("WindowEventHandlers.onafterprint")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`afterprint`](/es/docs/Web/Reference/Events/afterprint) event is raised.
- {{domxref("WindowEventHandlers.onbeforeprint")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`beforeprint`](/es/docs/Web/Reference/Events/beforeprint) event is raised.
- {{domxref("WindowEventHandlers.onbeforeunload")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`beforeunload`](/es/docs/Web/Reference/Events/beforeunload) event is raised.
- {{domxref("WindowEventHandlers.onhashchange")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`hashchange`](/es/docs/Web/Reference/Events/hashchange) event is raised.
- {{domxref("WindowEventHandlers.onlanguagechange")}} {{experimental_inline}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`languagechange`](/es/docs/Web/Reference/Events/languagechange) event is raised.
- {{domxref("WindowEventHandlers.onmessage")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`message`](/es/docs/Web/Reference/Events/message) event is raised.
- {{domxref("WindowEventHandlers.onoffline")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`offline`](/es/docs/Web/Reference/Events/offline) event is raised.
- {{domxref("WindowEventHandlers.ononline")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`online`](/es/docs/Web/Reference/Events/online) event is raised.
- {{domxref("WindowEventHandlers.onpagehide")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`pagehide`](/es/docs/Web/Reference/Events/pagehide) event is raised.
- {{domxref("WindowEventHandlers.onpageshow")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`pageshow`](/es/docs/Web/Reference/Events/pageshow) event is raised.
- {{domxref("WindowEventHandlers.onpopstate")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`popstate`](/es/docs/Web/Reference/Events/popstate) event is raised.
- {{domxref("WindowEventHandlers.onresize")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`resize`](/es/docs/Web/Reference/Events/resize) event is raised.
- {{domxref("WindowEventHandlers.onstorage")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`storage`](/es/docs/Web/Reference/Events/storage) event is raised.
- {{domxref("WindowEventHandlers.onunload")}}
  - : Is an [`event handler`](/es/docs/Web/Reference/Events/Event_handlers) representing the code to be called when the [`unload`](/es/docs/Web/Reference/Events/unload) event is raised.

## Methods

_This interface defines no method._

## Specifications

| Specification                                                                                        | Status                           | Comment                                                                                                                         |
| ---------------------------------------------------------------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| {{SpecName('HTML WHATWG', '#windoweventhandlers', 'GlobalEventHandlers')}} | {{Spec2('HTML WHATWG')}} | No change since the latest snapshot, {{SpecName("HTML5.1")}}.                                                          |
| {{SpecName('HTML5.1', '#windoweventhandlers', 'GlobalEventHandlers')}}         | {{Spec2('HTML5.1')}}     | Snapshot of {{SpecName("HTML WHATWG")}}. Added `onlanguage` since the {{SpecName("HTML 5")}} snapshot.           |
| {{SpecName("HTML5 W3C", "#windoweventhandlers", "GlobalEventHandlers")}}     | {{Spec2('HTML5 W3C')}}     | Snapshot of {{SpecName("HTML WHATWG")}}. Creation of `WindowEventHandlers` (properties where on the target before it). |

## Browser compatibility

{{Compat("api.WindowEventHandlers")}}

## See also

- {{domxref("Window")}} and {{domxref("WorkerGlobalScope")}}
