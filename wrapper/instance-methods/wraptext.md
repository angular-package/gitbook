# ★ wrapText()

### `Wrapper.prototype.wrapText()`

The method returns the primitive value of the `Wrapper` object with [`text`](../../wrap/instance-accessors/#wrap.prototype.text) wrapped by given `opening` and `closing` chars.

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

### Parameters

| Name: type             | Description                                                                                                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `opening: TextOpening` | The opening chars of a generic type variable `TextOpening` to wrap the [`text`](../../wrap/instance-accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance. |
| `closing: TextClosing` | The closing chars of a generic type variable `TextClosing` to wrap the [`text`](../../wrap/instance-accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance. |

### Returns

The **return value** is the primitive value with text wrapped by given `opening` and `closing` characters of generic type `Wrapped`.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
