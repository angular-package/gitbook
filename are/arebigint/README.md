# areBigInt()

## `areBigInt()`

Checks whether the values are a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type by using [`every()`](every.md), [`forEach()`](foreach.md) and [`some()`](some.md) methods of the returned object.

{% code title="are-bigint.func.ts" %}
```typescript
const areBigInt = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isBigInt, ...values);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/are/lib/are-bigint.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check its elements against a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type.

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of [`every()`](every.md), [`some()`](some.md) and [`forEach()`](foreach.md) as methods of checking supplied [`values`](./#...values-any).
