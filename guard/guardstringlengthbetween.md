# guardStringLengthBetween()

## `guardStringLengthBetween()`

Guards the value to be [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) or [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) instance of a length between the specified range.

{% code title="guard-string-length-between.func.ts" %}
```typescript
const guardStringLengthBetween = <
  Type extends AnyString,
  Min extends number,
  Max extends number,
  Payload extends object = object
>(
  value: Type,
  min: Min,
  max: Max,
  callback?: ResultCallback<Type, { min: Min; max: Max } & Payload>,
  payload?: Payload
): value is StringOfLength<Min, Max, Type> =>
  isStringLengthBetween(value, min, max, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>

A generic type variable `Obj` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](guardstringlengthbetween.md#value-type) via the [return type](guardstringlengthbetween.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardstringlengthbetween.md#callback-resultcallback-less-than-type-minmax-less-than-min-max-greater-than-and-payload-greater-tha) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Min`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`min`](guardstringlengthbetween.md#min-max) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](guardstringlengthbetween.md#callback-resultcallback-less-than-type-minmax-less-than-min-max-greater-than-and-payload-greater-tha) function [`ResultCallback`](../types/resultcallback.md) type and the **minimum** length of the provided [`value`](guardstringlengthbetween.md#value-type) via the [return type](guardstringlengthbetween.md#return-type).

#### <mark style="color:green;">**`Max`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`max`](guardstringlengthbetween.md#max-max) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](guardstringlengthbetween.md#callback-resultcallback-less-than-type-minmax-less-than-min-max-greater-than-and-payload-greater-tha) function [`ResultCallback`](../types/resultcallback.md) type and the **maximum** length of the provided [`value`](guardstringlengthbetween.md#value-type) via the [return type](guardstringlengthbetween.md#return-type).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardstringlengthbetween.md#callback-resultcallback-less-than-type-min-and-payload-greater-than) function and [`payload`](guardstringlengthbetween.md#payload-payload) optional parameter of the [`guardStringLengthBetween()`](guardstringlengthbetween.md#guardstringlengthbetween) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](guardstringlengthbetween.md#typeextendsanystring) constrained by [`AnyString`](../types/anystring.md), by default of the type captured from itself to guard.

#### `min: Max`

The **minimum** length of generic type variable [`Min`](guardstringlengthbetween.md#minextendsnumber) of a given [`value`](guardstringlengthbetween.md#value-type).

#### `max: Max`

The **maximum** length of generic type variable [`Max`](guardstringlengthbetween.md#maxextendsnumber) of a given [`value`](guardstringlengthbetween.md#value-type)

#### `callback?: ResultCallback<Type, { min: Min; max: Max  } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](guardstringlengthbetween.md#value-type) that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardstringlengthbetween.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The **`payload`** parameter of given `callback` function consists of the **`min`** and **`max`** properties of the given [`min`](guardstringlengthbetween.md#min-max) and [`max`](guardstringlengthbetween.md#max-max) parameters, and they can't be overwritten by the given [`payload`](guardstringlengthbetween.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardstringlengthbetween.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardstringlengthbetween.md#callback-resultcallback-less-than-type-min-min-max-max-and-payload-greater-than) function.

### Return type

#### `value is StringOfLength<Min, Max, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the [`value`](guardstringlengthbetween.md#value-type) is a generic type [`StringOfLength`](../types/stringoflength.md) that takes generic type variables [`Min`](guardstringlengthbetween.md#minextendsnumber) and [`Max`](guardstringlengthbetween.md#maxextendsnumber)(from the provided [`min`](guardstringlengthbetween.md#min-max) and [`max`](guardstringlengthbetween.md#max-max) parameter) as the **length range** of the supplied [`value`](guardstringlengthbetween.md#value-type), and [`Type`](guardstringlengthbetween.md#typeextendsanystring) as the type of the supplied [`value`](guardstringlengthbetween.md#value-type).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardstringlengthbetween.md#value-type) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of a [length](guardstringlengthbetween.md#length-minmax-less-than-min-max-greater-than-or-min-or-max) between the specified range.

## Example usage

```typescript
// Example usage.
import { guardStringLengthBetween } from '@angular-package/type';

// true; return type `value is StringOfLength<11, 12, "not my name">`
guardStringLengthBetween('not my name', 11, 12);
// true; return type `value is StringOfLength<10, 11, "not my name">`
guardStringLengthBetween('not my name', 10, 11);
// true; return type `value is StringOfLength<11, 11, "not my name">`
guardStringLengthBetween('not my name', 11, 11);
// false; return type `value is StringOfLength<12, 15, "not my name">`
guardStringLengthBetween('not my name', 12, 15);

// Long text for the captured value type.
const value = `Lorem Ipsum is simply dummy text of the printing and typesetting industry.
Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
when an unknown printer took a galley of type and scrambled it to make a type specimen book.
It has survived not only five centuries, but also the leap into electronic typesetting,
remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset
sheets containing Lorem Ipsum passages, and more recently with desktop publishing software
like Aldus PageMaker including versions of Lorem Ipsum.` as string;

// false, value is StringOfLength<0, 3, string>
guardStringLengthBetween(value, 0, 3); 
```
