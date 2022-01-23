# guardStringLength()

## `guardStringLength()`

Guards the value to be a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of a length between the specified range.

{% code title="guard-string-length.func.ts" %}
```typescript
const guardStringLength = <
  Type extends AnyString,
  Min extends number,
  Max extends number,
  Payload extends object = object
>(
  value: Type,
  length: MinMax<Min, Max> | Min | Max,
  callback?: ResultCallback<Type, MinMax<Min, Max> & Payload>,
  payload?: Payload
): value is StringOfLength<Min, Max, Type> =>
  isStringLength(value, length, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](guardstringlength.md#value-type) via the [return type](guardstringlength.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardstringlength.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

A generic type variable `Type` constrained by generic type [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the supplied [`value`](guardstringlength.md#value-type) via the [return type](guardstringlength.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardstringlength.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.



A generic type variable `Type` guarded by `AnyString`, by default of value captured from the supplied `value` indicates the **type** of the `value` via the return type `value is StringOfLength<Min, Max, Type>`.

#### <mark style="color:green;">**`Min`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from optional `min` of the provided [`range`](guardstringlength.md#range-minmax-less-than-min-max-greater-than) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](guardstringlength.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type and the **minimum** range of the provided [`value`](guardstringlength.md#value-type) via the [return type](guardstringlength.md#return-type).

A generic type variable `Min` constrained by the `number` type, by default of value captured from optional `min` of the provided `length` that indicates the **minimum** length of the provided `value` via the return type `value is StringOfLength<Min, Max, Type>`.

#### <mark style="color:green;">**`Max`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from optional `max` of the provided [`range`](guardstringlength.md#range-minmax-less-than-min-max-greater-than) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](guardstringlength.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type and the **maximum** range of the provided [`value`](guardstringlength.md#value-type) via the [return type](guardstringlength.md#return-type).

A generic type variable `Max` constrained by the `number` type, by default of value captured from optional `max` of the provided `length` that indicates the **maximum** length of the provided `value` via the return type `value is StringOfLength<Min, Max, Type>`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardstringlength.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardstringlength.md#payload-payload) optional parameter of the [`guardObject()`](guardstringlength.md#guardobject) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](guardstringlength.md#typeextendsanystring) constrained by [`AnyString`](../types/anystring.md), by default of the type captured from itself to guard.

#### `length: MinMax<Min, Max> | Min | Max`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of optional minimum and a maximum `length` of the given [`value`](guardstringlength.md#value-type).

#### `callback?: ResultCallback<null, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardstringlength.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardstringlength.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardstringlength.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is StringOfLength<Min, Max, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the `value` is a generic type [`StringOfLength`](../types/stringoflength.md) that takes generic type variables [`Min`](guardstringlength.md#minextendsnumber) and [`Max`](guardstringlength.md#maxextendsnumber)(from the provided `length` parameter) as the **length** of the supplied [`value`](guardstringlength.md#value-type), and [`Type`](guardstringlength.md#typeextendsanystring) as the type of the supplied `value`.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the `value` is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) between the specified range.

### Example usage

```typescript
// Example usage.
import { guardStringLength } from '@angular-package/type';

guardStringLength('not my name', {min: 11}); // true; return type `value is StringOfLength<11, number, "not my name">`
guardStringLength('my name', { max: 11 }); // true; return type `value is StringOfLength<number, 11, "my name">`
guardStringLength('not my name', {min: 11, max: 11}); // true; return type `value is StringOfLength<11, 11, "not my name">`
guardStringLength('not my name', {min: 12, max: 15}); // false; return type `value is StringOfLength<12, 15, "not my name">`

// Long text for the captured value type.
const value = `Lorem Ipsum is simply dummy text of the printing and typesetting industry.
Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
when an unknown printer took a galley of type and scrambled it to make a type specimen book.
It has survived not only five centuries, but also the leap into electronic typesetting,
remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset
sheets containing Lorem Ipsum passages, and more recently with desktop publishing software
like Aldus PageMaker including versions of Lorem Ipsum.` as string;

guardStringLength(value, { max: 3 }); // false, value is StringOfLength<number, 3, string>
```
