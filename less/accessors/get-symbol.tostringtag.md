---
description: Changes the default tag to 'Less' for an instance
---

# get \[Symbol.toStringTag]\()

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag), changes the default tag to `'Less'` for an instance of [`Less`](broken-reference).

{% code title="less.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'Less';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

## Example usage

```typescript
// Example usage.
import { Less } from '@angular-package/range';
import { typeOf } from '@angular-package/type';

// Returns "less".
typeOf(new Less(5));
```
