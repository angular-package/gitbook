# textReplaceOpening()

### `Wrapper.prototype.textReplaceOpening()`

Replaces the [`opening`](../../wrap/instance/accessors/#wrap.prototype.opening) chars of the [`Wrapper`](../wrapper.md) object in the [`text`](../../wrap/instance/accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) object with the given `closing` chars.

{% hint style="info" %}
The replacement succeeds if the opening characters exist at the beginning of the text.
{% endhint %}

{% code title="wrapper.class.ts" %}
```typescript
public textReplaceOpening(opening: string): string {
  return Wrapper.replaceOpening(this.text, this.opening, opening);
}
```
{% endcode %}

### Parameters

| Name: type        | Description                                                                                                                                                                                                                                |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `opening: string` | The **opening** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to replace in the [`text`](../../wrap/instance/accessors/#wrap.prototype.text)(part of the primitive value). |

### Returns

The **return value** is the [`text`](../../wrap/instance/accessors/#wrap.prototype.text) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`opening`](../../wrap/instance/accessors/#wrap.prototype.opening) chars.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
