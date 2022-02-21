---
description: Returns the primitive value of a specified Minimum object
---

# valueOf()

## `Minimum.prototype.valueOf()`

The `valueOf()` method returns the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of the generic type variable [`Value`](../generic-type-variables.md#minimum-less-than-value-greater-than) of the specified [`Minimum`](broken-reference) object.

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf" %}

{% code title="minimum.class.ts" %}
```typescript
public valueOf(): Value {
  return super.valueOf() as Value;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Value`</mark>](../generic-type-variables.md#minimum-less-than-value-greater-than)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of generic type variable [`Value`](../generic-type-variables.md#minimum-less-than-value-greater-than).

## Example usage

```typescript
// Example usage.
import { Minimum } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns 390 of type 390.
new Minimum(id).valueOf();
```
