# ★ wrap()

## `Wrapper.prototype.wrap()`

The method wraps the primitive value of a specified [`Wrapper`](../description.md) object by its [`opening`](../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../wrap/accessors/#wrap.prototype.closing) chars, or the given [`opening`](wrap.md#opening-customopening) and [`closing`](wrap.md#closing-customclosing) chars.

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

### Generic type variables

#### <mark style="color:green;">`CustomOpening`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`Opening`</mark>



#### <mark style="color:green;">`CustomClosing`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`Closing`</mark>



### Parameters

#### `opening: CustomOpening`

Optional opening chars of a generic type variable [`CustomOpening`](wrap.md#customopening-extends-string-opening) to wrap the primitive value of the [`Wrapper`](../description.md) instance.

#### `closing: CustomClosing`

Optional closing chars of a generic type variable [`CustomClosing`](wrap.md#customclosing-extends-string-closing) to wrap the primitive value of the [`Wrapper`](../description.md) instance.

### Returns

The **return value** is a primitive value wrapped by the given [`opening`](wrap.md#opening-customopening) and [`closing`](wrap.md#closing-customclosing) chars or from the [`Wrapper`](../description.md) instance.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
