---
description: >-
  Checks whether the range of a specified `Range` object is between every range
  of the given `ranges`
---

# isBetweenEvery()

## `Range.prototype.isBetweenEvery()`

Checks whether the range of a specified [`Range`](broken-reference) object is between every range of the given [`ranges`](isbetweenevery.md#...ranges-number-number).

{% code title="range.class.ts" %}
```typescript
public isBetweenEvery(...ranges: [number, number][]): boolean {
  return ranges.every((range) =>
    range[0] <= range[1] ? this.hasEvery(...range) : false
  );
}
```
{% endcode %}

### Parameters

#### `...ranges: [`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`,`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`][]`

A rest parameter of ranges of an [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) type to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)&#x20;

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the range of a specified [`Range`](broken-reference) object is between **every** range of the given [`ranges`](isbetweenevery.md#...ranges-number-number).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns false.
range.isBetweenEvery([3, 26], [4, 27], [5, 28]);

// Returns true.
range.isBetweenEvery([4, 27], [5, 26], [6, 25]);
```
