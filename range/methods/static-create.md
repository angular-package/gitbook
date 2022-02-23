---
description: >-
  Returns a new instance of `Range` with a range of the given required `min`,
  `max` and optional `step`
---

# static create()

## `Range.create()`

The static `create()` method returns a new instance of [`Range`](broken-reference) with a range of the given required [`min`](static-create.md#min-min), [`max`](static-create.md#max-max) and optional [`step`](static-create.md#step-step).

{% code title="range.class.ts" %}
```typescript
public static create<
  Min extends number,
  Max extends number,
  Step extends number = 1
>(min: Min, max: Max, step?: Step): Range<Min, Max, Step> {
  return new this(min, max, step);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Min`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`min`](static-create.md#min-min) indicates the **minimum** range type of a new [`Range`](broken-reference) instance.

#### <mark style="color:green;">`Max`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`max`](static-create.md#max-max) indicates the **maximum** range type of a new [`Range`](broken-reference) instance.

#### <mark style="color:green;">`Step`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`= 1`

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value equal to **`1`**, optionally **captured** from the supplied [`step`](static-create.md#step-step) indicates the range step type of a new [`Range`](broken-reference) instance.

### Parameters

#### `min:`[<mark style="color:green;">`Min`</mark>](static-create.md#minextendsnumber)<mark style="color:green;">``</mark>

The **minimum** range of generic type variable [`Min`](static-create.md#minextendsnumber) to set with a new [`Range`](broken-reference) instance.

#### `max:`[<mark style="color:green;">`Max`</mark>](static-create.md#maxextendsnumber)<mark style="color:green;">``</mark>

The **maximum** range of generic type variable [`Max`](static-create.md#maxextendsnumber) to set with a new [`Range`](broken-reference) instance.

#### `step:`<mark style="color:green;">`Step`</mark>

Optional step of generic type variable [`Step`](static-create.md#stepextendsnumber-1) to set with a new [`Range`](broken-reference) instance, by default **`1`**.

### Return type

#### `Range<`[<mark style="color:green;">`Min`</mark>](static-create.md#minextendsnumber)`,`[<mark style="color:green;">`Max`</mark>](static-create.md#maxextendsnumber)`,`[<mark style="color:green;">`Step`</mark>](static-create.md#stepextendsnumber-1)`>`

The **return type** is the [`Range`](broken-reference) object that takes generic type variable [`Min`](static-create.md#minextendsnumber), [`Max`](static-create.md#maxextendsnumber) and [`Step`](static-create.md#stepextendsnumber-1).

### Returns

The **return value** is the [`Range`](broken-reference) instance with a range of the given required [`min`](static-create.md#min-min), [`max`](static-create.md#max-max) and optional [`step`](static-create.md#step-step).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Range {min: 4, max: 27} of Range<4, 27, 1>
Range.create(4, 27);

// Returns Range {min: 4, max: 27} of Range<4, 27, 1.5>
Range.create(4, 27, 1.5);
```
