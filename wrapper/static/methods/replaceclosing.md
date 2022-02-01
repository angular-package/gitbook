# replaceClosing()

## `Wrapper.replaceClosing()`

Replaces given [`closing`](replaceclosing.md#closing-string) chars with a given [replacement value](replaceclosing.md#replacevalue-string) at the end of the given [`text`](replaceclosing.md#text-string).

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

#### `text: string`

The **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type in which given [`closing`](replaceclosing.md#closing-string) characters are replaced by a given replacement [value](replaceclosing.md#replacevalue-string).

#### `closing: string`

The **closing** chars of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to replace by a given replacement value at the end of the given [`text`](replaceclosing.md#text-string).

#### `replaceValue: string`

The replacement value of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type for the given [`closing`](replaceclosing.md#closing-string) characters in the given [`text`](replaceclosing.md#text-string).

### Returns

The **return value** is the given [`text`](replaceclosing.md#text-string) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with a replaced [`closing`](replaceclosing.md#closing-string) chars by a given [replacement value](replaceclosing.md#replacevalue-string) or the specified [`text`](replaceclosing.md#text-string) unchanged if it does not contain the given [`closing`](replaceclosing.md#closing-string) chars.

## Example usage

### Single bracket

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[', ']', 'quote');

// Returns [quote> of string.
Wrapper.replaceClosing(quote.valueOf(), ']', '>');

// Returns [quote}} of string.
Wrapper.replaceClosing(quote.valueOf(), ']', '}}');
```

### Triple bracket

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[[', ']]', '[quote]');

// Returns [[[quote]]> of string.
Wrapper.replaceClosing(quote.valueOf(), ']', '>');

// Returns [[[quote]]}} of string.
Wrapper.replaceClosing(quote.valueOf(), ']', '}}');

// Returns [[[quote} of string.
Wrapper.replaceClosing(quote.valueOf(), ']]]', '}');

// Returns [[[quote] style="" of string.
Wrapper.replaceClosing(quote.valueOf(), quote.closing, ' style=""');
```
