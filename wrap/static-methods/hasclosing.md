# hasClosing()

### `Wrap.hasClosing()`

Checks whether the `text` has given `closing` chars at the **end**.

{% code title="wrap.class.ts" %}
```typescript
public static hasClosing(text: string, closing: string): boolean {
  return (
    typeof text === 'string' &&
    text.length >= 1 &&
    typeof closing === 'string' &&
    closing.length >= 1 &&
    text.slice(-closing.length) === closing
  );
}
```
{% endcode %}

### Parameters

| Name: type         | Description                                                                    |
| ------------------ | ------------------------------------------------------------------------------ |
| `text: string`     | The text of `string` type, to check whether it contains given `closing` chars. |
| `closing: Closing` | The closing chars of `string` type to check if a given `text` contains.        |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the `text` contains `closing` chars at the **end**.

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

const quote = new Wrap(`[`, `]`, 'quote');

// Returns true.
Wrap.hasClosing(quote.valueOf(), ']');

// Returns false.
Wrap.hasClosing(quote.valueOf(), '>');

// Returns false.
Wrap.hasClosing(quote.valueOf(), '');

// Returns false.
Wrap.hasClosing(new Wrap(`[`, ``, 'quote').valueOf(), '');
```
