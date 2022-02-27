---
description: Returns the step of the range value
---

# getCurrentStep()

## `Range.prototype.getCurrentStep()`

The `getCurrentStep()` method returns the step of the range [value](../accessors/value.md).

{% code title="range.class.ts" %}
```typescript
public getCurrentStep(): number | undefined {
  return typeof this.value === 'number'
    ? Math.floor(this.value / this.#step)
    : undefined;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

### Returns

The **return value** is the step of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type, if range [value](../accessors/value.md) is set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Returns 3 of number | undefined.
range.getCurrentStep();
```
