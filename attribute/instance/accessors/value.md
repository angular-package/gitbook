# value

### `Attribute.prototype.value`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor returns the attribute **value** of a specified [`Attribute`](../../attribute.md) object.

{% code title="attribute.class.ts" %}
```typescript
public get value(): Value {
  return this.#value;
}
```
{% endcode %}

### Returns

The **return value** is the attribute **value** of a generic type variable [`Value`](../../generic-type-variables.md#attribute-less-than...-value-greater-than).

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';

// Define a new Attribute.
const colorRed = new Attribute('color', 'red');

// Returns red of type "red".
colorRed.value;
```
