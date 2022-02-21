---
description: Creates the Minimum instance with the given primitive value
---

# static create()

## `Minimum.create()`

The static `create()` method creates the [`Minimum`](broken-reference) instance with the given primitive [`value`](static-create.md#value-value).

{% code title="minimum.class.ts" %}
```typescript
public static create<Value extends number>(value: Value): Minimum<Value> {
  return new this(value);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`value`](static-create.md#value-value) via the [return type](static-create.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)<mark style="color:green;">``</mark>

The minimum number of generic type variable [`Value`](static-create.md#valueextendsnumber) to set with a new instance.

### Return type

#### `Minimum<`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)`>`

The **return type** is the [`Minimum`](broken-reference) [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) that takes the generic type variable [`Value`](static-create.md#valueextendsnumber).

### Returns

The **return value** is the [`Minimum`](broken-reference) instance with the [primitive value](valueof.md#minimum.prototype.valueof) of the given [`value`](static-create.md#value-value).

## Example usage

```typescript
// Example usage.
import { Minimum } from '@angular-package/range';

// Returns Minimum {27} of Minimum<27>.
Minimum.create(27);
```
