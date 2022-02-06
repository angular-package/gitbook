---
description: The solution to the described error problem.
---

# fix

## `CommonError.prototype.fix`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains a possible solution to the described [problem](problem.md) by returning the [`#fix`](../../properties/instance/fix.md) property of a specified object.

{% code title="common-error.class.ts" %}
```typescript
public get fix(): string {
  return this.#fix;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

### Returns

The **return value** is the fix of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

// Extend the `CommonError` class.
class TestError extends CommonError {}

// Returns "Fix accessor."
new TestError('problem', 'Fix accessor.', '(AE:427)').fix;
```
