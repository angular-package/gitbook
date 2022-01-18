# toWrap()

### `Wrapper.prototype.toWrap()`

Returns the [`Wrap`](../../wrap/wrap.md) instance consists of the [`text`](../../wrap/instance-accessors/#wrap.prototype.text), [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) and [`closing`](../../wrap/instance-accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../wrapper.md) object.

{% code title="wrapper.class.ts" %}
```typescript
public toWrap(): Wrap<Opening, Text, Closing> {
  return new Wrap(this.opening, this.closing, this.text);
}
```
{% endcode %}

### Returns

The **return value** is an instance of [`Wrap`](../../wrap/wrap.md) consisting of the [`text`](../../wrap/instance-accessors/#wrap.prototype.text), [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening), and [`closing`](../../wrap/instance-accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../wrapper.md) object.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
