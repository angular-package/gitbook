---
description: >-
  The `get` accessor obtains the range of an `Array` of the minimum to the
  maximum with the step of a specified `Range` object
---

# get range()

## `Range.prototype.range`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the range of an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of the [minimum](../properties/min.md) to the [maximum](../properties/max.md) with the [step](get-step.md) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public get range(): Readonly<Array<number>> {
  return this.getRange();
}
```
{% endcode %}

### Type

#### [<mark style="color:green;">`Readonly`</mark>](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)`<`[<mark style="color:green;">`Array`</mark>](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`>>`

### Returns

The **return value** is the range from [minimum](../properties/min.md) to the [maximum](../properties/max.md) of a read-only [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Returns
// (9) [3, 6, 9, 12, 15, 18, 21, 24, 27] of type readonly number[]
range.range;
```
