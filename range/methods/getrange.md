---
description: >-
  Returns range of numbers from minimum to the given `value` with the step of a
  specified `Range` object
---

# getRange()

## `Range.prototype.getRange()`

The `getRange()` method returns range of numbers from [minimum](../properties/min.md#range.prototype.min) to the given [`value`](getrange.md#value-this.value-or-or-this.max) with the [`step`](../accessors/get-step.md#range.prototype.step) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public getRange(value = this.max): Readonly<Array<number>> {
  const range = [];
  let current: number = this.min - this.step;
  while (current < value) {
    current += this.step;
    current <= this.max && range.push(current);
  }
  return range;
}
```
{% endcode %}

### Parameters

#### `value:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`= this.max`

Optional maximum range value of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type of returned [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) by default the [`value`](getrange.md#value-this.value-or-or-this.max) is the [maximum](../properties/max.md#range.prototype.max) range.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Readonly`</mark>](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)`<`[<mark style="color:green;">`Array`</mark>](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`>>`

### Returns

The **return value** is a range of numbers from [minimum](../properties/min.md#range.prototype.min) to the given [`value`](getrange.md#value-this.value-or-or-this.max) of a read-only [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Returns (9) [3, 6, 9, 12, 15, 18, 21, 24, 27] of readonly number[]
range.getRange();

// Returns (3) [3, 6, 9] of readonly number[]
range.getRange(10);
```
