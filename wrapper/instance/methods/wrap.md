# ★ wrap()

## `Wrapper.prototype.wrap()`

The method wraps the [primitive value](../../../wrap/methods/instance/valueof.md) of a specified [`Wrapper`](broken-reference) object by its [`opening`](../../../wrap/accessors/opening.md) and [`closing`](../../../wrap/accessors/closing.md) chars, or the given [`opening`](wrap.md#opening-customopening) and [`closing`](wrap.md#closing-customclosing) chars.

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

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) indicates the captured type of the supplied [`opening`](wrap.md#opening-customopening) parameter and the [`Opening`](../../../type/wrapped.md#openingextendsstring) type in the generic type [`Wrapped`](../../../type/wrapped.md) via [return type](wrap.md#undefined), by default generic type variable [`Opening`](../../generic-type-variables.md#wrap-opening) of the [`Wrapper`](broken-reference) object.

#### <mark style="color:green;">`CustomClosing`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`Closing`</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) indicates the captured type of the supplied [`closing`](wrap.md#closing-customclosing) parameter and the [`Closing`](../../../type/wrapped.md#closingextendsstring) type in the generic type [`Wrapped`](../../../type/wrapped.md) via [return type](wrap.md#undefined), by default generic type variable [`Closing`](../../generic-type-variables.md#wrap-closing) of the [`Wrapper`](broken-reference) object.

### Parameters

#### `opening:`[<mark style="color:green;">`CustomOpening`</mark>](wrap.md#customopeningextendsstring-opening)

Optional opening chars of a generic type variable [`CustomOpening`](wrap.md#customopeningextendsstring-opening) to wrap the [primitive value](../../../wrap/methods/instance/valueof.md) of the [`Wrapper`](broken-reference) instance.

#### `closing:`[<mark style="color:green;">`CustomClosing`</mark>](wrap.md#customclosingextendsstring-closing)

Optional closing chars of a generic type variable [`CustomClosing`](wrap.md#customclosingextendsstring-closing) to wrap the [primitive value](../../../wrap/methods/instance/valueof.md) of the [`Wrapper`](broken-reference) instance.

### Return type

#### `Wrapped<CustomOpening, Wrapped<Opening, Text, Closing>, CustomClosing>`&#x20;

The **return type** is the generic type [`Wrapped`](../../../type/wrapped.md) that takes generic type variables [`Opening`](../../../type/wrapped.md#openingextendsstring), [`Text`](../../../type/wrapped.md#textextendsstring) and [`Closing`](../../../type/wrapped.md#closingextendsstring).

### Returns

The **return value** is a [primitive value](../../../wrap/methods/instance/valueof.md) wrapped by the [`opening`](../../../wrap/accessors/opening.md) and [`closing`](../../../wrap/accessors/closing.md) chars of the [`Wrapper`](broken-reference) instance or the given [`opening`](wrap.md#opening-customopening) and [`closing`](wrap.md#closing-customclosing) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {{{This is a long text}}}.
longText.wrap();

// Returns {{This is a long text}}.
longText.wrap('', '');
```
