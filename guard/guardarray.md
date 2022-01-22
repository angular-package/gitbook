# guardArray()

### `guardArray()`

Guards the value to be an [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of a generic type variable `Type`.

{% code title="guard-array.func.ts" %}
```typescript
const guardArray = <Type, Payload extends object = object>(
  value: Array<Type>,
  callback?: ResultCallback<Array<Type>, Payload>,
  payload?: Payload
): value is Array<Type> =>
  isArray(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

A generic type variable `Type` indicates captured [`array`](https://www.typescriptlang.org/docs/handbook/basic-types.html#array) element type of the given `value` via the [return type](guardarray.md#return-type) and the `value` parameter of the provided `callback` function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by object indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

#### `value: Array<Type>`

An [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of generic type variable [`Type`](guardarray.md#type-any) to guard.

#### `callback: ResultCallback<Array<Type>, Payload>`

A callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardarray.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of generic type variable [`Payload`](guardarray.md#payloadextendsobject-object) is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is Array<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the `value` is an [`Array`](https://www.typescriptlang.org/docs/handbook/basic-types.html#array) of a generic type variable [`Type`](guardarray.md#type), by default equal to the array element type of the supplied `value`.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the `value` is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of a generic type variable [`Type`](guardarray.md#type-any).

### Example usage

```typescript
// Example usage.
import { guardArray } from '@angular-package/type';

guardArray([1, 2, 3]); // true. value is number[]
guardArray([1, '2', 3]);  // true. value is (string | number)[]
guardArray([1, '2', 3n]); // true value is (string | number | bigint)[]
guardArray([1, '2', 3n, undefined]);
guardArray([1, '2', 3n, undefined, null]);
guardArray([1, '2', 3n, undefined, null, Symbol(6), ]);
guardArray([1, '2', 3n, undefined, null, Symbol(6), true]);
```
