# closing

## `Wrap.prototype.closing`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [closing](../../library/basic-concepts.md#closing) of the wrap by returning the [`#closing`](../properties/closing.md) property of the specified object.

{% code title="wrap.class.ts" %}
```typescript
public get closing(): Closing {
  return this.#closing;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">`Closing`</mark>

The **return type** is the generic type variable [`Closing`](../generic-type-variables.md#wrap-closing) declared in the [`Wrap`](broken-reference) class.

### Returns

The **return value** is [closing](../../library/basic-concepts.md#closing) of the wrap of a generic type variable [`Closing`](../generic-type-variables.md#wrap-closing).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns ] of type "]".
new Wrap(`[`, `]`, 'quote').closing;
```
