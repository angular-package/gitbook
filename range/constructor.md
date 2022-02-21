---
description: Creates the `Range` instance with a range of the given `min` and `max`
---

# ★ Constructor

## `Range()`

Creates the [`Range`](broken-reference) instance with a range of the given [`min`](constructor.md#min-min) and [`max`](constructor.md#max-max).

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

#### `min:`[<mark style="color:green;">`Min`</mark>](generic-type-variables.md#minextendsnumber)<mark style="color:green;">``</mark>

The **minimum** range of generic type variable [`Min`](generic-type-variables.md#minextendsnumber) to set with a new [`Range`](broken-reference) instance.

#### `max:`[<mark style="color:green;">`Max`</mark>](generic-type-variables.md#maxextendsnumber)<mark style="color:green;">``</mark>

The **maximum** range of generic type variable [`Max`](generic-type-variables.md#range-less-than-min-max-greater-than-1) to set with a new [`Range`](broken-reference) instance.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Range { min: 4, max: 27 } of Range<4, 27>
new Range(4, 27);
```
