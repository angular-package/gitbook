---
description: The minimum range of a specified `Range` object
---

# min

## `Range.prototype.min`

The `min` read-only property is the minimum range of generic type variable [`Min`](../generic-type-variables.md#minextendsnumber) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public readonly min!: Min;
```
{% endcode %}

### Type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Min`</mark>](../generic-type-variables.md#minextendsnumber)<mark style="color:green;">``</mark>

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 4, max: 27} of Range<4, 27, 1>.
const range = new Range(4, 27);

// Returns 4 of type 4.
range.min;
```
