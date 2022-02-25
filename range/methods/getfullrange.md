---
description: >-
  Returns a range of numbers from minimum to maximum with the step of a
  specified `Range` object
---

# getFullRange()

## `Range.prototype.getFullRange()`

The `getRange()` method returns a range of numbers from [minimum](../properties/min.md#range.prototype.min) to [maximum](../properties/max.md) with the [step](../accessors/get-step.md#range.prototype.step) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public getFullRange(): Readonly<Array<number>> {
  return this.getRange(this.max);
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Readonly`</mark>](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)`<`[<mark style="color:green;">`Array`</mark>](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`>>`

### Returns

The **return value** is a range of numbers from [minimum](../properties/min.md#range.prototype.min) to [maximum](../properties/max.md#range.prototype.max) with the [step](../accessors/get-step.md#range.prototype.step) of a read-only [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Returns (9) [3, 6, 9, 12, 15, 18, 21, 24, 27]
range.getFullRange();
```
