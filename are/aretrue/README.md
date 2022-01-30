# ★ areTrue()

## `areTrue()`

Checks whether the values are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `true` by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-true.func.ts" %}
```typescript
const areTrue = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isTrue, ...values);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/are/lib/are-true.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check its elements against a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `true`.

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of `every()`, `some()` and `forEach()` as methods of checking supplied [`values`](./#...values-any).
