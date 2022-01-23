# guardBoolean()

## `guardBoolean()`

Guards the value to be [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) of any type.

{% code title="guard-boolean.func.ts" %}
```typescript
const guardBoolean = <
  Type extends AnyBoolean,
  Payload extends object = object
>(
  value: Type,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isBoolean(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyBoolean`**</mark>

A generic type variable `Type` constrained by generic type [`AnyBoolean`](../type/anyboolean.md) indicates captured [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) type of the given [`value`](guardboolean.md#value-type) via the [return type](guardboolean.md#return-type) and the [`value`](../type/resultcallback.md#value-value) parameter of the provided [`callback`](guardboolean.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../type/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../type/resultcallback.md#payload-payload) of the supplied [`callback`](guardboolean.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardboolean.md#payload-payload) optional parameter of the [`guardBoolean()`](guardboolean.md#guardboolean) function from which it captures its value.

### Parameters

#### `value: Type`

The value of generic type variable [`Type`](guardboolean.md#bigint) to guard.

#### `callback?: ResultCallback<bigint, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardboolean.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardboolean.md#payloadextendsobject-object) is assigned to the [`payload`](../type/resultcallback.md#payload-payload) of the given [`callback`](guardboolean.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardboolean.md#value-type) is a generic type variable [`Type`](guardboolean.md#bigint) by default of type captured from the supplied [`value`](guardboolean.md#value-type).

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the [`value`](guardboolean.md#value-type) is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) type or an instance of [`Boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean).

### Example usage

```typescript
// Example usage.
import { guardBoolean } from '@angular-package/type';

guardBoolean(true), // true, value is boolean
guardBoolean(new Boolean(false)) // true, value is Boolean
```
