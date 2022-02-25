---
description: >-
  Creates the `Range` instance with a range of the given required `min`, `max`
  and optional current `value`, `step`
---

# ★ Constructor

## `Range()`

Creates the [`Range`](broken-reference) instance with a range of the given required [`min`](constructor.md#min-min), [`max`](constructor.md#max-max) and optional current [`value`](constructor.md#public-value-number), [`step`](constructor.md#step-step).

{% code title="range.class.ts" %}
```typescript
constructor(min: Min, max: Max, value?: number, step: Step = 1 as Step) {
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
  // Sets the range value between the given `min` and `max`.
  typeof value === 'number' && this.setValue(value);
}
```
{% endcode %}

### Parameters

#### `min:`[<mark style="color:green;">`Min`</mark>](g-generic-type-variables.md#range-less-than-min-max-step-greater-than)<mark style="color:green;">``</mark>

The **minimum** range of generic type variable [`Min`](g-generic-type-variables.md#range-less-than-min-max-step-greater-than) to set with a new [`Range`](broken-reference) instance.

#### `max:`[<mark style="color:green;">`Max`</mark>](g-generic-type-variables.md#range-less-than-min-max-step-greater-than-1)<mark style="color:green;">``</mark>

The **maximum** range of generic type variable [`Max`](g-generic-type-variables.md#range-less-than-min-max-step-greater-than-1) to set with a new [`Range`](broken-reference) instance.

#### `value?:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;">``</mark>

The optional value of the [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type between the given [`min`](constructor.md#min-min) and [`max`](constructor.md#max-max) specifies the default value of a new [`Range`](broken-reference) instance.

#### `step:`[<mark style="color:green;">`Step`</mark>](g-generic-type-variables.md#range-less-than-min-max-step-greater-than-2)=`1 as`[<mark style="color:green;">`Step`</mark>](g-generic-type-variables.md#range-less-than-min-max-step-greater-than-2)<mark style="color:green;">``</mark>

Optional step of generic type variable [`Step`](g-generic-type-variables.md#stepextendsnumber-1) to set with a new [`Range`](broken-reference) instance, by default **`1`**.

{% hint style="info" %}
The step is used by the [`range`](accessors/get-range.md) accessor and [`stepByStep()`](methods/stepbystep.md) method to return the entire range.&#x20;
{% endhint %}

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Range {min: 4, max: 27} of Range<4, 27, 1>
new Range(4, 27);

// Returns Range {min: 4, max: 27, value: 27} of Range<4, 27, 1>
new Range(4, 27, 27);

// Returns Range {min: 4, max: 27, value: 5} of Range<4, 27, 1.5>
new Range(4, 27, 5, 1.5);
```
