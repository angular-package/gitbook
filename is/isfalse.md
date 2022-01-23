# ★ isFalse()

### `isFalse()`

Checks if any value is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) by using [`isBoolean()`](isboolean.md) function, that is equal to `false`.

{% code title="is-false.func.ts" %}
```typescript
const isFalse = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is false =>
  callback(
    isBoolean(value) ? value.valueOf() === false : false,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of the `payload` parameter of the main function from which it gets its value and `payload` parameter of a given `callback` function [`ResultCallback`](../type/resultcallback.md) type.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](isfalse.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of generic type variable [`Payload`](isfalse.md#payloadextendsobject) is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is false`

The **return type** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) as the result of its statement, indicating the `value` is equal to `false`.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) that is equal to `false`.

### Example usage

```typescript
// Example usage.
import { isFalse } from '@angular-package/type';

isFalse(true); // Returns `false` as `value is false`
isFalse(false); // Returns `true` as `value is false`

isFalse(new Boolean(true)); // Returns `false` as `value is false`
isFalse(new Boolean(false)); // Returns `true` as `value is false`

// Example usage with callback and payload.
isFalse(new Boolean(false), (result, value, payload) => {
  value // Returns `Boolean {false}`
  if (payload) {
    result // Returns `false`
    payload.age // Returns `27`
  }
  return result;
}, { age: 27 }); // Returns `true` as `value is false`
```
