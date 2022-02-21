---
description: Changes the default tag to 'Greater' for an instance
---

# get \[Symbol.toStringTag]\()

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag), changes the default tag to `'Greater'` for an instance of [`Greater`](broken-reference).

{% code title="greater.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'Greater';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

## Example usage

```typescript
// Example usage.
import { Greater } from '@angular-package/range';
import { typeOf } from '@angular-package/type';

// Returns "greater".
typeOf(new Greater(5));
```
