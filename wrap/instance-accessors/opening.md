# opening

### `Wrap.prototype.opening`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [opening](../../library/basic-concepts.md#opening) of the wrap by returning the [`#opening`](../instance-properties/#opening-opening) property of the specified object.

{% code title="wrap.class.ts" %}
```typescript
public get opening(): Opening {
  return this.#opening;
}
```
{% endcode %}

### Returns

The **return value** is the [opening](../../library/basic-concepts.md#opening) of the wrap of a generic type variable [`Opening`](../generic-type-variables.md#wrap-opening).

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns [ of type "[".
new Wrap(`[`, `]`, 'quote').opening;
```
