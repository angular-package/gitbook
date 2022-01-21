# attribute

### `Attribute.prototype.attribute`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor returns the **attribute**, the primitive value of a specified [`Attribute`](../../attribute.md) object.

{% code title="attribute.class.ts" %}
```typescript
public get attribute(): `${Name}="${Value}"` {
  return this.valueOf();
}
```
{% endcode %}

### Returns

The **return value** is the attribute of a generic type variables [`Name`](../../generic-type-variables.md#wrap-opening) and [`Value`](../../generic-type-variables.md#attribute-less-than...-value-greater-than) on the template `${Name}="${Value}"`.

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';

// Define a new Attribute.
const colorRed = new Attribute('color', 'red');

// Returns color="red" of type "color=\"red\"".
colorRed.attribute;
```
