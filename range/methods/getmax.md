---
description: Gets the maximum range of a specified `Range` object
---

# getMax()

## `Range.prototype.getMax()`

The `getMax()` method gets the **maximum** range of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public getMax(): Max {
  return this.#maximum.valueOf();
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Max`</mark>](../generic-type-variables.md#maxextendsnumber)<mark style="color:green;">``</mark>

### Returns

The **return value** is the **maximum** range of a generic type variable [`Max`](../generic-type-variables.md#maxextendsnumber).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns 27 of type 27.
range.getMax();
```
