# replaceOpening()

## `Wrapper.replaceOpening()`

Replaces given [`opening`](replaceopening.md#opening-string) chars with a given [replacement value](replaceopening.md#replacevalue-string) at the beginning of the given [`text`](replaceopening.md#text-string).

{% code title="wrapper.class.ts" %}
```typescript
public static replaceOpening(
  text: string,
  opening: string,
  replaceValue: string
): string {
  return this.hasOpening(text, opening)
    ? text.replace(opening, String(replaceValue))
    : text;
}
```
{% endcode %}

### Parameters

#### `text: string`

The text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type in which the given [`opening`](replaceopening.md#opening-string) chars are replaced by a given [replacement value](replaceopening.md#replacevalue-string).

#### `opening: string`

The opening chars of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to replace by a given [replacement value](replaceopening.md#replacevalue-string) at the beginning of the given [`text`](replaceopening.md#text-string).

#### `replaceValue: string`

The replacement value of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type for the given [`opening`](replaceopening.md#opening-string) characters in the given [`text`](replaceopening.md#text-string).

### Returns

The **return value** is the given [`text`](replaceopening.md#text-string) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with a replaced [`opening`](replaceopening.md#opening-string) chars by a given [replacement value](replaceopening.md#replacevalue-string) or the specified [`text`](replaceopening.md#text-string) unchanged if it does not contain the given [`opening`](replaceopening.md#opening-string) chars.

## Example usage

### Single bracket

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[', ']', 'quote');

// Returns <quote] of string.
Wrapper.replaceOpening(quote.valueOf(), '[', '<');

// Returns {{quote] of string.
Wrapper.replaceOpening(quote.valueOf(), '[', '{{');
```

### Triple bracket

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[[', ']]', '[quote]');

// Returns <[[quote]]] of string.
Wrapper.replaceOpening(quote.valueOf(), '[', '<');

// Returns {{[[quote]]] of string.
Wrapper.replaceOpening(quote.valueOf(), '[', '{{');

// Returns {quote]]] of string.
Wrapper.replaceOpening(quote.valueOf(), '[[[', '{');

// Returns style=""[quote]]] of string.
Wrapper.replaceOpening(quote.valueOf(), quote.opening, ' style=""');
```
