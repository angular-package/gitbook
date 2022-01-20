# ★ wrapOn()

### `Wrapper.prototype.wrapOn()`

Wraps given `text` with the wrap, the [`opening`](../../../wrap/instance/accessors/#wrap.prototype.opening), and [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../wrapper.md) object.

{% code title="wrapper.class.ts" %}
```typescript
public wrapOn<CustomText extends string = ''>(
  text: CustomText
): Wrapped<Opening, CustomText, Closing> {
  return new Wrap(this.opening, this.closing, text).valueOf();
}
```
{% endcode %}

### Parameters

| Name: type         | Description                                                                                                                                                                                                                                                        |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `text: CustomText` | The text of generic type variable `CustomText` to wrap by the [`opening`](../../../wrap/instance/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../wrapper.md) instance. |

### Returns

The **return value** is the text wrapped by the [`opening`](../../../wrap/instance/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/instance/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../wrapper.md) object of the generic type `Wrapped`.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
