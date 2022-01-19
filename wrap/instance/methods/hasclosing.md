# hasClosing()

### `Wrap.prototype.hasClosing()`

Checks whether the primitive value of a specified object has the [closing](../accessors/#wrap.prototype.closing) chars or given closing chars. An empty `string` indicates [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="wrap.class.ts" %}
```typescript
public hasClosing(closing?: string): boolean {
  return (
    this.#closing.length >= 1 &&
    (typeof closing === 'string' ? this.#closing === closing : true)
  );
}
```
{% endcode %}

### Parameters

| Name: type         | Description                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------- |
| `closing?: string` | Optional closing chars of a `string` type to check whether the primitive value contains them at the end. |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the primitive value has the closing chars.

### Functions used

`isStringLength()`, `isStringType()`

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns true.
new Wrap(`[`, `]`, 'quote').hasClosing();

// Returns true.
new Wrap(`[`, `]`, 'quote').hasClosing(']');

// Returns false.
new Wrap(`[`, `]`, 'quote').hasClosing('');

// Returns false.
new Wrap(`[`, ``, 'quote').hasClosing();

// Returns false.
new Wrap(`[`, ``, 'quote').hasClosing('');

// Returns false.
new Wrap(`[`, ``, 'quote').hasClosing(']');
```
