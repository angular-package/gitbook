# isWrapper()

## `Wrapper.isWrapper()`

The method checks if the [`value`](iswrapper.md#value-any) of any type is an instance of the [`Wrapper`](../../overview.md) of any, or given [`opening`](iswrapper.md#opening-opening), [`closing`](iswrapper.md#closing-closing) chars, and [`text`](iswrapper.md#text-text).

{% code title="wrapper.class.ts" %}
```typescript
public static isWrapper<
  Opening extends string,
  Closing extends string,
  Text extends string = ''
>(
  value: any,
  opening?: Opening,
  closing?: Closing,
  text?: Text
): value is Wrapper<Opening, Text, Closing> {
  return (
    typeof value === 'object' &&
    value instanceof this &&
    super.isWrap(value, opening, closing, text)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Opening`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`opening`](iswrapper.md#opening-opening) indicates the type of the opening in the [`Wrapper`](../../overview.md) via [return type](iswrapper.md#return-type).

#### <mark style="color:green;">**`Closing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`closing`](iswrapper.md#closing-closing) indicates the type of the closing in the [`Wrapper`](../../overview.md) via [return type](iswrapper.md#return-type).

#### <mark style="color:green;">**`Text`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`''`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`text`](iswrapper.md#text-text) indicates the type of the text in the [`Wrapper`](../../overview.md) via [return type](iswrapper.md#return-type).

### Parameters

#### `value: any`

The **value** of any type to test against the instance of [`Wrapper`](../../overview.md).

#### `opening?: Opening`

Optional **opening** chars of a generic type variable [`Opening`](iswrapper.md#openingextendsstring) to check if the given [`value`](iswrapper.md#value-any) contains.

#### `closing?: Closing`

Optional **closing** chars of a generic type variable [`Closing`](iswrapper.md#closingextendsstring) to check if the given [`value`](iswrapper.md#value-any) contains.

#### `text?: Text`

An optional **text** of generic type variable [`Text`](iswrapper.md#textextendsstring) to check if the given [`value`](iswrapper.md#value-any) contains.

### Return type

**`value is Wrapper<Opening, Text, Closing>`**

The **return type** is a boolean that indicates the [`value`](iswrapper.md#value-any) is the [`Wrapper`](broken-reference) instance.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the value is an instance of [`Wrapper`](../../overview.md) of any, or the given [`opening`](iswrapper.md#opening-opening), [`closing`](iswrapper.md#closing-closing) chars, and [`text`](iswrapper.md#text-text).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const tagWrapper = new Wrapper('[', ']');

// Returns true confirming the type Wrapper<string, "", string>
Wrapper.isWrapper(tagWrapper);

// Returns true confirming the type Wrapper<"[", "", "]">
Wrapper.isWrapper<'[', ']'>(tagWrapper);

// Returns false denying the type Wrapper<"[", "", "]">
Wrapper.isWrapper<'[', ']'>(null as any);
```
