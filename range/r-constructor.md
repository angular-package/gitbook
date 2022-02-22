---
description: Creates the `Range` instance with a range of the given `min` and `max`
---

# r: ★ Constructor

## `Range()`

Creates the [`Range`](broken-reference) instance with a range of the given [`min`](r-constructor.md#min-min) and [`max`](r-constructor.md#max-max).

{% code title="range.class.ts" %}
```typescript
constructor(min: Min, max: Max) {
  this.#maximum = new Maximum(max);
  this.#minimum = new Minimum(min);
  // Define the `min` and `max` property.
  Object.defineProperties(this, {
    min: {
      value: min,
      enumerable: true,
      writable: false,
    },
    max: {
      value: max,
      enumerable: true,
      writable: false,
    },
  });
}
```
{% endcode %}

### Parameters

#### `min:`[<mark style="color:green;">`Min`</mark>](r-generic-type-variables.md#range-less-than-min-max-step-greater-than)<mark style="color:green;">``</mark>

The **minimum** range of generic type variable [`Min`](r-generic-type-variables.md#minextendsnumber) to set with a new [`Range`](broken-reference) instance.

#### `max:`[<mark style="color:green;">`Max`</mark>](r-generic-type-variables.md#range-less-than-min-max-step-greater-than-1)<mark style="color:green;">``</mark>

The **maximum** range of generic type variable [`Max`](r-generic-type-variables.md#range-less-than-min-max-greater-than-1) to set with a new [`Range`](broken-reference) instance.

#### `step:`[<mark style="color:green;">`Step`</mark>](r-generic-type-variables.md#range-less-than-min-max-step-greater-than-2)<mark style="color:green;">``</mark>

Optional step of generic type variable [`Step`](r-generic-type-variables.md#stepextendsnumber-1) to set with a new [`Range`](broken-reference) instance, by default **`1`**.

{% hint style="info" %}
The step is used by the [`range`](accessors/get-range.md) accessor and [`stepByStep()`](methods/stepbystep.md) method to return the entire range.&#x20;
{% endhint %}

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Range { min: 4, max: 27 } of Range<4, 27>
new Range(4, 27);
```
