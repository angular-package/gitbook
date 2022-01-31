# isWrap()

## `Wrap.isWrap()`

The method checks whether the [`value`](iswrap.md#value-any) of any type is the [`Wrap`](../../info/) instance of any or given [`opening`](iswrap.md#opening-opening) and [`closing`](iswrap.md#closing-closing) chars.

{% code title="wrap.class.ts" %}
```typescript
public static isWrap<
  Opening extends string = string,
  Closing extends string = string,
  Text extends string = ``
>(
  value: any,
  opening?: Opening,
  closing?: Closing,
  text?: Text
): value is Wrap<Opening, Text, Closing> {
  return typeof value === 'object' && value instanceof this
    ? (typeof opening === 'string' ? opening === value.opening : true) &&
        (typeof closing === 'string' ? closing === value.closing : true) &&
        (typeof text === 'string' ? text === value.text : true)
    : false;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Opening`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`opening`](iswrap.md#opening-opening) indicates the `Opening` type of the [`Wrap`](../../info/) instance the [return type](iswrap.md#return-type).

#### <mark style="color:green;">**`Closing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`closing`](iswrap.md#closing-closing) indicates the `Closing` type of the [`Wrap`](../../info/) instance via [return type](iswrap.md#return-type).

#### <mark style="color:green;">**`Text`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**` `` `**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`text`](iswrap.md#text-text) indicates the `Text` type of the [`Wrap`](../../info/) instance via [return type](iswrap.md#return-type).

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Wrap`](../../info/) instance of any or given [`opening`](iswrap.md#opening-opening) and [`closing`](iswrap.md#closing-closing).

#### `opening?: Opening`

Optional opening chars of a generic type variable [`Opening`](iswrap.md#openingextendsstring-string) to check if the given [`value`](iswrap.md#value-any) contains.

#### `closing?: Closing`

Optional closing chars of a generic type variable [`Closing`](iswrap.md#closingextendsstring-string) to check if the given [`value`](iswrap.md#value-any) contains.

#### `text?: Text`

An optional text of a generic type variable [`Text`](iswrap.md#textextendsstring) to check if the given [`value`](iswrap.md#value-any) contains.

### Return type

**`value is Wrap<Opening, Text, Closing>`**

The return type is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating the [`value`](iswrap.md#value-any) parameter is an instance of [`Wrap`](../../info/) that takes a generic type variable [`Opening`](iswrap.md#openingextendsstring-string) [`Text`](iswrap.md#textextendsstring) and [`Closing`](iswrap.md#closingextendsstring-string).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the value is an instance of [`Wrap`](broken-reference) of any, or the given [`opening`](iswrap.md#opening-opening), [`closing`](iswrap.md#closing-closing), and [`text`](iswrap.md#text-text).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

const tagWrap = new Wrap(`[`, `]`, 'quote');

// Returns true confirming the type Wrap<"[", "", "]">
Wrap.isWrap(tagWrap);

// Returns true, confirming the type Wrap<"[", "", "]">
Wrap.isWrap(tagWrap, '[', ']');

// Returns true, confirming the type Wrap<"[", "quote", "]">
Wrap.isWrap(tagWrap, '[', ']', 'quote');

// Returns true, confirming the type Wrap<"[", "", "]">
Wrap.isWrap<'[', ']'>(tagWrap, '[', ']');

// Returns false, denying the type Wrap<"[", "span", "]">
Wrap.isWrap(tagWrap, '[', ']', 'span');

// Returns false denying the value is Wrap<"(", "", ")">
Wrap.isWrap(tagWrap, '(', ')');

// Returns false denying the value is Wrap<"(", "", ")">
Wrap.isWrap<'[', ']'>(null as any);

// Returns false denying the value is Wrap<"[", "", "]">
Wrap.isWrap(null as any, '[', ']');
```
