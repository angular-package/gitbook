# replaceClosing()

### `Wrapper.replaceClosing()`

Replaces the closing chars in a given `text` with a given replacement value at the end of the text.

{% code title="wrapper.class.ts" %}
```typescript
public static replaceClosing(
  text: string,
  closing: string,
  replaceValue: string
): string {
  return this.hasClosing(text, closing)
    ? text.slice(0, -closing.length) + replaceValue
    : text;
}
```
{% endcode %}

### Parameters

| Name: type             | Description                                                                                                                                                                                               |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text: string`         | The **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type in which given `closing` characters are replaced by a given replacement value.  |
| `closing: string`      | The **closing** chars of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to replace by a given replacement value at the end of the given `text`. |
| `replaceValue: string` | Replacement **value** for the given `closing` characters in the given `text`.                                                                                                                             |

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with a replaced **closing** chars by a given replacement value.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[', ']', 'quote');
```
