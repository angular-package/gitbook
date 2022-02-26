---
description: The `Number` primitive wrapper constructor
---

# ★ Constructor

## `Number()`

Creates the [`Number`](broken-reference) instance of the given primitive [`value`](constructor.md#value-value).

{% code title="number.class.ts" %}
```typescript
constructor(value: Value) {
  super(value);
}
```
{% endcode %}

### `Parameters`

#### `value:`[<mark style="color:green;">`Value`</mark>](../minimum/generic-type-variables.md#minimum-less-than-value-greater-than)<mark style="color:green;">``</mark>

The value of the generic type variable [`Value`](../minimum/generic-type-variables.md#minimum-less-than-value-greater-than) is the primitive value of the new instance.

## Example usage

```typescript
// Example usage.
import { Number } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Number {390} of Number<390>.
new Number(id);
```
