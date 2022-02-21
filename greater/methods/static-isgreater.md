---
description: >-
  Checks whether the given value is the Greater instance of any or given
  primitive value
---

# static isGreater()

## `Greater.isGreater()`

Checks whether the given [`value`](static-isgreater.md#undefined) is the [`Greater`](broken-reference) instance of any or given primitive value.

{% code title="greater.class.ts" %}
```typescript
public static isGreater<Value extends number>(
  value: any,
  greaterValue?: Value
): value is Greater<Value> {
  return (
    typeof value === 'object' &&
    value instanceof this &&
    (typeof greaterValue === 'number'
      ? value.valueOf() === greaterValue
      : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable indicates captured type of the supplied [`greaterValue`](static-isgreater.md#greatervalue-value) via the [return type](static-isgreater.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Greater`](broken-reference) instance.

#### `greaterValue:`[<mark style="color:green;">`Value`</mark>](static-isgreater.md#valueextendsnumber)``

An optional value of generic type variable [`Value`](static-isgreater.md#valueextendsnumber) to check whether it's the primitive value of the given [`value`](static-isgreater.md#value-any).

### Return type

#### `Greater<`[<mark style="color:green;">`Value`</mark>](static-isgreater.md#valueextendsnumber)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-isgreater.md#value-any) is the [`Greater`](broken-reference) object that takes the generic type variable [`Value`](static-isgreater.md#valueextendsnumber).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given [`value`](static-isgreater.md#value-any) is the [`Greater`](broken-reference) instance of any or given [primitive value](static-isgreater.md#greatervalue-value).

## Example usage

```typescript
// Example usage.
import { Greater } from '@angular-package/range';

// Define constant `id`.
const id = 390;

// Returns Greater {390} of Greater<390>.
const id390 = Greater.create(id);

// Returns `true`.
Greater.isGreater(id390);

// Returns `false`.
Greater.isGreater(id390, 381);

// Returns `true`.
Greater.isGreater(id390, 390);
```
