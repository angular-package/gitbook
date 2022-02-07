# ★ wrapText()

## `Wrapper.prototype.wrapText()`

The method returns the [primitive value](../../wrap/methods/valueof.md) of the [`Wrapper`](broken-reference) object with [`text`](../../wrap/accessors/get-text.md) wrapped by given [`opening`](wraptext.md#opening-textopening) and [`closing`](wraptext.md#closing-textclosing) chars.

{% code title="wrapper.class.ts" %}
```typescript
public wrapText<
  TextOpening extends string = '',
  TextClosing extends string = ''
>(
  opening: TextOpening,
  closing: TextClosing
): Wrapped<Opening, Wrapped<TextOpening, Text, TextClosing>, Closing> {
  return `${this.opening}${this.textWrap(opening, closing)}${this.closing}`;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`TextOpening`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) indicates the captured type of the supplied [`opening`](wraptext.md#opening-textopening) parameter and the [`Opening`](../../type/wrapped.md#openingextendsstring) type in the generic type [`Wrapped`](../../type/wrapped.md) via [return type](wraptext.md#return-type), by default an empty [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string).

#### <mark style="color:green;">`TextClosing`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) indicates the captured type of the supplied [`closing`](wraptext.md#closing-textclosing) parameter and the [`Closing`](../../type/wrapped.md#closingextendsstring) type in the generic type [`Wrapped`](../../type/wrapped.md) via [return type](wraptext.md#return-type), by default an empty [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string).

### Parameters

#### `opening:`[<mark style="color:green;">`TextOpening`</mark>](wraptext.md#textopeningextendsstring)<mark style="color:green;">``</mark>

The opening chars of a generic type variable [`TextOpening`](wraptext.md#textopeningextendsstring) to wrap the [`text`](../../wrap/accessors/get-text.md) of the [`Wrapper`](broken-reference) instance.

#### `closing:`[<mark style="color:green;">`TextClosing`</mark>](wraptext.md#textclosingextendsstring)<mark style="color:green;">``</mark>

The closing chars of a generic type variable [`TextClosing`](wraptext.md#textclosingextendsstring) to wrap the [`text`](../../wrap/accessors/get-text.md) of the [`Wrapper`](broken-reference) instance.

### Return type

#### `Wrapped<Opening, Wrapped<TextOpening, Text, TextClosing>, Closing>`

The return type is the generic type [`Wrapped`](../../type/wrapped.md) that takes generic type variables [`Opening`](../../type/wrapped.md#openingextendsstring), [`Text`](../../type/wrapped.md#textextendsstring) and [`Closing`](../../type/wrapped.md#closingextendsstring).

### Returns

The **return value** is the [primitive value](../../wrap/methods/valueof.md) with [`text`](../../wrap/accessors/get-text.md) wrapped by given [`opening`](wraptext.md#opening-textopening) and [`closing`](wraptext.md#closing-textclosing) characters of generic type [`Wrapped`](../../type/wrapped.md).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {{{This is a long text}}} of "{{{This is a long text}}}".
longText.wrapText('{', '}');

// Returns {<{This is a long text}>} of "{<{This is a long text}>}".
longText.wrapText('<', '>');
```
