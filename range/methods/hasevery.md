---
description: >-
  Checks whether every value of the given values is in the range of a specified
  `Range` object
---

# hasEvery()

## `Range.prototype.hasEvery()`

The `hasEvery()` method checks whether every value of the given [`values`](hasevery.md#...values-number) is in the range of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public hasEvery(...values: number[]): boolean {
  return values.every((value) => this.has(value));
}
```
{% endcode %}

### Parameters

#### `...values:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`[]`

A rest parameter of numbers to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether every value of the given [`values`](hasevery.md#parameter-type) is in the range of a specified [`Range`](broken-reference) object.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns false.
range.hasEvery(1, 2, 3);

// Returns true.
range.hasEvery(4, 5, 6);

// Returns true.
range.hasEvery(24, 25, 26);

// Returns false.
range.hasEvery(27, 28, 29);
```
