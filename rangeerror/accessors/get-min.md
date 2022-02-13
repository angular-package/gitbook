---
description: The `get` accessor obtains the minimum range
---

# get min()

## `RangeError.prototype.min`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the minimum range of generic type variable [`Min`](../4-generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-1) that causes an error to be thrown(or not thrown), if set, otherwise returns [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="range-error.class.ts" %}
```typescript
public get min(): Min | undefined {
  return this.#min;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Min`</mark>](../4-generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-1)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

### Returns

The **return value** is the minimum range of generic type variable [`Min`](../4-generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-1) or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Returns "9".
new RangeError('problem', 'Fix accessor.', '(AE:427)', 9, 27).min;
```
