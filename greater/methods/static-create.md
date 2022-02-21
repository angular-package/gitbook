---
description: Creates the Greater instance with the given primitive value.
---

# static create()

## `Greater.create()`

Creates the [`Greater`](broken-reference) instance with the given primitive [`value`](static-create.md#value-value).

{% code title="greater.class.ts" %}
```typescript
public static create<Value extends number>(value: Value): Greater<Value> {
  return new this(value);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`value`](static-create.md#value-value) via the [return type](static-create.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`Value`</mark>](static-create.md#value-extends-number)<mark style="color:green;">``</mark>

The value of generic type variable [`Value`](static-create.md#valueextendsnumber) to set with a newly created instance.

### Return type

#### `Greater<`[<mark style="color:green;">`Value`</mark>](static-create.md#valueextendsnumber)`>`

The **return type** is the [`Greater`](broken-reference) [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) that takes the generic type variable [`Value`](static-create.md#valueextendsnumber).

### Returns

The **return value** is the [`Greater`](broken-reference) instance with the [primitive value](valueof.md) of the given [`value`](static-create.md#value-value).

## Example usage

```typescript
// Example usage.
import { Greater } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Greater {390} of Greater<390>.
Greater.create(id);
```
