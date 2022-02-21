---
description: Checks whether some values are in the range of a specified `Range` object
---

# hasSome()

## `Range.prototype.hasSome()`

Checks whether some [`values`](hassome.md#...values-number) are in the range of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public hasSome(...values: number[]): boolean {
  return values.some((value) => this.has(value));
}
```
{% endcode %}

### Parameters

#### `...values:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`[]`

A rest parameter of numbers to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether some [`values`](hassome.md#...values-number) are in the range of a specified [`Range`](broken-reference) object.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns false.
range.hasSome(1, 2, 3);

// Returns true.
range.hasSome(4, 5, 6);

// Returns true.
range.hasSome(24, 25, 26);

// Returns true.
range.hasSome(27, 28, 29);
```
