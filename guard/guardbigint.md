# guardBigInt()

### `guardBigInt()`

Guards the value to be a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt).

{% code title="guard-bigint.func.ts" %}
```typescript
const guardBigInt = <
  BigInt extends bigint,
  Payload extends object = object
>(
  value: BigInt,
  callback?: ResultCallback<BigInt, Payload>,
  payload?: Payload
): value is BigInt => isBigInt(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`BigInt`**</mark>**`extends`**<mark style="color:green;">**`bigint`**</mark>

A generic type variable `BigInt` constrained by the [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) indicates captured [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type of the given `value` via the [return type](guardbigint.md#return-type) and the `value` parameter of the provided callback function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

#### `value: BigInt`

A [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type value to guard.

#### `callback: ResultCallback<bigint, Payload>`

A callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardbigint.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of generic type variable [`Payload`](guardbigint.md#payloadextendsobject-object) is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is BigInt`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the `value` is [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt).

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the `value` is a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt).

### Example usage

```typescript
// Example usage.
import { guardBigInt } from '@angular-package/type';

guardBigInt(1n); // true, value is bigint
guardBigInt(false as any); // false, value is bigint
```

