---
description: >-
  The get accessor, with the help of toStringTag, changes the default tag to
  'Range' for an instance of Range
---

# get \[Symbol.toStringTag]\()

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag), changes the default tag to `'Range'` for an instance of [`Range`](broken-reference).

{% code title="range.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'Range';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';
import { typeOf } from '@angular-package/type';

// Returns "range".
typeOf(new Range(4, 27));
```
