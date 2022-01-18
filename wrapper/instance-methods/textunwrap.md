# textUnwrap()

### `Wrapper.prototype.textUnwrap()`

The method returns the [`text`](../../wrap/instance-accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) object without its [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) and [`closing`](../../wrap/instance-accessors/#wrap.prototype.closing) chars or the given `opening` and `closing` chars.

{% hint style="info" %}
The default values for the `opening` and `closing` parameters are taken from the `Wrapper` object.
{% endhint %}

{% code title="wrapper.class.ts" %}
```typescript
public textUnwrap(
  opening: string = this.opening,
  closing: string = this.closing
): string {
  return Wrapper.unwrap(this.text, opening, closing);
}

```
{% endcode %}

### Parameters

| Name: type        | Description                                                                                                                                                                                                                                                                              |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `opening: string` | Optional **opening** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to remove from the **beginning** of the [`text`](../../wrap/instance-accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance. |
| `closing: string` | Optional **closing** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to remove from the **end** of the [`text`](../../wrap/instance-accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance.       |

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type without the [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) and [`closing`](../../wrap/instance-accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../wrapper.md) object or given `opening` and `closing` chars.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
