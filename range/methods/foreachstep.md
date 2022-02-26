---
description: Performs the specified action for each step in the maximum range of an `Array`
---

# forEachStep()

## `Range.prototype.forEachStep()`

The `forEachStep()` method performs the specified action for each step in the [maximum](../properties/max.md#range.prototype.max) range of an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).

{% code title="range.class.ts" %}
```typescript
public forEachStep(
  forEachStep: (value: number, step: number, range: readonly number[]) => void
): this {
  this.range.forEach(forEachStep);
  return this;
}
```
{% endcode %}

### Parameters

#### `forEachStep: (value:`<mark style="color:green;">`number`</mark>`, step:`<mark style="color:green;">`number`</mark>`, range: readonly`<mark style="color:green;">`number`</mark>`[]) => void`&#x20;

A function that accepts up to three arguments. It's called one time for each step in the range.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`this`</mark>](broken-reference)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [`Range`](broken-reference) instance.

## Example usage

### Maximum range

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 9} of Range<3, 9, 3>.
const range = new Range(3, 9, undefined, 3);

range.forEachStep((value, step, r) => {
  // 4 - 5.5 - 7 - 8.5 - 10
  value;
  // 0 - 1 - 2 - 3 - 4
  step;
  // (5) [4, 5.5, 7, 8.5, 10]
  r;
});
```