---
description: >-
  Checks whether the value of any type is the Maximum instance of any or the
  given primitive value
---

# static isMaximum()

## `Maximum.isMaximum()`

Checks whether the value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type is the [`Maximum`](broken-reference) instance of any or the given primitive [value](static-ismaximum.md#max-value).

{% code title="maximum.class.ts" %}
```typescript
public static isMaximum<Value extends number>(
  value: any,
  max?: Value
): value is Maximum<Value> {
  return (
    typeof value === 'object' &&
    value instanceof this &&
    (typeof max === 'number' ? value.valueOf() === max : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`max`](static-ismaximum.md#max-value) via the [return type](static-ismaximum.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Maximum`](broken-reference) instance.

#### `max?:`[<mark style="color:green;">`Value`</mark>](static-ismaximum.md#valueextendsnumber)<mark style="color:green;">``</mark>

Optional maximum of the generic type variable [`Value`](static-ismaximum.md#valueextendsnumber) to check if it's the primitive value of the given [`value`](static-ismaximum.md#value-any).

### Return type

#### `value is Maximum<`[<mark style="color:green;">`Value`</mark>](static-ismaximum.md#valueextendsnumber)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-ismaximum.md#value-any) is the [`Maximum`](broken-reference) object that takes the generic type variable [`Value`](static-ismaximum.md#valueextendsnumber).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided value is an instance of [`Maximum`](broken-reference).

### Example usage

```typescript
// Example usage.
import { Maximum } from '@angular-package/range';


```
