---
description: Creates the Maximum instance with the given primitive value
---

# static create()

## `Maximum.create()`

Creates the [`Maximum`](broken-reference) instance with the given primitive [`value`](static-create.md#value-value).

{% code title="maximum.class.ts" %}
```typescript
public static define<Value extends number>(value: Value): Maximum<Value> {
  return new this(value);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`value`](static-create.md#value-value) via the [return type](static-create.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)<mark style="color:green;">``</mark>

The maximum number of generic type variable [`Value`](static-create.md#valueextendsnumber) to set with a new instance.

### Return type

#### `Maximum<`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)`>`

The **return type** is the [`Maximum`](broken-reference) [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) that takes the generic type variable [`Value`](static-create.md#valueextendsnumber).

### Returns

The **return value** is the [`Maximum`](broken-reference) instance of any or the given primitive [`value`](static-create.md#value-value).

## Example usage

```typescript
// Example usage.
import { Maximum } from '@angular-package/range';

// Returns Maximum {27} of Maximum<27>.
Maximum.create(27);
```
