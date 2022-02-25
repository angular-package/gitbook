---
description: >-
  Performs a callback function with the ability to decide when to move to the
  next step of the range
---

# stepByStep()

## `Range.prototype.stepByStep()`

The `stepByStep()` method performs a callback function with the ability to decide when to move to the next step of the range.

{% code title="range.class.ts" %}
```typescript
public stepByStep(
  callbackFn: (value: Generator<number>, step: Step, max: Max) => void
): this {
  const t = this;
  callbackFn(
    (function* stepByStep(current = t.min - t.step): Generator<number> {
      while (current < t.max) {
        yield (current += t.step);
      }
    })(),
    t.step,
    t.max
  );
  return this;
}
```
{% endcode %}

### Parameters

#### `callbackFn: (value:`[<mark style="color:green;">`Generator`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function\*)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`>, step:`[<mark style="color:green;">`Step`</mark>](../g-generic-type-variables.md#range-less-than-min-max-step-greater-than-2)`, max:`[<mark style="color:green;">`Max`</mark>](../g-generic-type-variables.md#range-less-than-min-max-step-greater-than-1)`) => void`

A function that accepts up to three arguments. The `value` is a function generator that allows deciding when to move to the next step, `step` is the step, and `max` is the maximum of a specified `Range` object.

**`value:`**<mark style="color:green;">**`Generator`**</mark>**`<`**[<mark style="color:green;">**`number`**</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)**`>`** - Function generator allows deciding when to move to the next range step.\
**`step:`**[<mark style="color:green;">**`Step`**</mark>](../g-generic-type-variables.md#range-less-than-min-max-step-greater-than-2) - The step of a specified [`Range`](broken-reference) object.\
**`max:`**[<mark style="color:green;">**`Max`**</mark>](../g-generic-type-variables.md#range-less-than-min-max-step-greater-than-1) - The maximum range of a specified [`Range`](broken-reference) object.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`this`</mark>](broken-reference)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [`Range`](broken-reference) instance.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27, 1.5);

range.stepByStep((value) => {
  // Returns 4
  value.next().value;
  // Returns 5.5
  value.next().value;
  // Returns 7
  value.next().value;
  // Returns 8.5
  value.next().value;
  // Returns 10
  value.next().value;
  // Returns 11.5
  value.next().value;
  // Returns 13
  value.next().value;
});
```
