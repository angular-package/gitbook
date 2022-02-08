---
description: The `get` accessor obtains error name
---

# get name()

## `ValidationError.prototype.name`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains error name of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type, set to `'ValidationError'` that is being thrown.

{% code title="type-error.class.ts" %}
```typescript
public get name(): string {
  return 'ValidationError';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;"></mark>

### Returns

The **return value** is the error instance name of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { ValidationError } from '@angular-package/error';

// Returns "ValidationError".
new ValidationError('problem', 'Fix accessor.').name;
```
