# guardBigInt()

## `guardBigInt()`

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

A generic type variable `BigInt` constrained by the [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) indicates captured [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type of the given [`value`](guardbigint.md#value-bigint) via the [return type](guardbigint.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardbigint.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardbigint.md#callback-resultcallback-less-than-bigint-payload-greater-than) function and [`payload`](guardbigint.md#payload-payload) optional parameter of the [`guardBigInt()`](guardbigint.md#guardbigint) function from which it captures its value.

### Parameters

#### `value: BigInt`

A [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type value to guard.

#### `callback?: ResultCallback<BigInt, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](guardbigint.md#value-bigint) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](guardbigint.md#payloadextendsobject-object) with optional properties from the provided [`payload`](guardbigint.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardbigint.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardbigint.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is BigInt`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardbigint.md#value-bigint) is [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt).

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the [`value`](guardbigint.md#value-bigint) is a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt).

## Example usage

```typescript
// Example usage.
import { guardBigInt } from '@angular-package/type';

guardBigInt(1n); // true, value is bigint
guardBigInt(false as any); // false, value is bigint
```
