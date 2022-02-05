---
description: The solution to the described error problem.
---

# fix

## `Wrap.prototype.fix`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains a possible solution to the described problem by returning the [`#fix`](../properties/fix.md) property of a specified object.

{% code title="wrap.class.ts" %}
```typescript
public get fix(): string {
  return this.#fix;
}
```
{% endcode %}

### Returns

The **return value** is [closing](../../getting-started/basic-concepts.md#closing) of the wrap of a generic type variable [`Closing`](broken-reference).

The **return value** is the fix of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns ] of type "]".
new Wrap(`[`, `]`, 'quote').closing;
```

