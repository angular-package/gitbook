# Generic type variables

### `Wrap<`<mark style="color:green;">`Opening`</mark>`, ...>` <a href="#wrap-opening" id="wrap-opening"></a>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `opening` indicates the opening type of a new [`Wrap`](wrap.md) instance.

```typescript
export class Wrap<
  Opening extends string = string
  ...
> extends String {}
```



### `Wrap<...,`<mark style="color:green;">`Text`</mark>`, ...>`

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `text` indicates the text type of a new [`Wrap`](wrap.md) instance.

```typescript
export class Wrap<
  ...,
  Text extends string = ``,
  ...
> extends String {}
```



### `Wrap<...,`<mark style="color:green;">`Closing`</mark>`>` <a href="#wrap-closing" id="wrap-closing"></a>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `closing` indicates the closing type of a new [`Wrap`](wrap.md) instance.

```typescript
export class Wrap<
  ...
  Closing extends string = string
> extends String {}
```
