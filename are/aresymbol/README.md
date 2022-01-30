# areSymbol()

## `areSymbol()`

Checks whether the values are a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-symbol.func.ts" %}
```typescript
const areSymbol = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isSymbol, ...values);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/are/lib/are-symbol.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check its elements against a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type.

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with `every()`, `some()` and `forEach()` as methods of checking supplied [`values`](./#...values-any).
