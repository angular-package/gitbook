---
description: The `get` accessor obtains the minimum range
---

# get min()

## `RangeError.prototype.min`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the minimum range of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type that causes an error to be thrown(or not thrown), if set, otherwise returns [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="range-error.class.ts" %}
```typescript
public get min(): number | undefined {
  return this.#min;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">number</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) | [<mark style="color:green;">undefined</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;"></mark>

### Returns

The **return value** is the minimum range of a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Returns "9".
new RangeError('problem', 'Fix accessor.', '(AE:427)', 9, 27).min;
```
