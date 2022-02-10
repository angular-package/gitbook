---
description: Checks whether the value of any type is an instance of `Error`.
---

# static isError()

## `Error.isError()`

Checks whether the [`value`](static-iserror.md#value-any) of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type is an instance of [`Error`](broken-reference) of any or the given [identification](static-iserror.md#id-id).

{% code title="error.class.ts" %}
```typescript
public static isError<Id extends string>(
  value: any,
  id?: Id
): value is Error<Id> {
  return super.isError(value, id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)``

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-iserror.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of the [`Error`](broken-reference) via [return type](static-iserror.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against the [`Error`](broken-reference) instance.

#### `id?:`[<mark style="color:green;">`Id`</mark>](static-iserror.md#idextendsstring)<mark style="color:green;">``</mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) of generic type variable [`Id`](static-iserror.md#idextendsstring) that the given [`value`](static-iserror.md#value-any) contains.

### Return type

#### `value is Error<`[<mark style="color:green;">`Id`</mark>](static-iserror.md#idextendsstring)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-iserror.md#value-any) is the [`Error`](broken-reference) object that takes the generic type variable [`Id`](static-iserror.md#idextendsstring).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](static-iserror.md#value-any) is an instance of [`Error`](broken-reference) of any or the given [`id`](static-iserror.md#id-id).

## Example usage

```typescript
// Example usage.
import { Error } from '@angular-package/error';

// Define error.
const err = Error.define('Wrong type', 'Change the type', 'TE:201');

// Returns true.
Error.isError(err);

// Returns true.
Error.isError(err, 'TE:201');

// Returns false.
Error.isError(err, 'TE:202');

// Returns false.
Error.isError(new Array());
```
