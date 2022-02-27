---
description: >-
  Increments the range value of a specified `Range` object by the range step or
  given decrement
---

# valueDown()

## `Range.prototype.valueDown()`

The `valueDown()` method decrements the range [value](../accessors/value.md) of a specified [`Range`](broken-reference) object by the range [step](../accessors/get-step.md) or given [`stepDecrement`](valuedown.md#stepdecrement-number).

{% code title="range.class.ts" %}
```typescript
public valueDown(stepDecrement = 1): this {
  typeof this.value === 'number' &&
    stepDecrement > 0 &&
    this.setValue(this.value - stepDecrement * this.#step);
  return this;
}
```
{% endcode %}

### Parameters

#### `stepDecrement:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

The optional `stepDecrement` parameter of the [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type decrements the range [`value`](../properties/value.md#range.prototype.value). If no parameter is passed, `stepDecrement` defaults to **`1`**.

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

// Returns 10.
range.value;

// Returns 7.
range.valueDown().value;

// Returns 4.
range.valueDown(1).value;
```
