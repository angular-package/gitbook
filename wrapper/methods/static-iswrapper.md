# static isWrapper()

## `Wrapper.isWrapper()`

The method checks if the [`value`](static-iswrapper.md#value-any) of any type is an instance of the [`Wrapper`](broken-reference) of any, or given [`opening`](static-iswrapper.md#opening-opening), [`closing`](static-iswrapper.md#closing-closing) chars, and [`text`](static-iswrapper.md#text-text).

{% code title="wrapper.class.ts" %}
```typescript
public static isWrapper<
  Opening extends string,
  Closing extends string,
  Text extends string = string
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

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`opening`](static-iswrapper.md#opening-opening) indicates the type of the opening in the [`Wrapper`](broken-reference) via [return type](static-iswrapper.md#return-type).

#### <mark style="color:green;">**`Closing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`closing`](static-iswrapper.md#closing-closing) indicates the type of the closing in the [`Wrapper`](broken-reference) via [return type](static-iswrapper.md#return-type).

#### <mark style="color:green;">**`Text`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`text`](static-iswrapper.md#text-text) indicates the type of the text in the [`Wrapper`](broken-reference) via [return type](static-iswrapper.md#return-type).

### Parameters

#### `value: any`

The **value** of any type to test against the instance of [`Wrapper`](broken-reference).

#### `opening?: Opening`

Optional **opening** chars of a generic type variable [`Opening`](static-iswrapper.md#openingextendsstring) to check if the given [`value`](static-iswrapper.md#value-any) contains.

#### `closing?: Closing`

Optional **closing** chars of a generic type variable [`Closing`](static-iswrapper.md#closingextendsstring) to check if the given [`value`](static-iswrapper.md#value-any) contains.

#### `text?: Text`

An optional **text** of generic type variable [`Text`](static-iswrapper.md#textextendsstring-string) to check if the given [`value`](static-iswrapper.md#value-any) contains.

### Return type

**`value is Wrapper<Opening, Text, Closing>`**

The **return type** is a [boolean](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) that indicates the [`value`](static-iswrapper.md#value-any) is the [`Wrapper`](broken-reference) instance.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the [`value`](static-iswrapper.md#value-any) is an instance of [`Wrapper`](broken-reference) of any, or the given [`opening`](static-iswrapper.md#opening-opening), [`closing`](static-iswrapper.md#closing-closing) chars, and [`text`](static-iswrapper.md#text-text).

## Example usage

### Returns `true`

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const tagWrapper = new Wrapper('[', ']', 'quote');

// Returns true confirming the type Wrapper<string, string, string>
Wrapper.isWrapper(tagWrapper);

// Returns true confirming the type Wrapper<"[", string, string>
Wrapper.isWrapper(tagWrapper, '[');

// Returns true confirming the type Wrapper<"[", string, "]">
Wrapper.isWrapper(tagWrapper, '[', ']');

// Returns true confirming the type Wrapper<"[", "quote", "]">
Wrapper.isWrapper(tagWrapper, '[', ']', 'quote');

// Returns true confirming the type Wrapper<string, "quote", "]">
Wrapper.isWrapper(tagWrapper, undefined, ']', 'quote');

// Returns true confirming the type Wrapper<"[", "quote", string>
Wrapper.isWrapper(tagWrapper, '[', undefined, 'quote');

// Returns true confirming the type Wrapper<string, "quote", string>
Wrapper.isWrapper(tagWrapper, undefined, undefined, 'quote');

// Returns true confirming the type Wrapper<string, string, "]">
Wrapper.isWrapper(tagWrapper, undefined, ']');

// Returns true confirming the type Wrapper<"[", string, "]">
Wrapper.isWrapper<'[', ']'>(tagWrapper);
```

### Return `false`

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const tagWrapper = new Wrapper('[', ']', 'quote');

// Returns false denying the type Wrapper<"<", string, string>
Wrapper.isWrapper(tagWrapper, '<');

// Returns false denying the type Wrapper<"<", string, ">">
Wrapper.isWrapper(tagWrapper, '<', '>');

// Returns false denying the type Wrapper<"<", "quote", ">">
Wrapper.isWrapper(tagWrapper, '<', '>', 'quote');

// Returns false denying the type Wrapper<string, "quote", ">">
Wrapper.isWrapper(tagWrapper, undefined, '>', 'quote');

// Returns false denying the type Wrapper<"<", "quote", string>
Wrapper.isWrapper(tagWrapper, '<', undefined, 'quote');

// Returns false denying the type Wrapper<string, "no-quote", string>
Wrapper.isWrapper(tagWrapper, undefined, undefined, 'no-quote');

// Returns false denying the type Wrapper<string, string, ">">
Wrapper.isWrapper(tagWrapper, undefined, '>');

// Returns false denying the type Wrapper<"[", "", "]">
Wrapper.isWrapper<'[', ']'>(null as any);
```

### Confirms the wrong type

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const tagWrapper = new Wrapper('[', ']', 'quote');

// Returns true confirming the type Wrapper<"<", string, ">">
Wrapper.isWrapper<'<', '>'>(tagWrapper);
```
