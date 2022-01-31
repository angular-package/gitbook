# hasClosing()

## `Wrap.hasClosing()`

Checks whether the [`text`](hasclosing.md#text-string) has given [`closing`](hasclosing.md#closing-string) chars at the **end**.

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

#### `text: string`

The text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type, to check whether it contains given [`closing`](hasclosing.md#closing-string) chars.

#### `closing: string`

The closing chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check if a given [`text`](hasclosing.md#text-string) contains.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`text`](hasclosing.md#text-string) contains [`closing`](hasclosing.md#closing-string) chars at the **end**.

## Example usage

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
