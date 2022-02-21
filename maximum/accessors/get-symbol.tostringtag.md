---
description: Changes the default tag to 'Maximum' for an instance
---

# get \[Symbol.toStringTag]\()

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag), changes the default tag to `'Maximum'` for an instance of [`Maximum`](broken-reference).

{% code title="maximum.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'Maximum';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

## Example usage

```typescript
// Example usage.
import { Maximum } from '@angular-package/range';
import { typeOf } from '@angular-package/type';

// Returns "maximum".
typeOf(new Maximum(5));
```
