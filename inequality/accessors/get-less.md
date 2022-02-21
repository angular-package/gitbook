---
description: >-
  The get accessor obtains from the private #less property an instance of the
  Less
---

# get less()

## `Inequality.prototype.less`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains from the private [`#less`](../properties/less.md) property an instance of the [`Less`](broken-reference) with a [primitive value](../../less/methods/valueof.md) from a given [`value`](../constructor.md#value-value) of the [`Inequality`](broken-reference) constructor.

{% code title="inequality.class.ts" %}
```typescript
public get less(): Less<Value> {
  return this.#less;
}
```
{% endcode %}

### Return type

#### `Less<`[<mark style="color:green;">`Value`</mark>](../generic-type-variables.md#inequality-less-than-value-greater-than)`>`

The **return type** is the [`Less`](broken-reference) [primitive wrapper](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) object that takes the generic type variable [`Value`](../generic-type-variables.md#inequality-less-than-value-greater-than) of the [`Inequality`](broken-reference) object.

### Returns

The **return value** is the [`Less`](broken-reference) instance with a [primitive value](../../greater/methods/valueof.md) from the given [`value`](../constructor.md#value-value) of the [`Inequality`](broken-reference) constructor.

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

// Returns Less {1981} of Less<1981>
year.less;

// Returns `true`.
year.less.than(1982);

// Returns `false`.
year.less.thanEvery(1981, 1982, 1983);

// Returns `false`.
year.less.thanSome(1981, 1980, 1979);
```
