# toArray()

### `Wrapper.prototype.toArray()`

Returns an `array` consisting of the [`opening`](../../../wrap/instance/accessors/#wrap.prototype.opening) chars, [`text`](../../../wrap/instance/accessors/#wrap.prototype.text), and [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars.

{% code title="wrapper.class.ts" %}
```typescript
public toArray(): readonly [Opening, Text, Closing] {
  return [this.opening, this.text, this.closing];
}
```
{% endcode %}

### Returns

The **return value** is a **read-only** `array` consisting of the [`opening`](../../../wrap/instance/accessors/#wrap.prototype.opening) chars, [`text`](../../../wrap/instance/accessors/#wrap.prototype.text), and [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
