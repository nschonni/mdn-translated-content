---
title: start_url
slug: Web/Manifest/start_url
tags:
  - Manifest
  - Web
  - start_url
translation_of: Web/Manifest/start_url
---

{{QuickLinksWithSubpages('/ru/docs/Web/Manifest')}}

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Type</th>
      <td><code>String</code></td>
    </tr>
    <tr>
      <th scope="row">Mandatory</th>
      <td>No</td>
    </tr>
    <tr>
      <th scope="row">Example</th>
      <td>
        <pre class="brush: json no-line-numbers">
"start_url": "https://example.com"</pre>
      </td>
    </tr>
  </tbody>
</table>

_`start_url`_ является строкой, представляющей начальный URL-адрес веб-приложения — предпочтительный URL-адрес, который должен быть загружен при запуске пользователем веб-приложения (например, когда пользователь нажимает на значок веб-приложения в меню приложений или на домашнем экране).

> **Примечание:** `start_url` носит чисто рекомендательный характер, и пользовательский агент может его игнорировать или разрешить пользователю изменять его во время установки или после.

## Примеры

### Absolute URL

```json
"start_url": "https://example.com"
```

### Relative URL

Если URL является относительным, для его разрешения используется URL манифеста.

```json
"start_url": "../startpoint.html"
```

## Specifications

| Specification                                                                | Status                       | Comment             | Feedback                                                                         |
| ---------------------------------------------------------------------------- | ---------------------------- | ------------------- | -------------------------------------------------------------------------------- |
| {{SpecName('Manifest', '#start_url-member', 'start_url')}} | {{Spec2('Manifest')}} | Initial definition. | [Web App Manifest Working Group drafts](https://github.com/w3c/manifest/issues/) |

## Browser compatibility

{{Compat}}
