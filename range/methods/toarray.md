---
description: Returns a read-only array of the range in order minimum and maximum
---

# toArray()

## `Range.prototype.toArray()`

The `toArray()` method returns a read-only array of the range in order minimum and maximum.

{% code title="range.class.ts" %}
```typescript
public toArray(): readonly [Min, Max] {
  return [this.#minimum.valueOf(), this.#maximum.valueOf()];
}
```
{% endcode %}

### Return type

#### Type

The **return type**&#x20;

### Returns

The **return value** is a read-only array of the range in order minimum and maximum.&#x20;

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns [4, 27] of type readonly [4, 27]
range.toArray();
```
