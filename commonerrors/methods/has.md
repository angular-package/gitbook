---
description: Checks whether the error of the given id exists in a specified object
---

# has()

## `CommonErrors.prototype.has()`

The `has()` method checks whether the error of the given [`id`](has.md#id-errorid) exists in a specified object.

{% code title="common-errors.class.ts" %}
```typescript
public has<ErrorId extends Id>(id: ErrorId): boolean {
  return this.#errors.has(id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../generic-type-variables.md#commonerrors-less-than-id-greater-than) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../generic-type-variables.md#commonerrors-less-than-id-greater-than) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](has.md#erroridextendsid)<mark style="color:green;">``</mark>

The error identification number of generic type variable [`ErrorId`](has.md#erroridextendsid) to test for the presence of the error in the object.

### Return type

#### <mark style="color:green;">`this`</mark>

## Example usage

```typescript
// Example usage.
import { CommonErrors } from '@angular-package/error';

// Define new `TestClass` to add error to the map storage.
export class TestClass<Id extends string> extends CommonErrors<Id> {
  public get errors(): Map<Id, any> {
    return super.errors;
  }
  public set<ErrorId extends Id>(
    problem: string,
    fix: string,
    id: ErrorId
  ): this {
    this.errors.set(id, new Error(problem, fix, id));
    return this;
  }
}

// Initialize the `TestClass`.
const generalErrors = new TestClass('EG: 4332', 'EG: 4331', 'EG: 4330');

// Set the errors.
generalErrors
  .set(
    'Bad parameter type, detected number',
    'Provide proper type, the `string`',
    'EG: 4330'
  )
  .set('Detected numbers', 'Provide only letters', 'EG: 4331');

// Returns `true`.
generalErrors.has('EG: 4330');

// Returns `false`.
generalErrors.has('EG: 4332');
```
