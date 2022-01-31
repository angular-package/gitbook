# ★ wrapText()

## `Wrapper.prototype.wrapText()`

The method returns the primitive value of the [`Wrapper`](broken-reference) object with [`text`](../../wrap/accessors/#wrap.prototype.text) wrapped by given [`opening`](wraptext.md#opening-textopening) and [`closing`](wraptext.md#closing-textclosing) chars.

{% code title="wrapper.class.ts" %}
```typescript
public wrapText<
  TextOpening extends string = '',
  TextClosing extends string = ''
>(
  opening: TextOpening,
  closing: TextClosing
): Wrapped<Opening, Wrapped<TextOpening, Text, TextClosing>, Closing> {
  return `${this.opening}${this.textWrap(opening, closing)}${this.closing}`;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`TextOpening`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>

asdasd

#### <mark style="color:green;">`TextClosing`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>

asdasdasd

### Parameters

#### `opening: TextOpening`

The opening chars of a generic type variable [`TextOpening`](wraptext.md#textopening-extends-string) to wrap the [`text`](../../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](../description.md) instance.

#### `closing: TextClosing`

The closing chars of a generic type variable [`TextClosing`](wraptext.md#textclosing-extends-string) to wrap the [`text`](../../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](../description.md) instance.

### Returns

The **return value** is the primitive value with text wrapped by given [`opening`](wraptext.md#opening-textopening) and [`closing`](wraptext.md#closing-textclosing) characters of generic type [`Wrapped`](../../type/wrapped.md).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
