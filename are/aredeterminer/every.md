# every()

### `areDeterminer().every()`

Checks whether every of the provided `values` in the array pass the test implemented by the given `checkFn`.

{% code title="are-determiner.func.ts" %}
```typescript
{
  every: <Payload extends CommonPayload>(
    callback: ResultCallback<any, Payload> = resultCallback,
    payload?: Payload
  ): boolean =>
    callback(
      values.every((value) => checkFn(value)),
      values,
      payload
    ),
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`CommonPayload`**</mark>

The `Payload` generic type variable constrained by generic type variable [`CommonPayload`](./#commonpayloadextendsobject) indicates the type of the `payload` parameter from which it gets its value.

### Parameters

#### callback: <mark style="color:yellow;">ResultCallback</mark>\<any, Payload>



A callback `function` of [`ResultCallback`](../../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

`payload?: Payload`

Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `values` passed the test by given `checkFn`.

### Example usage

```typescript
// Example usage.
import { areDeterminer } from '@angular-package/type';

```
