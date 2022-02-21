---
description: Returns the `Minimum` instance of the given minimum value
---

# static createMinimum()

## `Range.createMinimum()`

The static `createMinimum()` method returns the [`Minimum`](broken-reference) instance of the given **minimum** [`value`](static-createminimum.md#value-value).

{% code title="range.class.ts" %}
```typescript
public static createMinimum<Value extends number>(
  value: Value
): Minimum<Value> {
  return Minimum.create(value);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`<mark style="color:green;">`number`</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`value`](static-createminimum.md#value-value) indicates the [primitive value](../../minimum/methods/valueof.md#minimum.prototype.valueof) type of a new [`Minimum`](broken-reference) instance.

### Parameters

#### `value:`[<mark style="color:green;">`Value`</mark>](static-createminimum.md#valueextendsnumber)<mark style="color:green;">``</mark>

The **minimum** range of a generic type variable [`Value`](static-createminimum.md#valueextendsnumber) to set with a new instance of [`Minimum`](broken-reference).

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Minimum`</mark>](broken-reference)`<`[<mark style="color:green;">`Value`</mark>](static-createminimum.md#valueextendsnumber)`>`

The **return type** is the [`Minimum`](broken-reference) object that takes generic type variable [`Value`](static-createminimum.md#valueextendsnumber).

### Returns

The **return value** is the [`Minimum`](broken-reference) instance with the [primitive value](../../minimum/methods/valueof.md#minimum.prototype.valueof) from the given [`value`](static-createminimum.md#value-value).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Minimum {4} of Minimum<4>.
Range.createMinimum(4);
```
