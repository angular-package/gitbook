# getOpening()

### `Wrap.prototype.getOpening()`

Gets the [opening](../../library/basic-concepts.md#opening) chars of the wrap by returning the [`#opening`](../instance-properties.md#opening-opening) property of a specified object.

{% code title="wrap.class.ts" %}
```typescript
public getOpening(): Opening {
  return this.#opening;
}
```
{% endcode %}

### Returns

The **return value** is opening chars of a generic type variable [`Opening`](../generic-type-variables.md#wrap-opening).

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

// Returns [ of type "[".
new Wrap(`[`, `]`, 'quote').getOpening();
```
