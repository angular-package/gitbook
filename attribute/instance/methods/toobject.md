# toObject()

### `Attribute.prototype.toObject()`

Returns attribute primitive value converted to the object where the property key is the attribute name, and property value is the attribute value.

{% code title="attribute.class.ts" %}
```typescript
public toObject(): Readonly<{ [key in Name]: Value }> {
  return Object.freeze({
    [this.#name]: this.#value,
  }) as { [key in Name]: Value };
}
```
{% endcode %}

### Returns

The **return value** is the attribute of a read-only object.

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';


```
