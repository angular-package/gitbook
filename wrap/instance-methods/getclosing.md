# getClosing()

### `Wrap.prototype.getClosing()`

Gets the [closing](../../library/basic-concepts.md#closing) chars of the wrap by returning the [`#closing`](../instance-properties.md#closing-closing) property of a specified object.

{% code title="wrap.class.ts" %}
```typescript
public getClosing(): Closing {
  return this.#closing;
}
```
{% endcode %}

### Returns

The **return value** is [closing](../instance-accessors/#wrap.prototype.closing) chars of a generic type variable [`Closing`](../generic-type-variables.md#wrap-closing).

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

// Returns ] of type "]".
new Wrap(`[`, `]`).getClosing();
```
