---
description: The `Minimum` primitive wrapper object constructor
---

# ★ Constructor

## `Minimum()`

Creates the [`Minimum`](broken-reference) instance of the given primitive [`value`](constructor.md#value-value).

{% code title="minimum.class.ts" %}
```typescript
constructor(value: Value) {
  super(value);
}
```
{% endcode %}

### `Parameters`

#### `value:`[<mark style="color:green;">`Value`</mark>](generic-type-variables.md#minimum-less-than-value-greater-than)<mark style="color:green;">``</mark>

The value of the generic type variable [`Value`](generic-type-variables.md#minimum-less-than-value-greater-than) is the primitive value of the new instance.

## Example usage

```typescript
// Example usage.
import { Minimum } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Minimum {390} of Minimum<390>.
new Minimum(id);
```
