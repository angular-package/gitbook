# replaceOpening()

## `Wrapper.replaceOpening()`

Replaces the [`opening`](replaceopening.md#opening-string) chars in a given [`text`](replaceopening.md#text-text) with a given [replacement value](replaceopening.md#replacevalue-string) at the beginning of the **text**.

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

Replacement value for the given [`opening`](replaceopening.md#opening-string) characters in the given [`text`](replaceopening.md#text-string).

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with a replaced **opening** chars by a given replacement value.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[', ']', 'quote');
```
