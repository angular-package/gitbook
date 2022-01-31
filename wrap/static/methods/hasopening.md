# hasOpening()

## `Wrap.hasOpening()`

Checks whether the [`text`](hasopening.md#text-string) has [`opening`](hasopening.md#opening-opening) chars at the **beginning**.

{% code title="wrap.class.ts" %}
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
{% endcode %}

### Parameters

#### `text: string`

The text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), to check whether it contains given [`opening`](hasopening.md#opening-opening) chars.

#### `opening: string`

The opening chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to check if a given [`text`](hasopening.md#text-string) contains.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`text`](hasopening.md#text-string) contains [`opening`](hasopening.md#opening-opening) chars at the **beginning**.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

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
