# textReplaceOpening()

## `Wrapper.prototype.textReplaceOpening()`

Replaces the [`opening`](../../../wrap/accessors/instance/opening.md) chars of the [`Wrapper`](broken-reference) object in the [`text`](../../../wrap/accessors/instance/text.md) of the [`Wrapper`](broken-reference) object with the given [`opening`](textreplaceopening.md#opening-string) chars.

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

#### `opening: string`

The **opening** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to replace in the [`text`](../../../wrap/accessors/instance/text.md)(part of the primitive value).

### Returns

The **return value** is the [`text`](../../../wrap/accessors/instance/text.md) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`opening`](../../../wrap/accessors/instance/opening.md) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {{This is a long text}}.
longText.valueOf();

// Returns This is a long text}.
longText.textReplaceOpening('');

// Returns {{This is a long text}.
longText.textReplaceOpening('{{');
```
