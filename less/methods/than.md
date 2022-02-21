---
description: >-
  Checks whether the primitive value of a specified object is less than the
  given value
---

# than()

## `Less.prototype.than()`

Checks whether the [primitive value](valueof.md) of a specified [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) is **less** than the given [`value`](than.md#value-number).

{% code title="less.class.ts" %}
```typescript
public than(value: number): boolean {
  return typeof value === 'number' ? this.valueOf() < value : false;
}
```
{% endcode %}

### Parameters

#### `value:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

The value of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type to test.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`boolean`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)<mark style="color:green;">``</mark>

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [primitive value](valueof.md) is **less** than the given [`value`](than.md#value-number).

## Example usage

```typescript
// Example usage.
import { Less } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns `false`.
new Less(id).than(389);

// Returns `false`.
new Less(id).than(390);

// Returns `true`.
new Less(id).than(391);
```
