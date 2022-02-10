---
description: The `get` accessor obtains the range of minimum and maximum
---

# get range()

## ​`RangeError.prototype.range`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the [minimum](get-min.md) and [maximum](get-max.md) range in the form of an [object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object).

{% code title="range-error.class.ts" %}
```typescript
public get range(): { min?: Min; max?: Max } {
  return {
    min: this.#min,
    max: this.#max,
  };
}
```
{% endcode %}

### Return type

#### `{ min?:`[<mark style="color:green;">`Min`</mark>](../generic-type-variables.md#wrap-opening-1)`; max?:`[<mark style="color:green;">`Max`</mark>](../generic-type-variables.md#wrap-opening-2)`}`

The **return type** is the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) that consists of the `min` and `max` properties, indicating the error range.

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that consists of the [minimum](get-min.md) range under the `min` property and the [maximum](get-max.md) under the `max` property.

`min` - The minimum range of generic type variable [`Min`](../generic-type-variables.md#wrap-opening-1) of the [`RangeError`](broken-reference) instance.\
`max` - The maximum range of generic type variable [`Max`](../generic-type-variables.md#wrap-opening-2) of the [`RangeError`](broken-reference) instance.

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Returns "{min: 9, max: 27}".
new RangeError('problem', 'Fix accessor.', '(AE:427)', 9, 27).range;
```