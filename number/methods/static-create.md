---
description: Creates the `Number` instance with the given primitive value
---

# static create()

## `Number.create()`

The static `create()` method creates the [`Number`](broken-reference) instance with the given primitive [`value`](static-create.md#value-value).

{% code title="number.class.ts" %}
```typescript
public static create<Value extends number>(value: Value): Number<Value> {
  return new this(value);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`value`](static-create.md#value-value) via the [return type](static-create.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)

The number of generic type variable [`Value`](static-create.md#valueextendsnumber) to set with a new instance.

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Number`</mark>](broken-reference)`<`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)`>`

The **return type** is the [`Number`](broken-reference) [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) that takes the generic type variable [`Value`](static-create.md#valueextendsnumber).

### Returns

The **return value** is the [`Number`](broken-reference) instance with the [primitive value](../../minimum/methods/valueof.md#minimum.prototype.valueof) of the given [`value`](static-create.md#value-value).

## Example usage

```typescript
// Example usage.
import { Number } from '@angular-package/range';

// Returns Number {27} of Number<27>.
Number.create(27);
```
