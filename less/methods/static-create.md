---
description: Creates the Less instance with the given primitive value
---

# static create()

## `Less.create()`

Creates the [`Less`](broken-reference) instance with the given primitive [`value`](static-create.md#value-value).

{% code title="less.class.ts" %}
```typescript
public static create<Value extends number>(value: Value): Less<Value> {
  return new this(value);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`value`](static-create.md#value-value) via the [return type](static-create.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)<mark style="color:green;">``</mark>

The value of generic type variable [`Value`](static-create.md#valueextendsnumber) to set with a newly created instance.

### Return type

#### `Less<`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)`>`

The **return type** is the [`Less`](broken-reference) [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) that takes the generic type variable [`Value`](static-create.md#valueextendsnumber).

### Returns

The **return value** is the [`Less`](broken-reference) instance with the [primitive value](valueof.md#less.prototype.valueof) of the given [`value`](static-create.md#value-value).

## Example usage

```typescript
// Example usage.
import { Greater } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Less {390} of Less<390>.
Less.create(id);
```
