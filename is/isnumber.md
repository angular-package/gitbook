# ★ isNumber()

### `isNumber()`

Checks if any value is a `number` type, or the type obtained from its `Object.prototype` equal to `'number'` or an `object` type and an instance of `Number`. The value is also checked by the `Number.isFinite()` method to determine whether it's finite and is validated by the `Number.isNaN()` method.

Use `isNumber()` or `is.number()` to check if **any** value is a \[`number`]\[js-number] type, or the type obtained from its `Object.prototype` equal to `'number'` or an \[`object`]\[js-object] type and an instance of \[`Number`]\[js-number]. The value is also checked by the \[`Number.isFinite()`]\[js-numberisfinite] method to determine whether it's **finite** and is **validated** by the \[`Number.isNaN()`]\[js-numberisnan] method.

{% code title="is-number.func.ts" %}
```typescript
const isNumber = <
  Type extends AnyNumber = number,
  Payload extends object = object
>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Type =>
  callback(
    (typeof value === 'number' ||
    ((typeOf(value) === 'number' || typeof value === 'object') &&
      value instanceof Number)) &&
    !Number.isNaN(value.valueOf()) &&
    Number.isFinite(value.valueOf()),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

Type

A generic type variable `Type` guarded by `AnyNumber` by default of `number` indicates the type of the `value` via the return type `value is Type`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnumber.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnumber.md#payload-payload) optional parameter of the [`isNumber()`](isnumber.md#isnumber) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnumber.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnumber.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type variable `Type` constrained by `AnyNumber` by default of `number` type.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is a `number` type or an instance of \[`Number`]\[js-number].

### Example usage

```typescript
// Example usage.
import { isNumber } from '@angular-package/type';

isNumber(10304050); // true, value is number
isNumber(Number(10304050)); // true, value is number
isNumber(new Number(10304050)); // true, value is number
isNumber<Number>(new Number(10304050)); // true, value is Number
```
