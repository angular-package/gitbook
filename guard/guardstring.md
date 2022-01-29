# ★ guardString()

## `guardString()`

Guards the value to be [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of any type.

{% code title="guard-string.func.ts" %}
```typescript
const guardString = <
  Type extends AnyString,
  Payload extends object = object
>(
  value: Type,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isString(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>

A generic type variable `Type` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](guardstring.md#value-type) via the [return type](guardstring.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardstring.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardstring.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardstring.md#payload-payload) optional parameter of the [`guardString()`](guardstring.md#guardstring) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](guardstring.md#typeextendsanystring) constrained by the [`AnyString`](../types/anystring.md), by default of the type captured from itself to guard.

#### `callback?: ResultCallback<Type, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](guardstring.md#value-type) that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardstring.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardstring.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardstring.md#callback-resultcallback-less-than-type-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardstring.md#value-type) is a generic type variable [`Type`](guardstring.md#typeextendsanystring) by default of the type captured from the [`value`](guardstring.md#value-type).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardstring.md#value-type) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

## Example usage

```typescript
// Example usage.
import { guardString } from '@angular-package/type';

let letFirstName = 'not my name';
guardString(letFirstName); // true; return type `value is string`

const firstName = 'my name';
guardString(firstName); // true; return type `value is "my name"`
```
