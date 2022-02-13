---
description: The `get` accessor obtains the maximum range
---

# get max()

## `RangeError.prototype.max`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the maximum range of generic type variable [`Max`](../4-generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-2) that causes an error to be thrown(or not thrown), if set, otherwise returns [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="range-error.class.ts" %}
```typescript
public get max(): Max | undefined {
  return this.#max;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Max`</mark>](../4-generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-2)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

### Returns

The **return value** is the maximum range of generic type variable [`Max`](../4-generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-2) or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Returns "27".
new RangeError('problem', 'Fix accessor.', '(AE:427)', 9, 27).max;
```
