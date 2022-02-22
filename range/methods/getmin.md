---
description: Gets the minimum range of a specified `Range` object
---

# getMin()

## `Range.prototype.getMin()`

The `getMin()` method gets the **minimum** range of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public getMin(): Min {
  return this.#minimum.valueOf();
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Min`</mark>](../r-generic-type-variables.md#minextendsnumber)<mark style="color:green;">``</mark>

### Returns

The **return value** is the **minimum** range of a generic type variable [`Min`](../r-generic-type-variables.md#minextendsnumber).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns 4 of type 4.
range.getMin();
```
