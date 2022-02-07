---
description: >-
  The `get` accessor gets the opening of the wrap by returning the `#opening`
  property of the specified object.
---

# get opening()

## `Wrap.prototype.opening`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [opening](../../getting-started/basic-concepts.md#opening) of the wrap by returning the [`#opening`](../properties/opening.md) property of the specified object.

{% code title="wrap.class.ts" %}
```typescript
public get opening(): Opening {
  return this.#opening;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">`Opening`</mark>

The **return type** is the generic type variable [`Opening`](../generic-type-variables.md#wrap-opening) declared in the [`Wrap`](broken-reference) class.

### Returns

The **return value** is the [opening](../../getting-started/basic-concepts.md#opening) of the wrap of a generic type variable [`Opening`](../generic-type-variables.md#wrap-opening).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns [ of type "[".
new Wrap(`[`, `]`, 'quote').opening;
```
