# ★ wrapOn()

## `Wrapper.prototype.wrapOn()`

Wraps given [`text`](wrapon.md#text-customtext) with the wrap, the [`opening`](../../wrap/accessors/#wrap.prototype.opening), and [`closing`](../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../description.md) object.

{% code title="wrapper.class.ts" %}
```typescript
public wrapOn<CustomText extends string = ''>(
  text: CustomText
): Wrapped<Opening, CustomText, Closing> {
  return new Wrap(this.opening, this.closing, text).valueOf();
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`CustomText`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>



### Parameters

#### `text: CustomText`

The text of generic type variable [`CustomText`](wrapon.md#customtext-extends-string) to wrap by the [`opening`](../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../description.md) instance.

### Return type

#### `Wrapped<Opening, CustomText, Closing>`

The **return type** is generic type [`Wrapped`](../../type/wrapped.md) that takes generic type variables [`Opening`](../generic-type-variables.md#wrap-opening), [`CustomText`](wrapon.md#customtextextendsstring) and [`Closing`](../generic-type-variables.md#wrap-closing).

### Returns

The **return value** is the text wrapped by the [`opening`](../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../description.md) object of the generic type [`Wrapped`](../../type/wrapped.md).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
