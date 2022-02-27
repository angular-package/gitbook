---
description: >-
  Checks whether the value is less than the maximum range of a specified `Range`
  object
---

# maxGreaterThan()

## `Range.prototype.maxGreaterThan()`

The `maxGreaterThan()` method checks whether the [`value`](maxgreaterthan.md#value-number) is **less** than the [**maximum**](../properties/max.md) **range** of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public maxGreaterThan(value: number): boolean {
  return this.#maximum.greaterThan(value);
}
```
{% endcode %}

### Parameters

#### `value:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;">``</mark>

The value of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](maxgreaterthan.md#value-number) is **less** than [**maximum**](../properties/max.md) **range** of a specified [`Range`](broken-reference) object.&#x20;

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns true.
range.maxGreaterThan(26);

// Returns false.
range.maxGreaterThan(27);
```
