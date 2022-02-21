---
description: Returns a new instance of `Range` with a range of the given `min` and `max`
---

# static create()

## `Range.create()`

The static `create()` method returns a new instance of [`Range`](broken-reference) with a range of the given [`min`](static-create.md#min-min) and [`max`](static-create.md#max-max).

{% code title="range.class.ts" %}
```typescript
public static create<Min extends number, Max extends number>(
  min: Min,
  max: Max
): Range<Min, Max> {
  return new this(min, max);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Min`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`min`](static-create.md#min-min) indicates the **minimum** range type of a new [`Range`](broken-reference) instance.

#### <mark style="color:green;">`Max`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`max`](static-create.md#max-max) indicates the **maximum** range type of a new [`Range`](broken-reference) instance.

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Range`](broken-reference) instance.

#### `min:`[<mark style="color:green;">`Min`</mark>](static-create.md#minextendsnumber)<mark style="color:green;">``</mark>

The **minimum** range of generic type variable [`Min`](static-create.md#minextendsnumber) to set with a new [`Range`](broken-reference) instance.

#### `max:`[<mark style="color:green;">`Max`</mark>](static-create.md#maxextendsnumber)<mark style="color:green;">``</mark>

The **maximum** range of generic type variable [`Max`](static-create.md#maxextendsnumber) to set with a new [`Range`](broken-reference) instance.

### Return type

#### `Range<`[<mark style="color:green;">`Min`</mark>](static-create.md#minextendsnumber)`,`[<mark style="color:green;">`Max`</mark>](static-create.md#maxextendsnumber)`>`

The **return type** is the [`Range`](broken-reference) object that takes generic type variable [`Min`](static-create.md#minextendsnumber) and [`Max`](static-create.md#maxextendsnumber).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](static-create.md#value-any) is an instance of [`Range`](broken-reference) of any or the given [**minimum**](static-create.md#min-min) and [**maximum**](static-create.md#max-max) range.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Range {min: 4, max: 27}
Range.create(4, 27);
```
