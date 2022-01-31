# hasText()

## `Wrap.prototype.hasText()`

The method checks whether the [text](../../accessors/#wrap.prototype.text) of a specified [`Wrap`](../../description.md) object is defined, which means it's a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of at least one char and optionally equal to the given [`text`](hastext.md#text-string).

{% code title="wrap.class.ts" %}
```typescript
public hasText(text?: string): boolean {
  return (
    this.#text.length >= 1 &&
    (typeof text === 'string' ? this.#text === text : true)
  );
}
```
{% endcode %}

### Parameters

#### `text`?`: string`

Optional text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check whether it's equal to the text of the [`Wrap`](../../description.md) object.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the text is defined and equal to the optionally given text.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

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
