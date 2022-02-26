---
description: Returns the range value of the given step
---

# getValueOfStep()

## `Range.prototype.getValueOfStep()`

The `getValueOfStep()` method returns the range value of the given [`step`](getvalueofstep.md#step-number).

{% code title="range.class.ts" %}
```typescript
public getValueOfStep(step: number): number | undefined {
  return step > 0 && step <= this.steps ? this.range[step - 1] : undefined;
}
```
{% endcode %}

### Parameters

#### `step:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

Step parameter of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to retrieve the range value.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

### Returns

The **return value** is the range value of the given [`step`](getvalueofstep.md#step-number) if exists otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';

// Create new instance.
// Returns Range {min: -27, max: 27, value: 10} of Range<-27, 27, 3>.
const range = new Range(-27, 27, 10, 3);

// Maximum steps is 19.
range.steps;

// Get value of step 3. Returns -21.
range.getValueOfStep(3);

// Get range to step 20. Returns undefined.
range.getValueOfStep(20);

// Get range to step 1. Returns -27.
range.getValueOfStep(1);
```
