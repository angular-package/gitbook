# ★ wrapOn()

## `Wrapper.prototype.wrapOn()`

The method wraps the given [`text`](wrapon.md#text-customtext) with the wrap, the [`opening`](../../../wrap/accessors/opening.md), and [`closing`](../../../wrap/accessors/closing.md) chars of the [`Wrapper`](../../overview.md) object.

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

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) indicates the captured type of the supplied [`text`](wrapon.md#text-customtext) parameter and the value of the generic type variable [`Text`](../../../type/wrapped.md#textextendsstring) in the  generic type [`Wrapped`](../../../type/wrapped.md) via [return type](wrapon.md#return-type), by default an empty [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string).

### Parameters

#### `text:`[<mark style="color:green;">`CustomText`</mark>](wrapon.md#customtextextendsstring)<mark style="color:green;">``</mark>

The text of generic type variable [`CustomText`](wrapon.md#customtext-extends-string) to wrap by the [`opening`](../../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](../../overview.md) instance.

### Return type

#### `Wrapped<Opening, CustomText, Closing>`

The **return type** is generic type [`Wrapped`](../../../type/wrapped.md) that takes generic type variables [`Opening`](../../generic-type-variables.md#wrap-opening), [`CustomText`](wrapon.md#customtextextendsstring) and [`Closing`](../../generic-type-variables.md#wrap-closing).

### Returns

The **return value** is the given [`text`](wrapon.md#text-customtext) wrapped by the [`opening`](../../../wrap/accessors/opening.md) and [`closing`](../../../wrap/accessors/closing.md) chars of the [`Wrapper`](broken-reference) object of the generic type [`Wrapped`](../../../type/wrapped.md).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {{This is a long text}}.
longText.wrapOn('{This is a long text}');

// Returns <span color="red">.
new Wrapper('<', '>').wrapOn('span color="red"');
```
