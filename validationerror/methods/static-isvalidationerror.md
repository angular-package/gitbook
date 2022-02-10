---
description: Checks whether the value of any type is an instance of `ValidationError`
---

# static isValidationError()

## `ValidationError.isValidationError()`

Checks whether the [`value`](static-isvalidationerror.md#value-any) of any type is the [`ValidationError`](broken-reference) instance of any or the given [identification](static-isvalidationerror.md#id-id).

{% code title="validation-error.class.ts" %}
```typescript
public static isValidationError<Id extends string>(
  value: any,
  id?: Id
): value is ValidationError<Id> {
  return super.isError(value, id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)``

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-isvalidationerror.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of the [`ValidationError`](broken-reference) via [return type](static-isvalidationerror.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against the [`ValidationError`](broken-reference) instance.

#### `id?:`[<mark style="color:green;">`Id`</mark>](../../error/generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) of generic type variable [`Id`](static-isvalidationerror.md#id-extends-string) to check whether the given [`value`](static-isvalidationerror.md#value-any) contains.

### Return type

#### `value is ValidationError<`[<mark style="color:green;">`Id`</mark>](static-isvalidationerror.md#id-extends-string)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-isvalidationerror.md#value-any) is the [`ValidationError`](broken-reference) object that takes the generic type variable [`Id`](static-isvalidationerror.md#id-extends-string).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](static-isvalidationerror.md#value-any) is an instance of [`ValidationError`](broken-reference) of any or the supplied optional [`id`](static-isvalidationerror.md#id-id) properties.

## Example usage

```typescript
// Example usage.
import { ValidationError } from '@angular-package/error';

// Define error.
const err = ValidationError.define('Wrong type', 'Change the type', 'TE:201');

// Returns true.
ValidationError.isValidationError(err);

// Returns true.
ValidationError.isValidationError(err, 'TE:201');

// Returns true.
ValidationError.isValidationError(err, 'TE:201');

// Returns false.
ValidationError.isValidationError(err, 'TE:202');

// Returns false.
ValidationError.isValidationError(new Array());
```
