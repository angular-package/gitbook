---
description: The `get` accessor obtains error name
---

# get name()

## `Error.prototype.name`

Error name of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type, set to [`Error`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Error) that is being thrown.

{% code title="error.class.ts" %}
```typescript
public get name(): string {
  return 'Error';
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;"></mark>

### Returns

The **return value** is the error instance name of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.&#x20;

## Example usage

```typescript
// Example usage.
import { Error } from '@angular-package/error';

// Returns "Error".
new Error('Wrong type', 'Change the type', 'TE:201').name;
```
