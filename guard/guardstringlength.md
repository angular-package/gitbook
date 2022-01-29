# guardStringLength()

## `guardStringLength()`

Guards the value to be [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) instance of a specified [`length`](guardstringlength.md#length-length).

{% code title="guard-string-length.func.ts" %}
```typescript
const guardStringLength = <
  Type extends AnyString,
  Length extends number,
  Payload extends object = object
>(
  value: Type,
  length: Length,
  callback?: ResultCallback<Type, { length: Length } & Payload>,
  payload?: Payload
): value is StringOfLength<Length, Length, Type> =>
  isStringLength(value, length, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>

A generic type variable `Obj` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](guardstringlength.md#value-type) via the [return type](guardstringlength.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardstringlength.md#callback-resultcallback-less-than-type-length-length-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Length`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Length` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`length`](guardstringlength.md#length-length) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](guardstringlength.md#callback-resultcallback-less-than-type-length-length-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type and the **length** of the provided [`value`](guardstringlength.md#value-type) via the [return type](guardstringlength.md#return-type).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardstringlength.md#callback-resultcallback-less-than-type-length-length-and-payload-greater-than) function and [`payload`](guardstringlength.md#payload-payload) optional parameter of the [`guardStringLength()`](guardstringlength.md#guardstringlength) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](guardstringlength.md#typeextendsanystring) constrained by [`AnyString`](../types/anystring.md), by default of the type captured from itself to guard.

#### `length: Length`

The **length** of generic type variable [`Length`](guardstringlength.md#lengthextendsnumber) of a given [`value`](guardstringlength.md#value-type).

#### `callback?: ResultCallback<Type, { length: Length } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](guardstringlength.md#value-type) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](guardstringlength.md#payloadextendsobject) with optional properties from the provided [`payload`](guardstringlength.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The **`payload`** parameter of given `callback` function consists of the **`length`** property of the given [`length`](guardstringlength.md#length-length), and it can't be overwritten by the given [`payload`](guardstringlength.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardstringlength.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardstringlength.md#callback-resultcallback-less-than-type-length-length-and-payload-greater-than) function.

### Return type

#### `value is StringOfLength<Length, Length, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the [`value`](guardstringlength.md#value-type) is a generic type [`StringOfLength`](../types/stringoflength.md) that takes generic type variable `Min` and `Max`(from the provided [`length`](guardstringlength.md#length-length) parameter) as the **length** of the supplied [`value`](guardstringlength.md#value-type), and [`Type`](guardstringlength.md#typeextendsanystring) as the type of the supplied [`value`](guardstringlength.md#value-type).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardstringlength.md#value-type) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of a specified [`length`](guardstringlength.md#length-length).

## Example usage

```typescript
// Example usage.
import { guardStringLength } from '@angular-package/type';

// true; return type `value is StringOfLength<11, 11, "not my name">`
guardStringLength('not my name', 11);
// false; return type `value is StringOfLength<10, 10, "not my name">` 
guardStringLength('not my name', 10);
// false; return type `value is StringOfLength<12, 12, "not my name">`
guardStringLength('not my name', 12);
```
