---
description: The solution to the described error problem.
---

# fix

## `Wrap.prototype.fix`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains a possible solution to the described problem by returning the [`#fix`](../properties/fix.md) property of a specified object.

{% code title="wrap.class.ts" %}
```typescript
public get closing(): Closing {
  return this.#closing;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">`Closing`</mark>

The **return type** is the generic type variable [`Closing`](broken-reference) declared in the [`Wrap`](broken-reference) class.

### Returns

The **return value** is [closing](../../getting-started/basic-concepts.md#closing) of the wrap of a generic type variable [`Closing`](broken-reference).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns ] of type "]".
new Wrap(`[`, `]`, 'quote').closing;
```

