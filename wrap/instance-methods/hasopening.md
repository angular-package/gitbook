# hasOpening()

### `Wrap.prototype.hasOpening()`

Checks whether the primitive value of a specified object has the [opening](../instance-accessors/#wrap.prototype.opening) chars or given opening chars. An empty `string` indicates [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="wrap.class.ts" %}
```typescript
public hasOpening(opening?: string): boolean {
  return (
    isStringLength(this.#opening, { min: 1 }) &&
    (isStringType(opening) ? this.#opening === opening : true)
  );
}
```
{% endcode %}

### Parameters

| Name: type         | Description                                                                                               |
| ------------------ | --------------------------------------------------------------------------------------------------------- |
| `opening?: string` | Optional opening chars of a `string` type to check if the primitive value contains them at the beginning. |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the primitive value has the opening chars.

### Functions used

`isStringLength()`, `isStringType()`

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

// Returns true.
new Wrap(`[`, `]`, 'quote').hasOpening();

// Returns true.
new Wrap(`[`, `]`, 'quote').hasOpening('[');

// Returns false.
new Wrap(`[`, `]`, 'quote').hasOpening('');

// Returns false.
new Wrap(``, `]`, 'quote').hasOpening();

// Returns false.
new Wrap(``, `]`, 'quote').hasOpening('');

// Returns false.
new Wrap(``, `]`, 'quote').hasOpening('[');
```
