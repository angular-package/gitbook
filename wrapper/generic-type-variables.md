# Generic type variables

## `Wrapper<`<mark style="color:green;">`Opening`</mark>`, ...>` <a href="#wrap-opening" id="wrap-opening"></a>

<mark style="color:green;">**`Opening`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `opening` indicates the opening type of a new [`Wrapper`](description.md) instance.

{% code title="wrapper.class.ts" %}
```typescript
class Wrapper<
  Opening extends string = string, // <--- Declare generic type variable Opening.
  Text extends string = '',
  Closing extends string = string
> extends Wrap<Opening, Text, Closing> {
  ...
  constructor(
    opening: Opening, // <--- Capture generic type variable Opening.
    closing: Closing,
    text: Text = '' as Text
  ) {
    super(opening, closing, text);
  }
  ...
}
```
{% endcode %}

## `Wrapper<...,`<mark style="color:green;">`Text`</mark>`, ...>`

#### <mark style="color:green;">**`Text`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`''`**</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `text` indicates the text type of a new [`Wrapper`](description.md) instance.

{% code title="wrapper.class.ts" %}
```typescript
class Wrapper<
  Opening extends string = string,
  Text extends string = '', // <--- Declare generic type variable Text.
  Closing extends string = string
> extends Wrap<Opening, Text, Closing> {
  ...
  constructor(
    opening: Opening,
    closing: Closing,
    text: Text = '' as Text // <--- Capture generic type variable Text.
  ) {
    super(opening, closing, text);
  }
  ...
}
```
{% endcode %}

## `Wrapper<...,`<mark style="color:green;">`Closing`</mark>`>` <a href="#wrap-closing" id="wrap-closing"></a>

#### <mark style="color:green;">**`Closing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `closing` indicates the closing type of a new [`Wrapper`](description.md) instance.

{% code title="wrapper.class.ts" %}
```typescript
class Wrapper<
  Opening extends string = string,
  Text extends string = '',
  Closing extends string = string // <--- Declare generic type variable Closing.
> extends Wrap<Opening, Text, Closing> {
  ...
  constructor(
    opening: Opening,
    closing: Closing, // <--- Capture generic type variable Closing.
    text: Text = '' as Text
  ) {
    super(opening, closing, text);
  }
  ...
}
```
{% endcode %}
