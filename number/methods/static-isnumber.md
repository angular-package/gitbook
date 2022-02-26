---
description: >-
  Checks the provided value of any type whether is an instance of `Number` of
  any or the given primitive value
---

# static isNumber()

## `Number.isNumber()`

The static `isNumber()` method checks the provided [`value`](static-isnumber.md#value-any) of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type whether is an instance of [`Number`](broken-reference) of any or the given primitive [value](static-isnumber.md#numbervalue-value).

{% code title="number.class.ts" %}
```typescript
public static isNumber<Value extends number>(
  value: any,
  numberValue?: Value
): value is Number<Value> {
  return (
    typeof value === 'object' &&
    value instanceof this &&
    (typeof numberValue === 'number' ? value.valueOf() === numberValue : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`numberValue`](static-isnumber.md#numbervalue-value) via the [return type](static-isnumber.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Number`](broken-reference) instance.

#### `numberValue?:`[<mark style="color:green;">`Value`</mark>](static-isnumber.md#valueextendsnumber)<mark style="color:green;">``</mark>

Optional number of the generic type variable [`Value`](static-isnumber.md#valueextendsnumber) to check if it's the [primitive value](valueof.md#number.prototype.valueof) of the given [`value`](static-isnumber.md#value-any).

### Return type

#### `value is Number<`[<mark style="color:green;">`Value`</mark>](static-isnumber.md#valueextendsnumber)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-isnumber.md#value-any) is the [`Number`](broken-reference) object that takes the generic type variable [`Value`](static-isnumber.md#valueextendsnumber).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](static-isnumber.md#value-any) is an instance of [`Number`](broken-reference) of any or the given [<mark style="background-color:purple;">`numberValue`</mark>](static-isnumber.md#min-value).

## Example usage

```typescript
// Example usage.
import { Number } from '@angular-package/range';


```
