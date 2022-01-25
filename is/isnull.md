# isNull()

### `isNull()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'null'` or an `object` type that is equal to `null`.

Use `isNull()` or `is.null()` to check if **any** value is of the type obtained from its `Object.prototype` equal to `'null'` or an \[`object`]\[js-object] type that is equal to \[`null`]\[js-null].

{% code title="is-null.func.ts" %}
```typescript
const isNull = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is null =>
  callback(
    (typeOf(value) === 'null' || typeof value === 'object') && value === null,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnull.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnull.md#payload-payload) optional parameter of the [`isNull()`](isnull.md#isnull) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnull.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnull.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

`value is null`

The **return type** is a `boolean` as the result of its statement.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is \[`null`]\[js-null].

### Example usage

```typescript
// Example usage.
import { isNull } from '@angular-package/type';

isNull(null); // true
isNull(27); // false
```
