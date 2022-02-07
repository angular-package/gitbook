---
description: The name of the `Error` object class.
---

# get \[Symbol.toStringTag]\()

## `[Symbol.toStringTag]()`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag), changes the default tag to `'Error'` for an instance of [`Error`](broken-reference). It can be read by the [`typeOf()`](https://docs.angular-package.dev/v/type/helper/typeof) function of [`@angular-package/type`](https://docs.angular-package.dev/v/type/).

{% code title="error.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'Error';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;"></mark>

### Returns

The **return value** is the word `Error` of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

## Example usage

```typescript
// Example usage.
import { Error } from '@angular-package/error';
import { typeOf } from '@angular-package/type';

// Returns "error".
typeOf(new Error('problem', 'fix solution'));
```
