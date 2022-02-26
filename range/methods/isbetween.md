---
description: >-
  Checks whether range of the given `min` and `max` is between the range of a
  specified `Range` object
---

# isBetween()

## `Range.prototype.isBetween()`

The `isBetween()` method checks whether range of the given [`min`](isbetween.md#min-number) and [`max`](isbetween.md#max-number) is between the range of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public isBetween(min: number, max: number): boolean {
  return min <= max ? this.hasEvery(min, max) : false;
}
```
{% endcode %}

### Parameters

#### `min:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

The **minimum** range of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to test.

#### `max:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

The **maximum** range of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)&#x20;

### Returns

The **return value**  is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the range of a specified [`Range`](broken-reference) object is between a range of the given [`min`](isbetween.md#min-number) and [`max`](isbetween.md#max-number).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns false.
range.isBetween(3, 26);

// Returns true.
range.isBetween(4, 27);

// Returns false.
range.isBetween(5, 28);
```
