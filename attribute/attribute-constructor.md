# ★ Attribute() constructor

## `Attribute()`

Creates a new [`Attribute`](attribute.md) instance with the **name** and **value**.

{% code title="attribute.class.ts" %}
```typescript
constructor(name: Name, value: Value) {
  super(Attribute.template`${name}${value}`);
  this.#name = String(name) as Name;
  this.#value = String(value) as Value;
}
```
{% endcode %}

### Parameters

| Name: type     | Description                                             |
| -------------- | ------------------------------------------------------- |
| `name: Name`   | The attribute name of a generic type variable `Name`.   |
| `value: Value` | The attribute value of a generic type variable `Value`. |

### Returns

The **return value** is a new [`Attribute`](attribute.md) instance with the primitive value of the provided `name` and `value` on the template `${Name}="${Value}"`.

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';

// Returns Attribute {'color="red"'} of type Attribute<"color", "red">.
new Attribute('color', 'red');
```
