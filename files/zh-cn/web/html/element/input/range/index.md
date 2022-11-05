---
title: <input type="range">
slug: Web/HTML/Element/input/range
original_slug: Web/HTML/Element/Input/范围
---

{{HTMLSidebar}}

{{HTMLElement("input")}} **`range`** 类型的元素允许用户指定一个数值，该数值必须不小于给定值，并且不得大于另一个给定值。但是，精确值并不重要。通常使用滑块或拨号控件而不是像 {{HTMLElement('input/number', 'number')}} 输入类型这样的文本输入框来表示。由于这种小部件不精确，因此除非控件的确切值不重要，否则通常不应使用它。

{{EmbedInteractiveExample("pages/tabbed/input-range.html", "tabbed-standard")}}

如果用户的浏览器不支持类型范围，它将回退并将其视为 `{{HTMLElement('input/text', 'text')}}` 输入。

<table class="properties">
 <tbody>
  <tr>
   <td><strong><a href="#值">Value</a></strong></td>
   <td>A {{domxref("DOMString")}} containing the string representation of the selected numeric value; use {{domxref("HTMLInputElement.valueAsNumber", "valueAsNumber")}} to get the value as a {{jsxref("Number")}}.</td>
  </tr>
  <tr>
   <td><strong>事件</strong></td>
   <td>[`change`](/zh-CN/docs/Web/API/HTMLElement/change_event) and [`input`](/zh-CN/docs/Web/API/HTMLElement/input_event)</td>
  </tr>
  <tr>
   <td><strong>支持的常用属性</strong></td>
   <td>{{htmlattrxref("autocomplete", "input")}}, {{htmlattrxref("list", "input")}}, {{htmlattrxref("max", "input")}}, {{htmlattrxref("min", "input")}}, and {{htmlattrxref("step", "input")}}</td>
  </tr>
  <tr>
   <td><strong>IDL 属性</strong></td>
   <td><code>list</code>, <code>value</code>, 和 <code>valueAsNumber</code></td>
  </tr>
  <tr>
   <td><strong>方法</strong></td>
   <td>{{domxref("HTMLInputElement.stepDown", "stepDown()")}} and {{domxref("HTMLInputElement.stepUp", "stepUp()")}}</td>
  </tr>
 </tbody>
</table>

### 验证方式

没有可用的模式验证。但是，执行以下形式的自动验证：

- 如果将 {{htmlattrxref("value", "input")}} 设置为无法转换为有效浮点数的值，则验证将失败，因为输入正遭受错误的输入。
- 该值不得小于 {{htmlattrxref("min", "input")}}. 默认值为 0。
- 该值将不大于 {{htmlattrxref("max", "input")}}. 默认值为 100。
- 该值将是 {{htmlattrxref("step", "input")}}. 预设值为 1。

### 值

{{htmlattrxref("value", "input")}} 属性包含一个 {{domxref("DOMString")}} 该属性包含所选数字的字符串表示形式。该值绝不能为空字符串 (`""`). 默认值介于指定的最小值和最大值之间，除非最大值实际上小于最小值，在这种情况下，默认值设置 `min` 属性的值。确定默认值的算法是：

```js
defaultValue = (rangeElem.max < rangeElem.min) ? rangeElem.min
               : rangeElem.min + (rangeElem.max - rangeElem.min)/2;
```

如果尝试将值设置为小于最小值，则将其设置为最小值。类似地，尝试将值设置为大于最大值会导致将其设置为最大值。

## 其他属性

除了所有 {{HTMLElement("input")}} 元素共享的属性之外，范围输入还提供以下属性：

| 属性            | 描述                                          |
| --------------- | --------------------------------------------- |
| [`list`](#list) | \<datalist>元素的 ID，其中包含可选的预定义选项 |
| [`max`](#max)   | 最大允许值                                    |
| [`min`](#min)   | 最小允许值                                    |
| [`step`](#step) | 步进间隔，用于用户界面和验证目的              |

{{page("/en-US/docs/Web/HTML/Element/input/text", "list", 0, 1, 2)}}

有关在支持的浏览器中如何表示范围中的选项的示例，请参见下面的[带散列的标记范围控制](#A_range_control_with_hash_marks)

### max

允许值范围内的最大值。如果输入到元素中的{{htmlattrxref("value", "input")}}超过此值，则元素将无法通过[约束验证](/zh-CN/docs/Web/Guide/HTML/HTML5/Constraint_validation)。如果 [`max`](/zh-CN/docs/Web/HTML/Attributes/max) 属性的值不是数字，则元素没有最大值。

此值必须大于或等于 `min` 属性的值。请参见 [HTML `max`](/zh-CN/docs/Web/HTML/Attributes/max) 属性。

### min

允许值范围内的最小值。如果元素的{{htmlattrxref("value", "input")}} 小于此值，则该元素将无法通过 [约束验证](/zh-CN/docs/Web/Guide/HTML/HTML5/Constraint_validation)。如果为`min` 指定的值不是有效数字，则输入没有最小值。

该值必须小于或等于 max 属性的值。请参见 [HTML `min`属性](/zh-CN/docs/Web/HTML/Attributes/min)。

### step

{{page("/en-US/docs/Web/HTML/Element/input/number", "step-include")}}

`range` 输入的默认步进值为 1，除非步进基数不是整数，否则仅允许输入整数；否则，默认值为 1。例如，如果将 `min` 设置为 -10 并将 `value` 设置为 1.5，则 1 的 `step` 将只允许正方向上的值为 1.5、2.5、3.5，...，以及 -0.5，-1.5，-2.5 等。 ..朝负面方向发展。请参阅[HTML `step` 属性](/zh-CN/docs/Web/HTML/Attributes/step)。

### 非标准属性

| 属性                     | 描述                                    |
| ------------------------ | --------------------------------------- |
| [`orient`](#attr-orient) | 设置范围滑块的方向。 **仅限 Firefox .** |

- {{htmlattrdef("orient")}} {{non-standard_inline}}
  - : 类似于-moz-orient 非标准 CSS 属性会影响 {{htmlelement('progress')}} 和 {{htmlelement('meter')}} 元素， `orient` 属性定义范围滑块的方向。值包括 `horizontal`, 表示范围是水平呈现，和 `vertical`, 其中范围是垂直呈现）。

> **备注：** 以下输入属性不适用于输入范围：`accept`, `alt`, `checked`, `dirname`, `formaction`, `formenctype`, `formmethod`, `formnovalidate`, `formtarget`,高度，`maxlength`, `minlength`, `multiple`, `pattern`, `placeholder`, `readonly`, `required`, `size`, `src`, 和 `width`. 这些属性中的任何一个（如果包含）将被忽略。

## 例子

虽然 `number` 类型允许用户输入带有可选约束的数字，以强制其值介于最小值和最大值之间，但它确实要求他们输入特定值。 `range` 输入类型使您可以在用户甚至不关心或不知道所选的特定数字值是什么的情况下，向用户询问一个值。

常用范围输入的一些情况示例：

- 音频控件（例如音量和平衡）或过滤器控件。
- 颜色配置控件，例如颜色通道，透明度，亮度等。
- 游戏配置控件，例如难度，可见性距离，世界范围等等。
- 密码管理员生成的密码的密码长度。

通常，如果用户对最小值和最大值之间的距离的百分比比实际数字本身更感兴趣，则范围输入是一个不错的选择。例如，在家庭立体声音量控制的情况下，用户通常认为“将音量设置为最大音量的一半”而不是“将音量设置为 0.5”。

### 指定最小和最大

默认情况下，最小值为 0，最大值为 100。如果这不是您想要的值，则可以通过更改 {{htmlattrxref("min", "input")}} 和/或 {{htmlattrxref("max", "input")}} 属性。这些可以是任何浮点值。

例如，要要求用户输入介于 -10 和 10 之间的值，可以使用：

```html
<input type="range" min="-10" max="10">
```

{{EmbedLiveSample("Specifying_the_minimum_and_maximum", 600, 40)}}

### 设置值的粒度

默认情况下，粒度为 1，表示该值始终是整数。您可以更改 {{htmlattrxref("step")}} 属性以控制粒度。例如，如果您需要一个介于 5 到 10 之间的值（精确到两位小数），则应将 `step` 的值设置为 0.01:

```html
<input type="range" min="5" max="10" step="0.01">
```

{{EmbedLiveSample("Granularity_sample1", 600, 40)}}

如果要接受任何值而不论扩展到小数点后多少位，都可以为{{htmlattrxref("step", "input")}} 属性指定 `any` 数值。

```html
<input type="range" min="0" max="3.14" step="any">
```

{{EmbedLiveSample("Granularity_sample2", 600, 40)}}

该示例使用户可以选择 0 到 π 之间的任何值，而对所选值的小数部分没有任何限制。

### 添加井号和标签

HTML 规范使浏览器在如何显示范围控件方面具有一定的灵活性。在散列标记和较小程度上的标签方面，这种灵活性最明显。该规范描述了如何使用 {{htmlattrxref("list", "input")}} 属性和 {{HTMLElement("datalist")}} 元素将自定义点添加到范围控件，但没有任何要求或 甚至是沿控件长度的标准化哈希或刻度线的建议。

#### 范围控制模型

由于浏览器具有这种灵活性，并且迄今为止都不支持 HTML 为范围控件定义的所有功能，因此以下是一些模型，以向您展示在支持它们的浏览器中在 macOS 上可以得到的功能。

##### 无装饰的范围控制

如果不指定 {{htmlattrxref("list", "input")}} 属性，或者浏览器不支持该属性，则会得到此结果。

<table class="fullwidth standard-table">
  <tbody>
    <tr>
      <th>HTML</th>
      <th>例子</th>
    </tr>
    <tr>
      <td rowspan="4">
        <pre class="brush: html notranslate">&#x3C;input type="range"></pre>
      </td>
      <th>屏幕截图</th>
    </tr>
    <tr>
      <td>
        <img
          alt="Screenshot of a plain slider control on macOS"
          src="macslider-plain.png"
        />
      </td>
    </tr>
    <tr>
      <th>留存</th>
    </tr>
    <tr>
      <td>
        {{EmbedLiveSample("An_unadorned_range_control",200,55,"","", "nobutton")}}
      </td>
    </tr>
  </tbody>
</table>

##### 带散列标记的范围控件

此范围控件使用的 `list` 属性指定{{HTMLElement("datalist")}} 的 ID，该 ID 定义了控件上的一系列带散列的标记。其中有 11 个，因此在 0％和每个 10％标记处都有一个。每个点均使用 {{HTMLElement("option")}} 元素表示，其元素 {{htmlattrxref("value", "option")}} 设置为应绘制标记的范围值。

<table class="fullwidth standard-table">
  <tbody>
    <tr>
      <th>HTML</th>
      <th>例子</th>
    </tr>
    <tr>
      <td rowspan="4">
        <pre class="brush: html notranslate">
&#x3C;input type="range" list="tickmarks">

&#x3C;datalist id="tickmarks">
&#x3C;option value="0">&#x3C;/option>
&#x3C;option value="10">&#x3C;/option>
&#x3C;option value="20">&#x3C;/option>
&#x3C;option value="30">&#x3C;/option>
&#x3C;option value="40">&#x3C;/option>
&#x3C;option value="50">&#x3C;/option>
&#x3C;option value="60">&#x3C;/option>
&#x3C;option value="70">&#x3C;/option>
&#x3C;option value="80">&#x3C;/option>
&#x3C;option value="90">&#x3C;/option>
&#x3C;option value="100">&#x3C;/option>
&#x3C;/datalist>

</pre
        >
      </td>
      <th>屏幕截图</th>
    </tr>
    <tr>
      <td>
        <img
          alt="Screenshot of a plain slider control on macOS"
          src="macslider-ticks.png"
        />
      </td>
    </tr>
    <tr>
      <th>留存</th>
    </tr>
    <tr>
      <td>
        {{EmbedLiveSample("A_range_control_with_hash_marks_and_labels",200,55,"","", "nobutton")}}
      </td>
    </tr>
  </tbody>
</table>

##### 具有散列标记和标签的范围控件

您可以通过向 {{htmlattrxref("label", "option")}} 元素添加 {{HTMLElement("option")}} 属性来将标签添加到您的范围控件中，这些元素对应于您希望为其添加标签的标记。

<table class="fullwidth standard-table">
  <tbody>
    <tr>
      <th>HTML</th>
      <th>例子</th>
    </tr>
    <tr>
      <td rowspan="4">
        <pre class="brush: html notranslate">
&#x3C;input type="range" list="tickmarks">

&#x3C;datalist id="tickmarks">
&#x3C;option value="0" label="0%">&#x3C;/option>
&#x3C;option value="10">&#x3C;/option>
&#x3C;option value="20">&#x3C;/option>
&#x3C;option value="30">&#x3C;/option>
&#x3C;option value="40">&#x3C;/option>
&#x3C;option value="50" label="50%">&#x3C;/option>
&#x3C;option value="60">&#x3C;/option>
&#x3C;option value="70">&#x3C;/option>
&#x3C;option value="80">&#x3C;/option>
&#x3C;option value="90">&#x3C;/option>
&#x3C;option value="100" label="100%">&#x3C;/option>
&#x3C;/datalist>

</pre
        >
      </td>
      <th>屏幕截图</th>
    </tr>
    <tr>
      <td>
        <img
          alt="Screenshot of a plain slider control on macOS"
          src="macslider-labels.png"
        />
      </td>
    </tr>
    <tr>
      <th>留存</th>
    </tr>
    <tr>
      <td>
        {{EmbedLiveSample("A_range_control_with_hash_marks_and_labels",200,55,"","", "nobutton")}}
      </td>
    </tr>
  </tbody>
</table>

> **备注：** 目前没有浏览器完全支持这些特性。例如，Firefox 根本不支持散列标记和标签，而 Chrome 支持散列标记，但不支持标签。Chrome 的 66 版本 (66.0.3359.181) 支持标签，但是 {{htmlelement("datalist")}} 标签必须使用 CSS 样式，因为它的 {{cssxref("display")}}属性默认设置为 `none` ，隐藏了标签。

### 改变方向

使旋钮向左和向右滑动。如果支持，我们将能够声明垂直高度，并通过声明高度值大于宽度值来使用 CSS 上下滑动。任何主要的浏览器实际上尚未实现此功能。（请参阅{{bug(981916)}}, [Chrome bug 341071](https://bugs.chromium.org/p/chromium/issues/detail?id=341071))。也许它仍在讨论中。

同时，我们可以通过使用 CSS 变换旋转范围来使范围垂直，或者通过使用各自的方法定位每个浏览器引擎，包括通过将 {{cssxref('appearance')}} 设置为 `slider-vertical`, 在 Firefox 中使用非标准的`orient` 属性，或通过更改 Internet Explorer 和 Edge 的文本方向。

考虑以下范围控制：

```html
<input type="range" id="volume" min="0" max="11" value="7" step="1">
```

{{EmbedLiveSample("改变方向", 200, 200)}}

此控件是水平的（至少对大多数主要浏览器（至少，如果不是全部）；其他控件可能有所不同）。

### 标准

根据规范，使其垂直需要添加 CSS 来更改控件的尺寸，以使其比宽度高，如下所示：

#### CSS

```css
#volume {
  height: 150px;
  width: 50px;
}
```

#### HTML

```html
<input type="range" id="volume" min="0" max="11" value="7" step="1">
```

#### 结果

{{EmbedLiveSample("Orientation_sample2", 200, 200, "https://mdn.mozillademos.org/files/14985/Orientation_sample2.png")}}

不幸的是，当前没有主流浏览器直接支持垂直范围控件。

### 变换：旋转（-90deg）

但是，您可以通过在侧面绘制水平范围控件来创建垂直范围控件。最简单的方法是使用 CSS：通过应用 {{cssxref("transform")}} 旋转元素，可以使其垂直。让我们来看看。

#### HTML

需要更新 HTML，以将 {{HTMLElement("input")}} 包裹在 {{HTMLElement("div")}} 中，以便我们在执行转换后纠正布局（因为转换不会自动影响 页面的布局）：

```html
<div class="slider-wrapper">
  <input type="range" min="0" max="11" value="7" step="1">
</div>
```

#### CSS

现在我们需要一些 CSS。首先是包装器本身的 CSS；这指定了我们想要的显示模式和大小，以便页面正确布局；本质上，它是为滑块保留页面的区域，以便旋转的滑块适合保留的空间而不会造成混乱。

```css
.slider-wrapper {
  display: inline-block;
  width: 20px;
  height: 150px;
  padding: 0;
}
```

然后是保留空间中 `<input>` 元素的样式信息：

```css
.slider-wrapper input {
  width: 150px;
  height: 20px;
  margin: 0;
  transform-origin: 75px 75px;
  transform: rotate(-90deg);
}
```

控件的大小设置为 150 像素长 x 20 像素高。边距设置为 0， {{cssxref("transform-origin")}} 移至滑块旋转通过的空间的中间；由于滑块配置为 150 像素宽，因此它将旋转通过每边 150 像素的框。在每个轴上将原点偏移 75 像素，这意味着我们将围绕该空间的中心旋转。最后，我们将逆时针旋转 90°。结果：旋转一个范围输入，因此最大值在顶部，最小值在底部。

{{EmbedLiveSample("transform_rotate-90deg", 200, 200, "https://mdn.mozillademos.org/files/14987/Orientation_sample3.png")}}

### 外观特性

{{cssxref('appearance')}}属性具有非标准值的`slider-vertical`可以使滑块垂直。

#### HTML

我们使用与前面的示例相同的 HTML：

```html
<input type="range" min="0" max="11" value="7" step="1">
```

#### CSS

我们仅针对具有范围类型的输入：

```css
input[type="range"] {
  -webkit-appearance: slider-vertical;
}
```

{{EmbedLiveSample("appearance_property", 200, 200)}}

### 定向属性

仅在 Firefox 中，有一个非标准的 `orient` 属性。

#### HTML

使用与前面示例类似的 HTML，我们添加属性值为 `vertical`:

```html
<input type="range" min="0" max="11" value="7" step="1" orient="vertical">
```

{{EmbedLiveSample("orient_attribute", 200, 200)}}

### 写作模式：bt-lr;

The {{cssxref('writing-mode')}} 属性通常不应用于出于国际化或本地化目的更改文本方向，而可以用于特殊效果。

#### HTML

我们使用与前面的示例相同的 HTML：

```html
<input type="range" min="0" max="11" value="7" step="1">
```

#### CSS

我们仅以范围为类型的输入作为目标，将写入模式从默认更改为 `bt-lr`, 或从下至上和从左至右：

```css
input[type="range"] {
  writing-mode: bt-lr;
}
```

{{EmbedLiveSample("writing-mode_bt-lr", 200, 200)}}

### 放在一起

由于上述每个示例都在不同的浏览器中工作，因此您可以将所有示例放在一个示例中，以使其在跨浏览器中工作：

#### HTML

对于 Firefox，我们将`orient`属性的值保持为`vertical：`

```html
<input type="range" min="0" max="11" value="7" step="1" orient="vertical">
```

#### CSS

对于 Edge 和 Internet Explorer，我们仅将输入类型作为目标，将写入模式从默认更改为 `bt-lr`, 或者从下至上，从左至右，然后添加 `-webkit-appearance: slider-vertical`用于所有基于-webkit 的浏览器：

```css
input[type="range"] {
  writing-mode: bt-lr;
  -webkit-appearance: slider-vertical;
}
```

{{EmbedLiveSample("Putting_it_all_together", 200, 200)}}

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat}}

## 另请参考

- [HTML 表单](/zh-CN/docs/Learn/HTML/Forms)
- {{HTMLElement("input")}} and the {{domxref("HTMLInputElement")}} interface it's based upon
- [`<input type="number">`](/zh-CN/docs/Web/HTML/Element/input/number)
- {{domxref('validityState.rangeOverflow')}} and {{domxref('validityState.rangeUnderflow')}}
- [使用 ConstantSourceNode 控制多个参数](/zh-CN/docs/Web/API/Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode)
- [设置范围元素的样式](https://css-tricks.com/sliding-nightmare-understanding-range-input)
