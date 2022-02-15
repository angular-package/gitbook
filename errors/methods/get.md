---
description: Returns the `Error` instance of the given unique identification
---

# get()

## `Errors.prototype.get()`

Returns the [`Error`](broken-reference) instance of the given unique identification [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="errors.class.ts" %}
```typescript
public get<ErrorId extends Id>(id: ErrorId): Error<ErrorId> | undefined {
  return this.errors.get(id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#errors-less-than-id-greater-than)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../generic-type-variables.md#errors-less-than-id-greater-than) of the [`Errors`](broken-reference) object indicates the type picked from the [`Id`](../generic-type-variables.md#errors-less-than-id-greater-than) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)<mark style="color:green;">``</mark>

The [unique identification](../../getting-started/basic-concepts.md#unique-identification) number of generic type variable [`ErrorId`](get.md#erroridextendsid) to pick an error from the object.

### Return type

#### `Error<`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)`> |`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

The **return type** is the [`Error`](broken-reference) object that takes the generic type variable [`ErrorId`](get.md#erroridextendsid) or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is the [`Error`](broken-reference) instance of the given [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { Errors } from '@angular-package/error';

// Define general errors.
const generalErrors = new Errors('EG: 4332', 'EG: 4331', 'EG: 4330');

// Set the `Error` objects under the given identification numbers.
generalErrors
  .set(
    'Bad parameter type, detected number',
    'Provide proper type, the `string`',
    'EG: 4330'
  )
  .set('Detected numbers', 'Provide only letters', 'EG: 4331');

// Returns the Error<"EG: 4330">.
generalErrors.get('EG: 4330');
```
