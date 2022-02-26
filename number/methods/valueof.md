---
description: >-
  Returns the primitive value of the generic type variable `Value` of the
  specified `Number` object
---

# valueOf()

## `Number.prototype.valueOf()`

The `valueOf()` method returns the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of the generic type variable [`Value`](../generic-type-variables.md#number-less-than-value-greater-than) of the specified [`Number`](broken-reference) object.

{% embed url="https://github.com/angular-package/range/blob/main/src/lib/range.class.ts" %}
`range.class.ts`
{% endembed %}

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf" %}
`String.prototype.valueOf()`
{% endembed %}

{% code title="number.class.ts" %}
```typescript
public valueOf(): Value {
  return super.valueOf() as Value;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Value`</mark>](../generic-type-variables.md#number-less-than-value-greater-than)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of generic type variable [`Value`](../generic-type-variables.md#number-less-than-value-greater-than).

## Example usage

```typescript
// Example usage.
import { Number } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns 390 of type 390.
new Number(id).valueOf();
```
