---
description: Checks whether the value is in the range of a specified `Range` object
---

# has()

## `Range.prototype.has()`

The `has()` method checks whether the [`value`](has.md#value-number) is in the range of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public has(value: number): boolean {
  return (
    (this.minLessThan(value) && this.maxGreaterThan(value)) ||
    value === this.min ||
    value === this.max
  );
}
```
{% endcode %}

### Parameters

#### `value:`<mark style="color:green;">`number`</mark>

The value of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given [`value`](has.md#value-number) is in the range of a specified [`Range`](broken-reference) object.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns false.
range.has(3);

// Returns true.
range.has(4);

// Returns false.
range.has(28);

// Returns true.
range.has(27);
```
