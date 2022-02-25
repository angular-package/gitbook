---
description: Gets the minimum range of a specified `Range` object
---

# ⚠ getMin()

## `Range.prototype.getMin()`

{% hint style="danger" %}
**Deprecated**: This feature is no longer recommended. Avoid using it, and update existing code if possible. Be aware that this feature may cease to work at any time.
{% endhint %}

The `getMin()` method gets the **minimum** range of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public getMin(): Min {
  return this.#minimum.valueOf();
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Min`</mark>](../generic-type-variables.md#minextendsnumber)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [**minimum**](../properties/min.md#range.prototype.min) range of a generic type variable [`Min`](../generic-type-variables.md#minextendsnumber).

## Example usage

```typescript
// Example usage.
import { Method } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns 4 of type 4.
range.getMin();
```
