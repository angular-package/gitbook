# textReplaceClosing()

## `Wrapper.prototype.textReplaceClosing()`

Replaces the [`closing`](../../../wrap/accessors/closing.md) chars of the [`Wrapper`](broken-reference) object in the [`text`](../../../wrap/accessors/text.md) of the [`Wrapper`](broken-reference) object with the given [`closing`](textreplaceclosing.md#closing-string) chars.

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

The **closing** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to replace in the [`text`](../../../wrap/accessors/text.md)(part of the primitive value).

### Returns

The **return value** is the [`text`](../../../wrap/accessors/text.md) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`closing`](../../../wrap/accessors/closing.md) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {{This is a long text}}.
longText.valueOf();

// Returns {This is a long text.
longText.textReplaceClosing('');

// Returns {This is a long text}}.
longText.textReplaceClosing('}}');
```
