# replaceClosingIn()

## `Wrapper.prototype.replaceClosingIn()`

Replaces the [`closing`](../../../wrap/accessors/closing.md) chars of the [`Wrapper`](../../overview.md) object in the given [`text`](replaceclosingin.md#text-string) with a given [replacement value](replaceclosingin.md#replacevalue-string).

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

#### `text: string`

The **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type in which the [`closing`](../../../wrap/accessors/closing.md) chars are replaced by given [replacement value](replaceclosingin.md#replacevalue-string).

#### `replaceValue: string`

The value of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type as a replacement for the [`closing`](../../../wrap/accessors/closing.md) chars at the **end** of the given [`text`](replaceclosingin.md#text-string).

### Returns

The **return value** is the given text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`closing`](../../../wrap/accessors/closing.md) chars by given [replacement value](replaceclosingin.md#replacevalue-string).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{{', '}}', 'This is a long text');
const text = `Lorem ipsum and more`;

// Returns Lorem ipsum and more??.
longText.replaceClosingIn(`${text}${longText.closing}`, '??');

// Returns }}Lorem ipsum and more.
longText.replaceClosingIn(`${longText.closing}${text}`, '??');
```
