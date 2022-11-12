---
title: screenshots
slug: Web/Manifest/screenshots
tags:
  - Manifest
  - Screenshots
  - Web
translation_of: Web/Manifest/screenshots
---

{{QuickLinksWithSubpages("/ru/docs/Web/Manifest")}}

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Type</th>
      <td><code>Object</code></td>
    </tr>
    <tr>
      <th scope="row">Mandatory</th>
      <td>No</td>
    </tr>
    <tr>
      <th scope="row">Example</th>
      <td>
        <pre class="brush: json no-line-numbers">
"screenshots": [
  {
    "src": "screenshot.webp",
    "sizes": "1280x720",
    "type": "image/webp"
  }
]</pre>
      </td>
    </tr>
  </tbody>
</table>

`screenshots` определяет массив снимков экрана, предназначенных для демонстрации приложения. Эти изображения предназначены для использования в прогрессивных веб-приложениях магазинов.

## Пример

```json
"screenshots" : [
  {
    "src": "screenshot1.webp",
    "sizes": "1280x720",
    "type": "image/webp"
  },
  {
    "src": "screenshot2.webp",
    "sizes": "1280x720",
    "type": "image/webp"
  }
]
```

## Specifications

| Specification                                                                        | Status                       | Comment             | Feedback                                                                         |
| ------------------------------------------------------------------------------------ | ---------------------------- | ------------------- | -------------------------------------------------------------------------------- |
| {{SpecName('Manifest', '#screenshots-member', 'screenshots')}} | {{Spec2('Manifest')}} | Initial definition. | [Web App Manifest Working Group drafts](https://github.com/w3c/manifest/issues/) |

## Browser compatibility

{{Compat}}
