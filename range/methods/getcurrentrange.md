---
description: >-
  Returns a range of numbers from minimum to the current value by the step of a
  specified `Range` object
---

# getCurrentRange()

## `Range.prototype.getCurrentRange()`

The `getCurrentRange()` method returns a range of numbers from [minimum](../properties/min.md#range.prototype.min) to the current [`value`](../accessors/value.md#range.prototype.value) by the [`step`](../accessors/get-step.md#range.prototype.step) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public getCurrentRange(): Readonly<Array<number>> | undefined {
  return typeof this.value === 'number'
    ? this.getRange(this.value)
    : undefined;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Readonly`</mark>](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)`<`[<mark style="color:green;">`Array`</mark>](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`>> |`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

### Returns

The **return value** is a range of numbers of a read-only [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) from [minimum](../properties/min.md#range.prototype.min) to the current [`value`](../accessors/value.md#range.prototype.value), if the current [`value`](../accessors/value.md#range.prototype.value) is set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Get entire range.
// Returns (9) [3, 6, 9, 12, 15, 18, 21, 24, 27]
range.range;

// Returns (3) [3, 6, 9]
range.getCurrentRange();
```
