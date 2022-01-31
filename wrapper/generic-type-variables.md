# Generic type variables

## `Wrapper<`<mark style="color:green;">`Opening`</mark>`, ...>` <a href="#wrap-opening" id="wrap-opening"></a>

<mark style="color:green;">**`Opening`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `opening` indicates the opening type of a new [`Wrapper`](description.md) instance.

## `Wrapper<...,`<mark style="color:green;">`Text`</mark>`, ...>`

<mark style="color:green;">**`Text`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`''`**</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `text` indicates the text type of a new [`Wrapper`](description.md) instance.

## `Wrapper<...,`<mark style="color:green;">`Closing`</mark>`>` <a href="#wrap-closing" id="wrap-closing"></a>

<mark style="color:green;">**`Closing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `closing` indicates the closing type of a new [`Wrapper`](description.md) instance.
