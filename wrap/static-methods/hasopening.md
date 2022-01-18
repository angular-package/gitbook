# hasOpening()

### `Wrap.hasOpening()`

Checks whether the `text` has `opening` chars at the **beginning**.

```typescript
public static hasOpening(text: string, opening: string): boolean {
  return (
    typeof text === 'string' &&
    text.length >= 1 &&
    typeof opening === 'string' &&
    opening.length >= 1 &&
    text.slice(0, opening.length) === opening
  );
}
```

### Parameters

| Name: type         | Description                                                               |
| ------------------ | ------------------------------------------------------------------------- |
| `text: string`     | The text of `string`, to check whether it contains given `opening` chars. |
| `opening: Opening` | The opening chars of `string` to check if a given `text` contains.        |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the `text` contains `opening` chars at the **beginning**.

### Functions used

`isStringLength()`

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

const quote = new Wrap(`[`, `]`, 'quote');

// Returns true.
Wrap.hasOpening(quote.valueOf(), '[');

// Returns false.
Wrap.hasOpening(quote.valueOf(), '>');

// Returns false.
Wrap.hasOpening(quote.valueOf(), '');

// Returns false.
Wrap.hasOpening(new Wrap(``, `]`, 'quote').valueOf(), '');
```
