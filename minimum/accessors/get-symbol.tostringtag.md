---
description: >-
  The get accessor, with the help of toStringTag, changes the default tag to
  'Minimum' for an instance of Minimum
---

# get \[Symbol.toStringTag]\()

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag), changes the default tag to `'Minimum'` for an instance of [`Minimum`](broken-reference).

{% code title="minimum.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'Minimum';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

## Example usage

```typescript
// Example usage.
import { Minimum } from '@angular-package/range';
import { typeOf } from '@angular-package/type';

// Returns "minimum".
typeOf(new Minimum(5));
```
