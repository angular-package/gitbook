# replaceOpeningIn()

### `Wrapper.prototype.replaceOpeningIn()`

Replaces the [`opening`](../../wrap/instance/accessors/#wrap.prototype.opening) chars of the [`Wrapper`](../wrapper.md) object in the given `text` with a given replacement value.

{% hint style="info" %}
The replacement succeeds if the opening characters exist at the beginning of the text.
{% endhint %}

{% code title="wrapper.class.ts" %}
```typescript
public replaceOpeningIn(text: string, replaceValue: string): string {
  return Wrapper.replaceOpening(text, this.opening, replaceValue);
}
```
{% endcode %}

### Parameters

| Name: type             | Description                                                                                                                                                                                                                                                        |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `text: string`         | The text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type in which the [`opening`](../../wrap/instance/accessors/#wrap.prototype.opening) chars are replaced by given replacement value.               |
| `replaceValue: string` | The value of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type as a replacement for the [`opening`](../../wrap/instance/accessors/#wrap.prototype.opening) chars at the **beginning** of the given `text`. |

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`opening`](../../wrap/instance/accessors/#wrap.prototype.opening) chars by given replacement value.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
