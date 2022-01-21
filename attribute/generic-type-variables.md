# Generic type variables

### Attribute`<`<mark style="color:green;">`Name`</mark>`, ...>` <a href="#wrap-opening" id="wrap-opening"></a>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `name` indicates the opening type of a new [`Attribute`](attribute.md) instance.

```typescript
class Attribute<
  Name extends string = string, // <--- Declare generic type variable Name.
  Value extends string = string
> extends String {
  ...
  constructor(
    name: Name,   // <--- Capture generic type variable Name.
    value: Value  
  ) { ... }
  ...
}
```



### `Attribute<...,`<mark style="color:green;">`Value`</mark>`>`

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value captured from the provided `value` indicates the value type of a new [`Attribute`](attribute.md) instance.

```typescript
class Attribute<
  Name extends string = string,
  Value extends string = string // <--- Declare generic type variable Value.
> extends String {
  ...
  constructor(
    name: Name,
    value: Value  // <--- Capture generic type variable Value.
  ) { ... }
  ...
}
```
