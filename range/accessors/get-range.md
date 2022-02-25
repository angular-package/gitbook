---
description: >-
  The `get` accessor obtains the range of an `Array` of the minimum to the range
  current value or maximum with the step of a specified `Range` object
---

# get range()

## `Range.prototype.range`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the range of an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of the [minimum](../properties/min.md#range.prototype.min) to the range [current value](../properties/value.md#range.prototype.value) or [maximum](../properties/max.md#range.prototype.max) with the [step](get-step.md#range.prototype.step) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public get range(): Readonly<Array<number>> {
  return this.getRange();
}
```
{% endcode %}

### Type

#### [<mark style="color:green;">`Readonly`</mark>](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)`<`[<mark style="color:green;">`Array`</mark>](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`>>`

### Returns

The **return value** is the range from [minimum](../properties/min.md#range.prototype.min) to the range [current value](../properties/value.md#range.prototype.value) or [maximum](../properties/max.md#range.prototype.max) of a read-only [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 4, max: 27, value: 10} of Range<4, 27, 1.5>.
const range = new Range(4, 27, 10, 1.5);

// Returns
// (5) [4, 5.5, 7, 8.5, 10] of type readonly number[]
range.range;
```
