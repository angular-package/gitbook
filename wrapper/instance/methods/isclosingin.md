# isClosingIn()

## `Wrapper.prototype.isClosingIn()`

Determines whether the provided [`text`](isclosingin.md#text-string) has the [`closing`](../../../wrap/accessors/instance/closing.md) chars of the specified [`Wrapper`](broken-reference) object at the **end**.

{% code title="wrapper.class.ts" %}
```typescript
public isClosingIn(text: string): boolean {
  return Wrapper.hasClosing(text, this.closing);
}
```
{% endcode %}

### Parameters

#### `text: string`

The **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to test for the existence of the [`closing`](../../../wrap/accessors/instance/closing.md) chars at the **end** of it.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given [`text`](isclosingin.md#text-string) has the [`closing`](../../../wrap/accessors/instance/closing.md) chars of the wrap.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{{', '}}', 'This is a long text');
const text = `Lorem ipsum and more`;

// Returns true.
longText.isClosingIn(`${text}${longText.closing}`);

// Returns false.
longText.isClosingIn(text);

// Returns false.
longText.isClosingIn(`${longText.closing}${text}`);
```
