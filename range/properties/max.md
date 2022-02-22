---
description: The maximum range of a specified `Range` object
---

# max

## `Range.prototype.max`

The `max` read-only property is the maximum range of generic type variable [`Max`](../generic-type-variables.md#maxextendsnumber) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public readonly max!: Max;
```
{% endcode %}

### Type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Max`</mark>](../generic-type-variables.md#maxextendsnumber)<mark style="color:green;">``</mark>

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 4, max: 27} of Range<4, 27>.
const range = new Range(4, 27);

// Returns 27 of type 27.
range.max;
```
