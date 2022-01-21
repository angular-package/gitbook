# name

### `Attribute.prototype.name`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor returns the attribute **name** of a specified [`Attribute`](../../attribute.md) object.

{% code title="attribute.class.ts" %}
```typescript
public get name(): Name {
  return this.#name;
}
```
{% endcode %}

### Returns

The **return value** is the attribute **name** of a generic type variable [`Name`](../../generic-type-variables.md#wrap-opening).

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';

// Define a new Attribute.
const colorRed = new Attribute('color', 'red');

// Returns color of type "color".
colorRed.name;
```
