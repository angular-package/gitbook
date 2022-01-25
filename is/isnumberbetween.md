# isNumberBetween()

## `isNumberBetween()`

Checks if any value is a `number` type or an instance of `Number` by using `isNumber()` between a specified range.

Use `isNumberBetween()` or `is.numberBetween()` to check if **any** value is a \[`number`]\[js-number] type or an instance of \[`Number`]\[js-number] between a specified range.

{% code title="is-number-between.func.ts" %}
```typescript
const isNumberBetween = <
  Type extends AnyNumber = number,
  Min extends number = number,
  Max extends number = number,
  Payload extends object = object
>(
  value: any,
  range: MinMax<Min, Max> | Min | Max,
  callback: ResultCallback<
    any,
    MinMax<Min, Max> & Payload
  > = resultCallback,
  payload?: Payload
): value is NumberBetween<Min, Max, Type> =>
  callback(
    isNumber(value)
    ? isObject(range)
      ? (isNumberType(range.min) && range.min >= 0
          ? value.valueOf() >= range.min
          : true) &&
          (isNumberType(range.max) && range.max >= 0
            ? value.valueOf() <= range.max
            : true)
        : isNumberType(length) && value.valueOf() === range
    : false,
    value,
    {
      ...payload,
      ...(isNumberType(range) ? { range } : range),
    } as any
  );
```
{% endcode %}

### Generic type variables

`Type`

A generic type variable `Type` guarded by `AnyNumber` by default of `number` indicates the type of the `value` via the return type `value is NumberBetween<Min, Max, Type>`.

`Min`

A generic type variable `Min` constrained by the `number` type, by default of value captured from optional `min` of the provided `range` that indicates the **minimum** range of the provided `value` via the return type `value is NumberBetween<Min, Max, Type>`.

`Max`

A generic type variable `Max` constrained by the `number` type, by default of value captured from optional `max` of the provided `range` that indicates the **maximum** range of the provided `value` via the return type `value is NumberBetween<Min, Max, Type>`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnumberbetween.md#payload-payload) optional parameter of the [`isNumberBetween()`](isnumberbetween.md#isnumberbetween) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `range: MinMax<Min, Max>`

An \[`object`]\[js-object] of optional **minimum** and **maximum** range of a given `value`.



#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnumberbetween.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is NumberBetween<Min, Max, Type>`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type `NumberBetween` that takes generic type variables `Min` and `Max` as a **range** of the supplied value and `Type` as the type of the supplied value.

### Returns

The **return value** is a `boolean` indicating whether the `value` is a finite number of a `number` type or an instance of \[`Number`]\[js-number] between a specified range.

### Example usage

```typescript
// Example usage.
import { isNumberBetween } from '@angular-package/type';

const age = 13;

isNumberBetween(age, 0, 13); // true; The return type `value is NumberBetween<0, 13>`
isNumberBetween(age, 14, 28); // false; The return type `value is NumberBetween<14, 28>`
isNumberBetween(age, 0, 12); // false; The return type `value is NumberBetween<0, 12>`
isNumberBetween(age, 13, 13); // true; The return type `value is NumberBetween<13, 13>`

const ageBox = new Number(age);

isNumberBetween(ageBox, 0, 13); // true; The return type `value is NumberBetween<0, 13>`
isNumberBetween(ageBox, 14, 28); // false; The return type `value is NumberBetween<14, 28>`
isNumberBetween(ageBox, 0, 12); // false; The return type `value is NumberBetween<0, 12>`
isNumberBetween(ageBox, 13, 13); // true; The return type `value is NumberBetween<13, 13>`
```
