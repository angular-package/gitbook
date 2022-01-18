# hasText()

### `Wrap.prototype.hasText()`

The method checks whether the [text](../instance-accessors/#wrap.prototype.text) of a specified [`Wrap`](../wrap.md) object is defined, which means it's a `string` of at least one char and optionally equal to the given `text`.

{% code title="wrap.class.ts" %}
```typescript
public hasText(text?: string): boolean {
  return (
    isStringLength(this.#text, { min: 1 }) &&
    (isStringType(text) ? this.#text === text : true)
  );
}
```
{% endcode %}

### Parameters

| Name: type        | Description                                                                                                |
| ----------------- | ---------------------------------------------------------------------------------------------------------- |
| `text`?`: string` | Optional text of `string` type to check whether it's equal to the text of the [`Wrap`](../wrap.md) object. |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the text is defined and equal to the optionally given text.

### Functions used

`isStringLength()`, `isStringType()`

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

// Returns true.
new Wrap(`[`, `]`, 'quote').hasText();

// Returns true.
new Wrap(`[`, `]`, 'quote').hasText('quote');

// Returns false.
new Wrap(`[`, `]`).hasText();

// Returns false.
new Wrap(`[`, `]`, '').hasText();

// Returns false.
new Wrap(`[`, `]`, '').hasText('');
```
