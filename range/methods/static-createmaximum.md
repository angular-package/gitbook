---
description: Returns the `Maximum` instance of the given maximum value
---

# static createMaximum()

## `Range.createMaximum()`

The static `createMaximum()` method returns the [`Maximum`](broken-reference) instance of the given **maximum** [`value`](static-createmaximum.md#value-value).

{% code title="range.class.ts" %}
```typescript
public static createMaximum<Value extends number>(
  value: Value
): Maximum<Value> {
  return Maximum.create(value);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`<mark style="color:green;">`number`</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`value`](static-createmaximum.md#value-value) indicates the [primitive value](../../maximum/methods/valueof.md#maximum.prototype.valueof) type of a new [`Maximum`](broken-reference) instance.

### Parameters

#### `value:`[<mark style="color:green;">`Value`</mark>](static-createmaximum.md#valueextendsnumber)<mark style="color:green;">``</mark>

The **maximum** range of a generic type variable [`Value`](static-createmaximum.md#valueextendsnumber) to set with a new instance of [`Maximum`](broken-reference).

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Maximum`</mark>](broken-reference)`<`[<mark style="color:green;">`Value`</mark>](static-createmaximum.md#valueextendsnumber)`>`

The **return type** is the [`Maximum`](broken-reference) object that takes generic type variable [`Value`](static-createmaximum.md#valueextendsnumber).

### Returns

The **return value** is the [`Maximum`](broken-reference) instance with the [primitive value](../../maximum/methods/valueof.md#maximum.prototype.valueof) from the given [`value`](static-createmaximum.md#value-value).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Maximum {27} of Maximum<27>.
Range.createMaximum(27);
```
