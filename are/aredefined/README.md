# areDefined()

## `areDefined()`

Checks whether the **values** are **defined** by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-date.func.ts" %}
```typescript
const areDate = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isDate, ...values);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/are/lib/are-defined.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check whether its elements are defined.

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of [`every()`](https://app.gitbook.com/s/HmRqpb9wXbHlBaTRCXZm/c/zkFcxLE4HTwIcknJCu1A/are/areboolean/every), [`some()`](https://app.gitbook.com/s/HmRqpb9wXbHlBaTRCXZm/c/zkFcxLE4HTwIcknJCu1A/are/areboolean/some) and [`forEach()`](https://app.gitbook.com/s/HmRqpb9wXbHlBaTRCXZm/c/zkFcxLE4HTwIcknJCu1A/are/areboolean/foreach) as methods of checking supplied [`values`](./#...values-any).
