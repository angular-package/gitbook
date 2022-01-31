# ★ wrap()

### `Wrapper.prototype.wrap()`

The method wraps the primitive value of a specified [`Wrapper`](../../wrapper.md) object by its [`opening`](../../../wrap/instance/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars, or the given `opening` and `closing` chars.

{% code title="wrapper.class.ts" %}
```typescript
public wrap<
  CustomOpening extends string = Opening,
  CustomClosing extends string = Closing
>(
  opening: CustomOpening = this.opening as any,
  closing: CustomClosing = this.closing as any
): Wrapped<CustomOpening, Wrapped<Opening, Text, Closing>, CustomClosing> {
  return new Wrap(opening, closing, this.valueOf()).valueOf();
}
```
{% endcode %}

### Parameters

| Name: type               | Description                                                                                                                                  |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `opening: CustomOpening` | Optional opening chars of a generic type variable `CustomOpening` to wrap the primitive value of the [`Wrapper`](../../wrapper.md) instance. |
| `closing: CustomClosing` | Optional closing chars of a generic type variable `CustomClosing` to wrap the primitive value of the [`Wrapper`](../../wrapper.md) instance. |

### Returns

The **return value** is a primitive value wrapped by the given `opening` and `closing` chars or from the [`Wrapper`](../../wrapper.md) instance.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
