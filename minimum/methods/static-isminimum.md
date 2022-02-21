---
description: >-
  Checks whether the value of any type is the Maximum instance of any or the
  given primitive value
---

# static isMinimum()

## `Minimum.isMinimum()`

The static `isMinimum()` method checks the provided [`value`](static-isminimum.md#value-any) of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type whether is an instance of [`Minimum`](broken-reference) of any or the given [`min`](static-isminimum.md#min-value).

{% code title="minimum.class.ts" %}
```typescript
public static isMinimum<Value extends number>(
  value: any,
  min?: Value
): value is Minimum<Value> {
  return (
    typeof value === 'object' &&
    value instanceof this &&
    (typeof min === 'number' ? value.valueOf() : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`min`](static-isminimum.md#max-value) via the [return type](static-isminimum.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Minimum`](broken-reference) instance.

#### `min?:`[<mark style="color:green;">`Value`</mark>](static-isminimum.md#valueextendsnumber)<mark style="color:green;">``</mark>

Optional minimum of the generic type variable [`Value`](static-isminimum.md#valueextendsnumber) to check if it's the [primitive value](valueof.md#minimum.prototype.valueof) of the given [`value`](static-isminimum.md#value-any).

### Return type

#### `value is Minimum<`[<mark style="color:green;">`Value`</mark>](static-isminimum.md#valueextendsnumber)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-isminimum.md#value-any) is the [`Minimum`](broken-reference) object that takes the generic type variable [`Value`](static-isminimum.md#valueextendsnumber).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](static-isminimum.md#value-any) is an instance of [`Minimum`](broken-reference) of any or the given [`min`](static-isminimum.md#min-value).

### Example usage

```typescript
// Example usage.
import { Minimum } from '@angular-package/range';


```
