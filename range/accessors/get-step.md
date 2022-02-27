---
description: The `get` accessor obtains the step of a specified `Range` object
---

# get step()

## `Range.prototype.step`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the step of a specified [`Range`](broken-reference) object. It's used to return the entire range, calculate the range value of the current step, and change the range value.

{% code title="range.class.ts" %}
```typescript
public get step(): Step {
  return this.#step;
}
```
{% endcode %}

### Type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Step`</mark>](../r-generic-type-variables.md#range-less-than-min-max-step-greater-than-2)<mark style="color:green;">``</mark>

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 4, max: 27, value: 4} of Range<4, 27, 1.5>.
const range = new Range(4, 27, 4, 1.5);

// Returns 1.5 of type 1.5
range.step;
```
