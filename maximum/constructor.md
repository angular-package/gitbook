---
description: Creates the Maximum instance of the given primitive value
---

# ★ Constructor

## `Maximum()`

Creates the [`Maximum`](broken-reference) instance of the given primitive [`value`](constructor.md#value-value).

{% code title="maximum.class.ts" %}
```typescript
constructor(value: Value) {
  super(value);
}
```
{% endcode %}

### `Parameters`

#### `value:`[<mark style="color:green;">`Value`</mark>](generic-type-variables.md#maximum-less-than-value-greater-than)<mark style="color:green;">``</mark>

The value of the generic type variable [`Value`](generic-type-variables.md#maximum-less-than-value-greater-than) is the primitive value of the new instance.

## Example usage

```typescript
// Example usage.
import { Maximum } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Maximum {390} of Maximum<390>.
new Maximum(id);
```
