---
description: >-
  The get accessor obtains from the private #greater property an instance of the
  Greater
---

# get greater()

## `Inequality.prototype.greater`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains from the private [`#greater`](../properties/greater.md) property an instance of the [`Greater`](broken-reference) with a [primitive value](../../greater/methods/valueof.md) from a given [`value`](../constructor.md#value-value) of the [`Inequality`](broken-reference) constructor.

{% code title="inequality.class.ts" %}
```typescript
public get greater(): Greater<Value> {
  return this.#greater;
}
```
{% endcode %}

### Return type

#### `Greater<`[<mark style="color:green;">`Value`</mark>](../generic-type-variables.md#inequality-less-than-value-greater-than)`>`

The **return type** is the [`Greater`](broken-reference) [primitive wrapper](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) object that takes the generic type variable [`Value`](../generic-type-variables.md#inequality-less-than-value-greater-than) of the [`Inequality`](broken-reference) object.

### Returns

The **return value** is the [`Greater`](broken-reference) instance with a [primitive value](../../greater/methods/valueof.md) from the given [`value`](../constructor.md#value-value) of the [`Inequality`](broken-reference) constructor.

## Example usage

```typescript
// Example usage.
import { Inequality } from '@angular-package/range';

// Define the `Year` class and extend it with `Inequality`.
class Year<Value extends number> extends Inequality<Value> {}

// Initialize `Year`.
const year = new Year(1981);

// Returns Year {1981} of Year<1981>.
year;

// Returns Greater {1981} of Greater<1981>
year.greater;

// Returns `false`.
year.greater.than(1982);

// Returns `false`.
year.greater.thanEvery(1981, 1982, 1983);

// Returns `true`.
year.greater.thanSome(1981, 1980, 1979);
```
