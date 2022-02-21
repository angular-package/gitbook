---
description: Returns the primitive value of a specified object
---

# valueOf()

## `Less.prototype.valueOf()`

Returns the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of a specified object.

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf" %}

{% code title="less.class.ts" %}
```typescript
public valueOf(): Value {
  return super.valueOf() as any;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Value`</mark>](../generic-type-variables.md)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of generic type variable [`Value`](../generic-type-variables.md#less-less-than-value-greater-than).

## Example usage

```typescript
// Example usage.
import { Less } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns 390 of type 390.
new Less(id).valueOf();
```
