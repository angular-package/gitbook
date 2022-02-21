---
description: >-
  Checks whether the given value is the Less instance of any or given primitive
  value
---

# static isLess()

## `Less.isLess()`

Checks whether the given [`value`](static-isless.md#undefined) is the [`Less`](broken-reference) instance of any or given primitive [value](static-isless.md#lessvalue-value).

{% code title="less.class.ts" %}
```typescript
public static isLess<Value extends number>(
  value: any,
  lessValue?: Value
): value is Less<Value> {
  return (
    typeof value === 'object' &&
    value instanceof this &&
    (typeof lessValue === 'number' ? value.valueOf() === lessValue : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`lessValue`](static-isless.md#lessvalue-value) via the [return type](static-isless.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Less`](broken-reference) instance.

#### `lessValue:`[<mark style="color:green;">`Value`</mark>](static-isless.md#valueextendsnumber)``

An optional value of generic type variable [`Value`](static-isless.md#valueextendsnumber) to check whether it's the primitive value of the given [`value`](static-isless.md#value-any).

### Return type

#### `Lees<`[<mark style="color:green;">`Value`</mark>](static-isless.md#valueextendsnumber)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-isless.md#value-any) is the [`Less`](broken-reference) object that takes the generic type variable [`Value`](static-isless.md#valueextendsnumber).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given [`value`](static-isless.md#value-any) is the [`Less`](broken-reference) instance of any or given [primitive value](static-isless.md#lessvalue-value).

## Example usage

```typescript
// Example usage.
import { Less } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Less {390} of Less<390>.
const id390 = Less.create(id);

// Returns `true`.
Less.isLess(id390);

// Returns `false`.
Less.isLess(id390, 381);

// Returns `true`.
Less.isLess(id390, 390);
```
