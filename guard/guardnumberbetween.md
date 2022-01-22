# guardNumberBetween()

### `guardNumberBetween()`

Guards the value to be [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) between the specified range.

{% code title="guard-number-between.func.ts" %}
```typescript
const guardNumberBetween = <
  Type extends AnyNumber,
  Min extends number,
  Max extends number,
  Payload extends object = object
>(
  value: Type,
  range: MinMax<Min, Max> | Min | Max,
  callback?: ResultCallback<Type, MinMax<Min, Max> & Payload>,
  payload?: Payload
): value is NumberBetween<Min, Max, Type> =>
  isNumberBetween(value, range, callback, payload);
```
{% endcode %}

Code on [**GitHub**](https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-number-between.func.ts).

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyNumber`**</mark>

A generic type variable `Type` constrained by generic type [`AnyNumber`](../types/anynumber.md) indicates captured [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type of the supplied [`value`](guardnumberbetween.md#value-type) via the [return type](guardnumberbetween.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardnumberbetween.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Min`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from optional `min` of the provided [`range`](guardnumberbetween.md#range-minmax-less-than-min-max-greater-than) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](guardnumberbetween.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type and the **minimum** range of the provided [`value`](guardnumberbetween.md#value-type) via the [return type](guardnumberbetween.md#return-type).

#### <mark style="color:green;">**`Max`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from optional `max` of the provided [`range`](guardnumberbetween.md#range-minmax-less-than-min-max-greater-than) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](guardnumberbetween.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type and the **maximum** range of the provided [`value`](guardnumberbetween.md#value-type) via the [return type](guardnumberbetween.md#return-type).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardnumberbetween.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardnumberbetween.md#payload-payload) optional parameter of the [`guardNumberBetween()`](guardnumberbetween.md#guardnumberbetween) function from which it captures its value.

### Parameters

#### `value: Type`

The value of generic type variable [`Type`](guardnumberbetween.md#typeextendsanynumber) to guard.

#### `range: MinMax<Min, Max>`

Optional minimum or maximum range of generic type [`MinMax`](../interfaces/minmax.md) of the given [`value`](guardnumberbetween.md#value-type).

#### `callback?: ResultCallback<Type, MinMax<Min, Max> & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardnumberbetween.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardnumberbetween.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardnumberbetween.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is NumberBetween<Min, Max, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardnumberbetween.md#value-type) is a generic type [`NumberBetween`](../types/numberbetween.md) that takes generic type variables [`Min`](guardnumberbetween.md#minextendsnumber) and [`Max`](guardnumberbetween.md#maxextendsnumber) as a **range** of the supplied [`value`](guardnumberbetween.md#value-type) and [`Type`](guardnumberbetween.md#typeextendsanynumber) as the **type** of the supplied [`value`](guardnumberbetween.md#value-type).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardnumberbetween.md#value-type) is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) between the specified range.

### Example usage

```typescript
// Example usage.
import { guardNumberBetween } from '@angular-package/type';

guardNumberBetween(Infinity, {min: 0}); // false, value is number
guardNumberBetween(NaN, {min: 0}); // false, value is number
guardNumberBetween(new Number(Infinity), {min: 0}); // false, value is Number
guardNumberBetween(new Number(NaN), {min: 0}); // false, value is Number

// Minimum.
guardNumberBetween(3, {min: 3 }); // true, value is number
guardNumberBetween(new Number(3), {min: 2 }); // true, value is Number
guardNumberBetween(3, {min: 4 }); // false, value is number

// Maximum.
guardNumberBetween(3, {max: 3 }); // true, value is number
guardNumberBetween(3, {max: 2 }); // false, value is number

// Minimum and Maximum.
guardNumberBetween(3, {min: 1, max: 3 }); // true, value is number
guardNumberBetween(3, {min: 4, max: 2 }); // false, value is number
```
