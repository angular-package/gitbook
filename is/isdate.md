# isDate()

### `isDate()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'date'` or an `object` type, and an instance of [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date). The value is checked against a valid date by using [`isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/isNaN) method.

{% code title="is-date.func.ts" %}
```typescript
const isDate = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Date =>
  callback(
    (typeOf(value) === 'date' || typeof value === 'object') &&
    value instanceof Date === true &&
    !isNaN(value),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isdate.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isdate.md#payload-payload) optional parameter of the [`isDate()`](isdate.md#isdate) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isdate.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isdate.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Date`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the `value` is a [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a date.

### Example usage

```typescript
// Example usage.
import { isDate } from '@angular-package/type';

const DATE = new Date(1995, 11, 17, 3, 24, 0);

isDate(new Date('December 17, 1995 03:24:00')), // true
isDate(new Date('1995-12-17T03:24:00')), // true
isDate(new Date(1995, 11, 17)), // true
isDate(new Date(628021800000)), // true
isDate(DATE); // Returns `true` as `value is Date`

// Example usage with callback and payload.
isDate(DATE, (result, payload) => {
  if (payload) {
    result // Returns `true`
    payload.value // Returns new date
    payload.birthDay // Returns `14`
  }
  return result;
}, { birthDay: 14 }); // Returns `true` as `value is Date`
```
