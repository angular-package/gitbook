# replaceClosingIn()

### `Wrapper.prototype.replaceClosingIn()`

Replaces the [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../wrapper.md) object in the given `text` with a given replacement value.

{% hint style="info" %}
The replacement succeeds if the closing characters exist at the end of the text.
{% endhint %}

{% code title="wrapper.class.ts" %}
```typescript
public replaceClosingIn(text: string, replaceValue: string): string {
  return Wrapper.replaceClosing(text, this.closing, replaceValue);
}
```
{% endcode %}

### Parameters

| Name: type             | Description                                                                                                                                                                                                                                                     |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text: string`         | The **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type in which the [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars are replaced by given replacement value.     |
| `replaceValue: string` | The value of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type as a replacement for the [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars at the **end** of the given `text`. |

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars by given replacement value.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
