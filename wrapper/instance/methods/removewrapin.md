# removeWrapIn()

## `Wrapper.prototype.removeWrapIn()`

Returns given [`text`](removewrapin.md#text-string) without the [`opening`](../../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../wrapper.md) object.

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

The **text** of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to unwrap with the [`opening`](../../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../wrapper.md) object.

### Returns

The **return value** is the **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type unwrapped from the [`opening`](../../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](broken-reference) object.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
