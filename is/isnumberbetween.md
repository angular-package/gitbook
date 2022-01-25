# isNumberBetween()

### `isNumberBetween()`

Checks if any value is a `number` type or an instance of `Number` by using `isNumber()` between a specified range.

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

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnumberbetween.md#payload-payload) optional parameter of the [`isNumberBetween()`](isnumberbetween.md#isnumberbetween) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnumberbetween.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isNumberBetween } from '@angular-package/type';

```

