# textReplaceClosing()

## `Wrapper.prototype.textReplaceClosing()`

Replaces the [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../wrapper.md) object in the [`text`](../../../wrap/instance/accessors/#wrap.prototype.text) of the [`Wrapper`](../../wrapper.md) object with the given [`closing`](textreplaceclosing.md#closing-string) chars.

{% hint style="info" %}
The replacement succeeds if the closing characters exist at the end of the text.
{% endhint %}

{% code title="wrapper.class.ts" %}
```typescript
public textReplaceClosing(closing: string): string {
  return Wrapper.replaceClosing(this.text, this.closing, closing);
}
```
{% endcode %}

### Parameters

#### `closing: string`

The **closing** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to replace in the [`text`](../../../wrap/instance/accessors/#wrap.prototype.text)(part of the primitive value).

### Returns

The **return value** is the [`text`](../../../wrap/instance/accessors/#wrap.prototype.text) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

```
