---
description: >-
  Returns a range of numbers by the specified step from the minimum to the given
  `step` of a specified `Range` object
---

# getRangeOfStep()

## `Range.prototype.getRangeOfStep()`

The `getRangeOfStep()` method returns a range of numbers by the specified [`step`](../accessors/get-step.md) from the [minimum](../properties/min.md) to the given [`step`](getrangeofstep.md#step-number) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public getRangeOfStep(step: number): Readonly<Array<number>> {
  const range = [];
  if (step > 0 && step <= this.steps) {
    for (let value = 0; value < step; value++) {
      range.push(this.min + value * this.#step);
    }
  }
  return range;
}
```
{% endcode %}

### Parameters

#### `step:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

Step of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type is the maximum range of the returned [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).&#x20;

{% hint style="warning" %}
The value must be less or equal to the number of range [`steps`](../accessors/get-steps.md).
{% endhint %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Readonly`</mark>](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)`<`[<mark style="color:green;">`Array`</mark>](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`>>`

### Returns

The **return value** is a range of numbers of a read-only [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) from [minimum](../properties/min.md) to step of the given [`step`](getrangeofstep.md#step-number) if the given [`step`](getrangeofstep.md#step-number) is within a range, otherwise an empty [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';
// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Maximum steps is 9.
range.steps;

// Get range to step 3. Returns (3) [3, 6, 9]
range.getRangeToStep(3);

// Get range to step 9. Returns (9) [3, 6, 9, 12, 15, 18, 21, 24, 27]
range.getRangeToStep(9);
```
