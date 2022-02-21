---
description: >-
  Checks whether the primitive value of a specified object is less than every
  value of the given values
---

# thanEvery()

## `Less.prototype.thanEvery()`

Checks whether the [primitive value](valueof.md) of a specified [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) is **less** than **every** value of the given [`values`](thanevery.md#...values-number).

{% code title="less.class.ts" %}
```typescript
public thanEvery(...values: number[]): boolean {
  return Array.isArray(values)
    ? values.every((value) => this.valueOf() < value)
    : false;
}
```
{% endcode %}

### Parameters

#### `...values:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of the numbers to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [primitive value](valueof.md) is **less** than **every** value of the given [`values`](thanevery.md#...values-number).

## Example usage

```typescript
// Example usage.
import { Less } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns `false`.
new Less(id).thanEvery(387, 388, 390);

// Returns `true`.
new Less(id).thanEvery(393, 392, 394, 391);
```
