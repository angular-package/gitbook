# toString()

### `Attribute.prototype.toString()`

Returns attribute, the primitive value of a specified [`Attribute`](../../attribute.md) object.

{% code title="attribute.class.ts" %}
```typescript
public toString(): `${Name}="${Value}"` {
  return this.valueOf();
}
```
{% endcode %}

### Returns

The **return value** is the attribute of generic type variables [`Name`](../../generic-type-variables.md#wrap-opening) and [`Value`](../../generic-type-variables.md#attribute-less-than...-value-greater-than) on the template `${Name}="${Value}"`.

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';


```
