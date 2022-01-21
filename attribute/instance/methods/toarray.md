# toArray()

### `Attribute.prototype.toArray()`

Returns attribute primitive value converted to the `array` where the first element is the name, and the second is the value.

{% code title="attribute.class.ts" %}
```typescript
public toArray(): readonly [Name, Value] {
  return [this.#name, this.#value];
}
```
{% endcode %}

### Returns

The **return value** is the attribute of a read-only `array`.

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';


```
