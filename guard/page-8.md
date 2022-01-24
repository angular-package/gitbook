# guardDate()

## `guardDate()`

Guards the value to be a date.

{% code title="guard-date.func.ts" %}
```typescript
const guardDate = <Payload extends object>(
  value: Date,
  callback?: ResultCallback<Date, Payload>,
  payload?: Payload
): value is Date => isDate(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](page-8.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-8.md#payload-payload) optional parameter of the [`guardDate()`](page-8.md#guarddate) function from which it captures its value.

### Parameters

#### `value: Date`

The value of [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date) type to guard.

#### `callback?: ResultCallback<Class, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-8.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-8.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](page-8.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Date`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement [`value`](page-8.md#value-is-date) is [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the `value` is a [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

### Example usage

```typescript
// Example usage.
import { guardDate } from '@angular-package/type';

guardDate(new Date('December 17, 1995 03:24:00')); // true, value is Date
guardDate(new Date('1995-12-17T03:24:00')); // true, value is Date
guardDate(new Date(1995, 11, 17)); // true, value is Date
guardDate(new Date(1995, 11, 17, 3, 24, 0)); // true, value is Date
guardDate(new Date(628021800000)); // true, value is Date
```
