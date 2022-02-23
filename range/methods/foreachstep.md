---
description: Performs the specified action for each step in the range of an array
---

# forEachStep()

## `Range.prototype.forEachStep()`

The `forEachStep()` method performs the specified action for each step in the range of an array.

{% code title="range.class.ts" %}
```typescript
public forEachStep(
  forEachStep: (value: number, index: number, range: number[]) => void
): this {
  this.range.forEach(forEachStep);
  return this;
}
```
{% endcode %}

### Parameters

#### `forEachStep: (value:`<mark style="color:green;">`number`</mark>`, index:`<mark style="color:green;">`number`</mark>`, range:`<mark style="color:green;">`number`</mark>`[]) => void`&#x20;

A function that accepts up to three arguments. It's called one time for each step in the range.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`this`</mark>](broken-reference)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [`Range`](broken-reference) instance.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);


```
