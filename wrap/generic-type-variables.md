---
description: The `Wrap` primitive wrapper object generic type variables
---

# Generic type variables

## `Wrap<`<mark style="color:green;background-color:green;">`Opening`</mark>`,`<mark style="color:green;">`Text`</mark>`,`<mark style="color:green;">`Closing`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Opening`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`string`</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`opening`](constructor.md#opening-opening) indicates the opening type of a new [`Wrap`](broken-reference) instance.

{% code title="wrap.class.ts" %}
```typescript
class Wrap<
  Opening extends string = string, // <--- Declare generic type variable Opening.
  Text extends string = ``,
  Closing extends string = string
> extends String {
  ...
  constructor(
    opening: Opening, // <--- Capture generic type variable Opening.
    closing: Closing,
    text: Text = '' as Text
  ) { ... }
  ...
}
```
{% endcode %}

## `Wrap<`<mark style="color:green;">`Opening`</mark>`,`<mark style="color:green;background-color:green;">`Text`</mark>`,`<mark style="color:green;">`Closing`</mark>`>`

#### <mark style="color:green;">`Text`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">` `` `</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`text`](constructor.md#text-text) indicates the text type of a new [`Wrap`](broken-reference) instance.

{% hint style="info" %}
The constructor **`text`** parameter is optional, and if not provided, the default value of the generic type variable [`Text`](generic-type-variables.md#wrap-less-than...-text-...greater-than) is not captured, but it's an empty [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) from the declaration.
{% endhint %}

{% code title="wrap.class.ts" %}
```typescript
class Wrap<
  Opening extends string = string,
  Text extends string = ``, // <--- Declare generic type variable Text.
  Closing extends string = string
> extends String {
  ...
  constructor(
    opening: Opening,
    closing: Closing,
    text: Text = '' as Text  // <--- Capture generic type variable Text.
  ) { ... }
  ...
}
```
{% endcode %}

## `Wrap<`<mark style="color:green;">`Opening`</mark>`,`<mark style="color:green;">`Text`</mark>`,`<mark style="color:green;background-color:green;">`Closing`</mark>`>` <a href="#wrap-closing" id="wrap-closing"></a>

#### <mark style="color:green;">`Closing`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`string`</mark>

​A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value **captured** from the provided [`closing`](constructor.md#closing-closing) indicates the closing type of a new [`Wrap`](broken-reference) instance.

{% code title="wrap.class.ts" %}
```typescript
class Wrap<
  Opening extends string = string,
  Text extends string = ``,
  Closing extends string = string // <--- Declare generic type variable Closing.
> extends String {
  ...
  constructor(
    opening: Opening,
    closing: Closing, // <--- Capture generic type variable Closing.
    text: Text = '' as Text
  ) { ... }
  ...
}
```
{% endcode %}
