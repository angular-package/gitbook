---
description: >-
  The `get` accessor obtains the range of an `Array` of the minimum to the
  maximum with the step of a specified `Range` object
---

# get range()

## `Range.prototype.range`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the range of an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of the minimum to the maximum with the step of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public get range(): Array<number> {
  const arr = [];
  let range: number = this.min - this.step;
  while (range < this.max) {
    range += this.step;
    range <= this.max && arr.push(range);
  }
  return arr;
}
```
{% endcode %}

### Type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Max`</mark>](../generic-type-variables.md#maxextendsnumber)<mark style="color:green;">``</mark>

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 4, max: 27} of Range<4, 27, 1.5>.
const range = new Range(4, 27, 1.5);

// Returns
// [4, 5.5, 7, 8.5, 10, 11.5, 13, 14.5, 16, 17.5, 19, 20.5, 22, 23.5, 25, 26.5]
// of type number[]
range.range;
```
