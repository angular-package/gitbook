---
description: The `Greater` primitive wrapper object constructor
---

# ★ Constructor

## `Greater()`

Creates the [`Greater`](broken-reference) instance with the given [`value`](constructor.md#undefined).

{% code title="greater.class.ts" %}
```typescript
constructor(value: Value) {
  super(value);
}
```
{% endcode %}

### `Parameters`

#### `value:`[<mark style="color:green;">`Value`</mark>](generic-type-variables.md#greater-less-than-value-greater-than)<mark style="color:green;">``</mark>

The value of generic type variable [`Value`](generic-type-variables.md#greater-less-than-value-greater-than) to set with a new instance.

## Example usage

```typescript
// Example usage.
import { Greater } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Greater {390} of Greater<390>.
new Greater(id);
```
