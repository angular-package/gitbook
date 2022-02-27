---
description: >-
  Checks whether the value is less than a minimum range of a specified `Range`
  object
---

# minGreaterThan()

## `Range.prototype.minGreaterThan()`

The `minGreaterThan()` method checks whether the value is **less** than a **minimum range** of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public minGreaterThan(value: number): boolean {
  return this.#minimum.greaterThan(value);
}
```
{% endcode %}

### Parameters

#### `value:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;">``</mark>

The value of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)&#x20;

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](mingreaterthan.md#value-number) is less than **minimum range** of a specified [`Range`](broken-reference) object.

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns true.
range.minGreaterThan(3);

// Returns false.
range.minGreaterThan(4);
```
