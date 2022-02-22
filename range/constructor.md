---
description: >-
  Creates the `Range` instance with a range of the given required `min`, `max`
  and optional `step`
---

# r: ★ Constructor

## `Range()`

Creates the [`Range`](broken-reference) instance with a range of the given required [`min`](constructor.md#min-min), [`max`](constructor.md#max-max) and optional [`step`](constructor.md#step-step).

{% code title="range.class.ts" %}
```typescript
constructor(min: Min, max: Max, step: Step = 1 as Step) {
  this.#maximum = new Maximum(max);
  this.#minimum = new Minimum(min);
  this.#step = step;
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

#### `min:`[<mark style="color:green;">`Min`</mark>](generic-type-variables.md#range-less-than-min-max-step-greater-than)<mark style="color:green;">``</mark>

The **minimum** range of generic type variable [`Min`](generic-type-variables.md#minextendsnumber) to set with a new [`Range`](broken-reference) instance.

#### `max:`[<mark style="color:green;">`Max`</mark>](generic-type-variables.md#range-less-than-min-max-step-greater-than-1)<mark style="color:green;">``</mark>

The **maximum** range of generic type variable [`Max`](generic-type-variables.md#range-less-than-min-max-greater-than-1) to set with a new [`Range`](broken-reference) instance.

#### `step:`[<mark style="color:green;">`Step`</mark>](generic-type-variables.md#range-less-than-min-max-step-greater-than-2)<mark style="color:green;">``</mark>

Optional step of generic type variable [`Step`](generic-type-variables.md#stepextendsnumber-1) to set with a new [`Range`](broken-reference) instance, by default **`1`**.

{% hint style="info" %}
The step is used by the [`range`](accessors/get-range.md) accessor and [`stepByStep()`](methods/stepbystep.md) method to return the entire range.&#x20;
{% endhint %}

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Range { min: 4, max: 27 } of Range<4, 27, 1>
new Range(4, 27);

// Returns Range { min: 4, max: 27 } of Range<4, 27, 1.5>
new Range(4, 27, 1.5);
```
