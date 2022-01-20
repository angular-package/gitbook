# unwrap()

### `Wrapper.prototype.unwrap()`

Returns the [`text`](../../../wrap/instance/accessors/#wrap.prototype.text) without the [`opening`](../../../wrap/instance/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars.

{% code title="wrapper.class.ts" %}
```typescript
public unwrap(): Text {
  return this.text;
}
```
{% endcode %}

### Returns

The **return value** is the [`text`](../../../wrap/instance/accessors/#wrap.prototype.text) of a generic type variable [`Text`](../../generic-type-variables.md#wrapper-less-than...-text-...greater-than).

### Example usage

```typescript
// Example usage.wrapper
import { Wrapper } from '@angular-package/wrapper';


```
