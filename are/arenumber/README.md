# ★ areNumber()

## `areFalse()`

Checks whether the values are [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null) by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-number.func.ts" %}
```typescript
const areNumber = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isNumber, ...values);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/are/lib/are-number.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check its elements against a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with `every()`, `some()` and `forEach()` as methods of checking supplied [`values`](./#...values-any).
