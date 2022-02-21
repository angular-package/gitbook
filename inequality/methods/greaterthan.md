---
description: >-
  Checks whether the primitive value of a child class is greater than the given
  value
---

# greaterThan()

## `Inequality.prototype.greaterThan()`

Checks whether the [primitive value](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) of a child class instance is **greater** than the given [`value`](greaterthan.md#...values-number).

{% code title="inequality.class.ts" %}
```typescript
public greaterThan(value: number): boolean {
  return this.#greater.than(value);
}
```
{% endcode %}

### Parameters

#### `value:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of the numbers to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [primitive value](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) of a child class instance is **greater** than the given [`value`](greaterthan.md#value-number).

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

// Returns false. 1981 > 1982.
year.greaterThan(1982);

// Returns true. 1981 > 1980.
year.greaterThan(1980);
```
