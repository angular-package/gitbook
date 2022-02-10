---
description: The `get` accessor obtains error name
---

# get name()

## ​`RangeError.prototype.name`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains error name of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type, set to `'RangeError'` that is being thrown.

{% code title="range-error.class.ts" %}
```typescript
public get name(): string {
  return 'RangeError';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

### Returns

The **return value** is the error instance name of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Returns "RangeError".
new RangeError('problem', 'Fix accessor.').name;
```
