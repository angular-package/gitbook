---
description: The `Less` primitive wrapper object constructor
---

# ★ Constructor

## `Less()`

Creates the [`Less`](broken-reference) instance with the given [`value`](constructor.md#value-value).

{% code title="less.class.ts" %}
```typescript
constructor(value: Value) {
  super(value);
}
```
{% endcode %}

### `Parameters`

#### `value:`[<mark style="color:green;">`Value`</mark>](generic-type-variables.md#less-less-than-value-greater-than)<mark style="color:green;">``</mark>

The value of generic type variable [`Value`](generic-type-variables.md#less-less-than-value-greater-than) to set with a new instance.

## Example usage

```typescript
// Example usage.
import { Less } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Less{390} of Less<390>.
new Less(id);
```
