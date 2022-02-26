---
description: Retrieves the number of steps of the specified `Range` object
---

# get steps()

## `Range.prototype.steps`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor retrieves the [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) of steps of the specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public get steps(): number {
  return this.getRange().length;
}
```
{% endcode %}

### Type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 3, max: 27, value: 10} of Range<3, 27, 3>.
const range = new Range(3, 27, 10, 3);

// Returns 9 of number type.
range.steps;
```
