---
description: Returns the `ValidationError` instance of the given unique identification
---

# get()

## `ValidationErrors.prototype.get()`

Returns the [`ValidationError`](broken-reference) instance of the given [unique identification](../../getting-started/basic-concepts.md#unique-identification) [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="validation-errors.class.ts" %}
```typescript
public get<ErrorId extends Id>(
  id: ErrorId
): ValidationError<ErrorId> | undefined {
  return this.errors.get(id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../../rangeerrors/generic-type-variables.md#rangeerrors-less-than-id-greater-than)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../generic-type-variables.md#validationerrors-less-than-id-greater-than) of the [`Errors`](broken-reference) object indicates the type picked from the [`Id`](../generic-type-variables.md#validationerrors-less-than-id-greater-than) and its exact type is useful in picking the specific range error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)<mark style="color:green;">``</mark>

The [unique identification](../../getting-started/basic-concepts.md#unique-identification) number of generic type variable [`ErrorId`](get.md#erroridextendsid) to pick an error from the object.

### Return type

#### `ValidationError<`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)`> |`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

The **return type** is the [`ValidationError`](broken-reference) object that takes the generic type variable [`ErrorId`](get.md#erroridextendsid) or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is the [`ValidationError`](broken-reference) instance of the given [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { ValidationErrors } from '@angular-package/error';

// Define validation errors.
const validationErrors = new ValidationErrors(
  '(VE: 4332)',
  '(VE: 4331)',
  '(VE: 4330)'
);

// Set the `ValidationError` objects under the given identification numbers.
validationErrors
  .set('Age is 99', 'Age must be', '(VE: 4330)')
  .set('Detected numbers', 'Provide only letters', '(VE: 4331)');


// Returns ValidationError: Problem(VE: 4330): Age is 99 => Fix: Age must be
validationErrors.get('(VE: 4330)');
```
