---
description: Changes the default tag to 'RangeError' for an instance
---

# get \[Symbol.toStringTag]\()

## `[Symbol.toStringTag]()`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag), changes the default tag to `'RangeError'` for an instance of [`RangeError`](broken-reference).

It can be read by the [`typeOf()`](https://docs.angular-package.dev/v/type/helper/typeof) function of [`@angular-package/type`](https://docs.angular-package.dev/v/type/).

{% code title="range-error.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'RangeError';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;"></mark>

### Returns

The **return value** is the word `'RangeError'` of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';
import { typeOf } from '@angular-package/type';

// Returns "rangeerror".
typeOf(new RangeError('problem', 'Fix accessor.'));
```
