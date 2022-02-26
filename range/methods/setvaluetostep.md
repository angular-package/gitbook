---
description: >-
  Sets the value of the specified `Range` object to the value of the given
  `step`
---

# setValueToStep()

## `Range.prototype.setValueToStep()`

The method `setValueToStep()` sets the [value](../properties/value.md#range.prototype.value) of the specified [`Range`](broken-reference) object to the value of the given [`step`](setvaluetostep.md#value-number).

{% code title="range.class.ts" %}
```typescript
public setValueToStep(step: number): this {
  step > 0 &&
    Object.defineProperty(this, 'value', {
      configurable: true,
      value: this.getValueOfStep(step),
      writable: false,
    });
  return this;
}
```
{% endcode %}

### Parameters

#### `step:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

Step of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to retrieve the value from the range and set it as the range current value.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`this`</mark>](broken-reference)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [`Range`](broken-reference) instance.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Cannot assign to 'value' because it is a read-only property.ts(2540)
// range.value = 12;

// Returns 9 of type number | undefined.
range.setValueToStep(3).value;

// Returns 27 of type number | undefined.
range.setValueToStep(9).value;

// Returns undefined of type number | undefined.
range.setValueToStep(11).value;
```
