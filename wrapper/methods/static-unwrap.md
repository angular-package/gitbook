# static unwrap()

## `Wrapper.unwrap()`

The method returns the given [`text`](static-unwrap.md#text-string) without the given [`opening`](static-unwrap.md#opening-string) and [`closing`](static-unwrap.md#closing-string) chars.

{% code title="wrapper.class.ts" %}
```typescript
public static unwrap(text: string, opening = '', closing = ''): string {
  return (
    (text = this.replaceClosing(text, closing, '')),
    (text = this.replaceOpening(text, opening, '')),
    text
  );
}
```
{% endcode %}

### Parameters

#### `text: string`

The **text** of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) from which given [`opening`](static-unwrap.md#opening-string) and [`closing`](static-unwrap.md#closing-string) chars are removed.

#### `opening: string`

The **opening** chars of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to be removed in the given [`text`](static-unwrap.md#text-string).

#### `closing: string`

The **closing** chars of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to be removed in the given [`text`](static-unwrap.md#text-string).

### Returns

The **return value** is the given [`text`](static-unwrap.md#text-string) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type without the given [`opening`](static-unwrap.md#opening-string) and [`closing`](static-unwrap.md#closing-string) chars or unchanged [`text`](static-unwrap.md#text-string) if it does not contain the given [`opening`](static-unwrap.md#opening-string) and [`closing`](static-unwrap.md#closing-string) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[', ']', 'quote');

// Returns quote of string.
Wrapper.unwrap(quote.valueOf(), '[', ']');

// Returns [quote] of string.
Wrapper.unwrap(quote.valueOf(), '[[', ']]');
```
