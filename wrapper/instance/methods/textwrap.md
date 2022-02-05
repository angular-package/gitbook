# textWrap()

## `Wrapper.prototype.textWrap()`

The method returns the [`text`](../../../wrap/accessors/instance/text.md) of the [`Wrapper`](broken-reference) object wrapped by the given [`opening`](textwrap.md#opening-textopening) and [`closing`](textwrap.md#closing-textclosing) chars.

{% code title="wrapper.class.ts" %}
```typescript
public textWrap<TextOpening extends string, TextClosing extends string>(
  opening: TextOpening,
  closing: TextClosing
): Wrapped<TextOpening, Text, TextClosing> {
  return new Wrap(opening, closing, this.text).valueOf();
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`TextOpening`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`opening`](textwrap.md#opening-textopening) indicates the type of the opening chars in generic type [`Wrapped`](../../../type/wrapped.md)  via [return type](textwrap.md#return-type).

#### <mark style="color:green;">**`TextClosing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`closing`](textwrap.md#closing-textclosing) indicates the type of the closing chars in generic type [`Wrapped`](../../../type/wrapped.md) via [return type](textwrap.md#return-type).

### Parameters

#### `opening: TextOpening`

The **opening** chars of a generic type variable [`TextOpening`](textwrap.md#textopeningextendsstring) to wrap the [`text`](../../../wrap/accessors/instance/text.md) of the [`Wrapper`](broken-reference) instance.

#### `closing: TextClosing`

The **closing** chars of a generic type variable [`TextClosing`](textwrap.md#textclosingextendsstring) to wrap the [`text`](../../../wrap/accessors/instance/text.md) of the [`Wrapper`](broken-reference) instance.

### Return type

#### `Wrapped<TextOpening, Text, TextClosing>`

The **return type** is generic type [`Wrapped`](../../../type/wrapped.md) that takes generic type variables [`TextOpening`](textwrap.md#textopeningextendsstring), [`Text`](../../generic-type-variables.md#wrapper-less-than...-text-...greater-than) and [`TextClosing`](textwrap.md#textclosingextendsstring).

### Returns

The **return value** is the [`text`](../../../wrap/accessors/instance/text.md) wrapped by given [`opening`](textwrap.md#opening-textopening) and [`closing`](textwrap.md#closing-textclosing) chars of generic type [`Wrapped`](../../../type/wrapped.md).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {{This is a long text}}.
longText.valueOf();

// Returns {This is a long text}.
longText.textWrap('', '');

// Returns {{This is a long text}.
longText.textWrap('{', '');

// Returns {This is a long text}}.
longText.textWrap('', '}');

// Returns {{This is a long text}}.
longText.textWrap('{', '}');
```
