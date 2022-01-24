# areDeterminer()

## `areDeterminer()`

The helper function returns the object with [`every()`](every.md), [`forEach()`](foreach.md) and [`some()`](some.md) methods to check given [`values`](./#...values-any) by the given [`checkFn`](./#checkfn-function) function.

{% code title="are-determiner.func.ts" %}
```typescript
const areDeterminer = <CommonPayload extends object>(
  checkFn: Function,
  ...values: any[]
) => {
  return {
    every: <Payload extends CommonPayload>(
      callback: ResultCallback<any, Payload> = resultCallback,
      payload?: Payload
    ): boolean =>
      callback(
        values.every((value) => checkFn(value)),
        values,
        payload
      ),

    forEach: <Payload extends CommonPayload>(
      forEachCallback: ForEachCallback<any, Payload>,
      payload?: Payload
    ) => {
      isArray(values) &&
        isFunction(forEachCallback) &&
        values.forEach((value, index) =>
          forEachCallback(checkFn(value), value, index, values, payload)
        );
    },

    some: <Payload extends CommonPayload>(
      callback: ResultCallback<any, Payload> = resultCallback,
      payload?: Payload
    ): boolean =>
      callback(
        isArray(values) ? values.some((value) => checkFn(value)) : false,
        values,
        payload
      ),
  };
};
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`CommonPayload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `CommonPayload` generic type variable constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) constrains the generic type variable `Payload` of each returned method.

### Parameters

#### `checkFn: Function`

Function to test given [`values`](./#...values-any).

#### `...values: any[]`

A rest parameter of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check its elements against test given in the [`checkFn`](./#checkfn-function).

### Returns

The **return value** is an [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of [`every()`](every.md), [`some()`](some.md) and [`forEach()`](foreach.md) as methods of checking supplied [`values`](./#...values-any).
