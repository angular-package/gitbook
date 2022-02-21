---
description: >-
  Checks whether the primitive value of a child instance is greater than some
  given values
---

# greaterThanSome()

## `Inequality.prototype.greaterThanSome()`

Checks whether the [primitive value](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) of a child class instance is **greater** than **some** given [`values`](greaterthansome.md#...values-number).

{% code title="inequality.class.ts" %}
```typescript
public greaterThanSome(...values: number[]): boolean {
  return this.#greater.thanSome(...values);
}
```
{% endcode %}

### Parameters

#### `...values:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of the numbers to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [primitive value](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) of a child class instance is **greater** than **some** given [`values`](greaterthansome.md#...values-number).&#x20;

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

// Returns `true`.
year.greaterThanSome(1971, 1972, 1972, 1973);

// Returns `true`.
year.greaterThanSome(1971, 1972, 1972, 1973, 1982);
```
