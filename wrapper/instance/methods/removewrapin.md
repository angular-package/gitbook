# removeWrapIn()

## `Wrapper.prototype.removeWrapIn()`

Returns given [`text`](removewrapin.md#text-string) without the [`opening`](../../../wrap/accessors/instance/opening.md) and [`closing`](../../../wrap/accessors/instance/closing.md) chars of the [`Wrapper`](broken-reference) object.

{% code title="wrapper.class.ts" %}
```typescript
public removeWrapIn(text: string): string {
  return (
    (text = this.replaceClosingIn(text, '')),
    (text = this.replaceOpeningIn(text, '')),
    text
  );
}
```
{% endcode %}

### Parameters

#### `text: string`

The **text** of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to unwrap from the [`opening`](../../../wrap/accessors/instance/opening.md) and [`closing`](../../../wrap/accessors/instance/closing.md) chars of the [`Wrapper`](broken-reference) object.

### Returns

The **return value** is the **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type unwrapped from the [`opening`](../../../wrap/accessors/instance/opening.md) and [`closing`](../../../wrap/accessors/instance/closing.md) chars of the [`Wrapper`](broken-reference) object.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{{', '}}', 'This is a long text');
const text = `Lorem ipsum and more`;

// Returns Lorem ipsum and more.
longText.removeWrapIn(`${longText.opening}${text}${longText.closing}`);

// Returns }}Lorem ipsum and more{{.
longText.removeWrapIn(`${longText.closing}${text}${longText.opening}`);
```
