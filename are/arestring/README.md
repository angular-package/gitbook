# ★ areString()

## `areString()`

Checks whether the values are a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-string.func.ts" %}
```typescript
const areString = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isString, ...values);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check its elements against a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with `every()`, `some()` and `forEach()` as methods of checking supplied [`values`](./#...values-any).
