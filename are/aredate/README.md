# areDate()

## `areDate()`

Checks whether the values are [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date) by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-date.func.ts" %}
```typescript
const areDate = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isDate, ...values);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check its elements against [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of `every()`, `some()` and `forEach()` as methods of checking supplied [`values`](./#...values-any).
