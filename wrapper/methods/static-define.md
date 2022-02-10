# static define()

## `Wrapper.define()`

Defines a new [`Wrapper`](broken-reference) instance with the provided [`opening`](static-define.md#opening-opening), [`closing`](static-define.md#closing-closing) chars, and optional [`text`](static-define.md#text-text).

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

#### <mark style="color:green;">**`Opening`**</mark>**`extends`**[<mark style="color:green;">**`string`**</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`opening`](static-define.md#opening-opening) indicates the type of the opening in the [`Wrapper`](broken-reference) via [return type](static-define.md#return-type).

#### <mark style="color:green;">**`Closing`**</mark>**`extends`**[<mark style="color:green;">**`string`**</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">**``**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`closing`](static-define.md#closing-closing) indicates the type of the closing in the [`Wrapper`](broken-reference) via [return type](static-define.md#return-type).

#### <mark style="color:green;">**`Text`**</mark>**`extends`**[<mark style="color:green;">**`string`**</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)**`=`**<mark style="color:green;">**`''`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`text`](static-define.md#text-text) indicates the type of the text in the [`Wrapper`](broken-reference) via [return type](static-define.md#return-type).

### Parameters

#### `opening:`[<mark style="color:green;">`Opening`</mark>](static-define.md#openingextendsstring)<mark style="color:green;">``</mark>

The **opening** chars of generic type variable [`Opening`](static-define.md#openingextendsstring) for new [`Wrapper`](broken-reference) instance.

#### `closing:`[<mark style="color:green;">`Closing`</mark>](static-define.md#closingextendsstring)<mark style="color:green;">``</mark>

The **closing** chars of generic type variable [`Closing`](static-define.md#closingextendsstring) for new [`Wrapper`](broken-reference) instance.

#### `text?:`[<mark style="color:green;">`Text`</mark>](static-define.md#textextendsstring)<mark style="color:green;">``</mark>

An optional **text** of generic type variable [`Text`](static-define.md#textextendsstring) for new [`Wrapper`](broken-reference) instance.

### Return type

#### `Wrapper<Opening, Text, Closing>`

The **return type** is the [`Wrapper`](broken-reference) object that takes generic type variables [`Opening`](static-define.md#openingextendsstring), [`Text`](static-define.md#textextendsstring), and [`Closing`](static-define.md#closingextendsstring).

### Returns

The **return value** is the [`Wrapper`](broken-reference) instance of given [`opening`](static-define.md#opening-opening), [`closing`](static-define.md#closing-closing) chars, and optional [`text`](static-define.md#text-text).

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
