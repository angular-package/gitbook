# getClosing()

## `Wrap.prototype.getClosing()`

Gets the [closing](../../../library/basic-concepts.md#closing) chars of the wrap by returning the [`#closing`](../../properties/closing.md) property of a specified object.

{% code title="wrap.class.ts" %}
```typescript
public getClosing(): Closing {
  return this.#closing;
}
```
{% endcode %}

### Returns

The **return value** is [`closing`](../../accessors/closing.md) chars of a generic type variable [`Closing`](../../generic-type-variables.md#wrap-closing).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns ] of type "]".
new Wrap(`[`, `]`).getClosing();
```
