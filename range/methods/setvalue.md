---
description: >-
  Sets the range value between the minimum and maximum of a specified `Range`
  object
---

# setValue()

## `Range.prototype.setValue()`

The method `setValue()` sets the range [value](../properties/value.md#range.prototype.value) between the [minimum](../properties/min.md#range.prototype.min) and [maximum](../properties/max.md#range.prototype.max) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public setValue(value: number): this {
  this.has(value) &&
    Object.defineProperty(this, 'value', {
      configurable: true,
      value,
      writable: false,
    });
  return this;
}
```
{% endcode %}

### Parameters

#### `value:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

The value of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to test.

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
range.value = 12;

// Returns 10 of type number | undefined.
range.setValue(300).value;

// Returns 27 of type number | undefined.
range.setValue(27).value;
```
