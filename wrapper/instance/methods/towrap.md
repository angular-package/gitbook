# toWrap()

### `Wrapper.prototype.toWrap()`

Returns the [`Wrap`](../../../wrap/overview.md) instance consists of the [`text`](../../../wrap/accessors/#wrap.prototype.text), [`opening`](../../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../overview.md) object.

{% code title="wrapper.class.ts" %}
```typescript
public toWrap(): Wrap<Opening, Text, Closing> {
  return new Wrap(this.opening, this.closing, this.text);
}
```
{% endcode %}

### Return type

#### `Wrap<Opening, Text, Closing>`

The return type is the [`Wrap`](broken-reference) object that takes generic type variables [`Opening`](../../generic-type-variables.md#wrap-opening), [`Text`](../../generic-type-variables.md#wrapper-less-than...-text-...greater-than) and [`Closing`](../../generic-type-variables.md#wrap-closing).

### Returns

The **return value** is an instance of [`Wrap`](../../../wrap/overview.md) consisting of the [`text`](../../../wrap/accessors/#wrap.prototype.text), [`opening`](../../../wrap/accessors/#wrap.prototype.opening), and [`closing`](../../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../overview.md) object.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```