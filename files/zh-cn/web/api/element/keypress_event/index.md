---
title: keypress
slug: Web/API/Element/keypress_event
---

The `keypress` event is fired when a key is pressed down and that key normally produces a character value (use [`input`](/zh-CN/Mozilla_event_reference/input) instead).

## General info

- Specification
  - : [DOM L3](http://www.w3.org/TR/DOM-Level-3-Events/#event-type-keypress) {{deprecated_inline()}}
- Interface
  - : [KeyboardEvent](/zh-CN/docs/DOM/KeyboardEvent)
- Bubbles
  - : Yes
- Cancelable
  - : Yes
- Target
  - : Document, Element
- Default Action
  - : Varies: `keypress` event; launch text composition system; `blur` and `focus` events; `DOMActivate` event; other event

## Properties

## Related Events

- [`keydown`](/zh-CN/docs/Web/API/Element/keydown_event)
- [`keyup`](/zh-CN/docs/Web/API/Element/keyup_event)
- [`keypress`](/zh-CN/docs/Web/API/Element/keypress_event)
- [`input`](/zh-CN/docs/Web/API/HTMLElement/input_event)

<table class="standard-table">
  <thead>
    <tr>
      <th scope="col">Property</th>
      <th scope="col">Type</th>
      <th scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>target</code> {{readonlyInline}}</td>
      <td>EventTarget</td>
      <td>The event target (the topmost target in the DOM tree).</td>
    </tr>
    <tr>
      <td><code>type</code> {{readonlyInline}}</td>
      <td>DOMString</td>
      <td>The type of event.</td>
    </tr>
    <tr>
      <td><code>bubbles</code> {{readonlyInline}}</td>
      <td>Boolean</td>
      <td>Whether the event normally bubbles or not</td>
    </tr>
    <tr>
      <td><code>cancelable</code> {{readonlyInline}}</td>
      <td>Boolean</td>
      <td>Whether the event is cancellable or not?</td>
    </tr>
    <tr>
      <td><code>view</code> {{readonlyInline}}</td>
      <td>WindowProxy</td>
      <td>
        <a href="/zh-CN/docs/Web/API/Document/defaultView"
          ><code>document.defaultView</code></a
        >
        (<code>window</code> of the document)
      </td>
    </tr>
    <tr>
      <td><code>detail</code> {{readonlyInline}}</td>
      <td><code>long</code> (<code>float</code>)</td>
      <td>0.</td>
    </tr>
    <tr>
      <td><code>target</code> {{readonlyInline}}</td>
      <td>EventTarget (DOM element)</td>
      <td>
        Focused element processing the key event, root element if no suitable
        input element focused.
      </td>
    </tr>
    <tr>
      <td><code>char</code> {{readonlyInline}}</td>
      <td>DOMString (string)</td>
      <td>
        The character value of the key. If the key corresponds to a printable
        character, this value is a non-empty Unicode string containing that
        character. If the key doesn't have a printable representation, this is
        an empty string. See
        <a href="/zh-CN/docs/Web/API/KeyboardEvent#Key_names_and_Char_values"
          >key names and char values</a
        >
        for the detail.
        <div class="note">
          <strong>Note:</strong> If the key is used as a macro that inserts
          multiple characters, this attribute's value is the entire string, not
          just the first character.
        </div>
      </td>
    </tr>
    <tr>
      <td><code>key</code> {{readonlyInline}}</td>
      <td>DOMString (string)</td>
      <td>
        The key value of the key represented by the event. If the value has a
        printed representation, this attribute's value is the same as the
        <code>char</code> attribute. Otherwise, it's one of the key value
        strings specified in <a href="#key_values">Key Values</a>. If the key
        can't be identified, this is the string "Unidentified". See
        <a href="/zh-CN/docs/Web/API/KeyboardEvent#Key_names_and_Char_values"
          >key names and char values</a
        >
        for the detail. Read Only.
      </td>
    </tr>
    <tr>
      <td><code>charCode</code> {{readonlyInline}}</td>
      <td>Unsigned long (int)</td>
      <td>
        The Unicode reference number of the key; this attribute is used only by
        the
        <a href="/zh-CN/docs/Mozilla_event_reference/keypress"
          ><code>keypress</code></a
        >
        event. For keys whose <code>char</code> attribute contains multiple
        characters, this is the Unicode value of the first character in that
        attribute.
        <div class="warning">
          <strong>Warning:</strong> This attribute is deprecated; you should use
          <code>char</code> instead, if available.
        </div>
      </td>
    </tr>
    <tr>
      <td><code>keyCode</code> {{readonlyInline}}</td>
      <td>Unsigned long (int)</td>
      <td>
        A system and implementation dependent numerical code identifying the
        unmodified value of the pressed key. This is usually the decimal ASCII
        ({{ RFC(20) }}) or Windows 1252 code corresponding to the key; see
        <a href="virtual_key_codes">Virtual key codes</a> for a list of common
        values. If the key can't be identified, this value is 0.
        <div class="warning">
          <strong>Warning:</strong> This attribute is deprecated; you should use
          <code>key</code> instead, if available.
        </div>
      </td>
    </tr>
    <tr>
      <td><code>which</code> {{readonlyInline}}</td>
      <td>Unsigned long (int)</td>
      <td>
        A system and implementation dependent numeric code identifying the
        unmodified value of the pressed key; this is usually the same as
        <code>keyCode</code>.
        <div class="warning">
          <strong>Warning:</strong> This attribute is deprecated; you should use
          <code>key</code> instead, if available.
        </div>
      </td>
    </tr>
    <tr>
      <td><code>location</code> {{readonlyInline}}</td>
      <td>long (float)</td>
      <td>The location of the key on the device.</td>
    </tr>
    <tr>
      <td><code>repeat</code> {{readonlyInline}}</td>
      <td>boolean</td>
      <td>
        <code>true</code> if a key has been depressed long enough to trigger key
        repetition, otherwise <code>false</code>.
      </td>
    </tr>
    <tr>
      <td><code>locale</code> {{readonlyInline}}</td>
      <td>string</td>
      <td>
        The language code for the key event, if available; otherwise, the empty
        string.
      </td>
    </tr>
    <tr>
      <td><code>ctrlKey</code> {{readonlyInline}}</td>
      <td>boolean</td>
      <td>
        <code>true</code> if the control key was down when the event was fired.
        <code>false</code> otherwise.
      </td>
    </tr>
    <tr>
      <td><code>shiftKey</code> {{readonlyInline}}</td>
      <td>boolean</td>
      <td>
        <code>true</code> if the shift key was down when the event was fired.
        <code>false</code> otherwise.
      </td>
    </tr>
    <tr>
      <td><code>altKey</code> {{readonlyInline}}</td>
      <td>boolean</td>
      <td>
        <code>true</code> if the alt key was down when the event was fired.
        <code>false</code> otherwise.
      </td>
    </tr>
    <tr>
      <td><code>metaKey</code> {{readonlyInline}}</td>
      <td>boolean</td>
      <td>
        <code>true</code> if the meta key was down when the event was fired.
        <code>false</code> otherwise.
      </td>
    </tr>
  </tbody>
</table>
