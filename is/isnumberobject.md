# isNumberObject()

### `isNumberObject()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'number'`, or an `object` type and an instance of `Number` and is also checked by the `isFinite()` method to determine whether it's finite and is validated by the `Number.isNaN()` method.

{% code title="is-number-object.func.ts" %}
```typescript
const isNumberObject = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Number =>
  callback(
    (typeOf(value) === 'number' || typeof value === 'object') &&
    value instanceof Number &&
    !Number.isNaN(value.valueOf()) &&
    Number.isFinite(value.valueOf()),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnumberobject.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnumberobject.md#payload-payload) optional parameter of the [`isNumberObject()`](isnumberobject.md#isnumberobject) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnumberobject.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnumberobject.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isNumberObject } from '@angular-package/type';

```

