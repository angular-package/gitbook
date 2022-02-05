# isOpeningIn()

## `Wrapper.prototype.isOpeningIn()`

Checks whether the provided [`text`](isopeningin.md#text-string) has the [`opening`](../../../wrap/accessors/instance/opening.md) chars of a specified [`Wrapper`](broken-reference) object at the **beginning**.

{% code title="wrapper.class.ts" %}
```typescript
public isOpeningIn(text: string): boolean {
  return Wrapper.hasOpening(text, this.opening);
}
```
{% endcode %}

### Parameters

#### `text: string`

The **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to test for the existence of the [`opening`](../../../wrap/accessors/instance/opening.md) chars at the **beginning** of it.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given [`text`](isopeningin.md#text-string) has the [`opening`](../../../wrap/accessors/instance/opening.md) chars  of the wrap.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{{', '}}', 'This is a long text');
const text = `Lorem ipsum and more`;

// Returns false.
longText.isOpeningIn(`${text}${longText.opening}`);

// Returns false.
longText.isOpeningIn(text);

// Returns true.
longText.isOpeningIn(`${longText.opening}${text}`);
```
