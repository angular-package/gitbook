# define()

## `Wrapper.define()`

Defines a new [`Wrapper`](../../overview.md) instance with the provided [`opening`](define.md#opening-opening), [`closing`](define.md#closing-closing) chars, and optional [`text`](define.md#text-text).

{% code title="wrapper.class.ts" %}
```typescript
public static define<
  Opening extends string,
  Closing extends string,
  Text extends string = ''
>(
  opening: Opening,
  closing: Closing,
  text?: Text
): Wrapper<Opening, Text, Closing> {
  return new this(opening, closing, text);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Opening`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`opening`](define.md#opening-opening) indicates the type of the opening in the [`Wrapper`](broken-reference) via [return type](define.md#return-type).

#### <mark style="color:green;">**`Closing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`closing`](define.md#closing-closing) indicates the type of the closing in the [`Wrapper`](broken-reference) via [return type](define.md#return-type).

#### <mark style="color:green;">**`Text`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`''`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`text`](define.md#text-text) indicates the type of the text in the [`Wrapper`](broken-reference) via [return type](define.md#return-type).

### Parameters

#### `opening: Opening`

The **opening** chars of generic type variable [`Opening`](define.md#openingextendsstring) for new [`Wrapper`](../../overview.md) instance.

#### `closing: Closing`

The **closing** chars of generic type variable [`Closing`](define.md#closingextendsstring) for new [`Wrapper`](../../overview.md) instance.

#### `text?: Text`

An optional **text** of generic type variable [`Text`](define.md#textextendsstring) for new [`Wrapper`](../../overview.md) instance.

### Return type

#### `Wrapper<Opening, Text, Closing>`

The return type is the [`Wrapper`](broken-reference) object that takes generic type variables [`Opening`](define.md#openingextendsstring), [`Text`](define.md#textextendsstring), and [`Closing`](define.md#closingextendsstring).

### Returns

The **return value** is the [`Wrapper`](../../overview.md) instance of given [`opening`](define.md#opening-opening), [`closing`](define.md#closing-closing) chars, and optional [`text`](define.md#text-text).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

// Returns Wrapper {'()'}
// of type Wrapper<"(", "", ")">
Wrapper.define('(', ')');

// Returns Wrapper {'!!'}
// of type Wrapper<"!", "", "!">
Wrapper.define('!', '!');

// Returns Wrapper {'"This is quoted text"'}
// of type Wrapper<"\"", "This is quoted text", "\"">
Wrapper.define('"', '"', 'This is quoted text');
```
