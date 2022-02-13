# delete()

## `CommonErrors.prototype.delete()`

Deletes the error of a specified [`id`](delete.md#id-errorid) from the object.&#x20;

{% code title="common-errors.class.ts" %}
```typescript
public delete<ErrorId extends Id>(id: ErrorId): this {
  this.#errors.delete(id);
  return this;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../v-generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../v-generic-type-variables.md#wrap-opening) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../v-generic-type-variables.md#wrap-opening) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](delete.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification of a generic type variable [`ErrorId`](delete.md#erroridextendsid) to remove the error from the object.

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

// Returns Map(2)
generalErrors.errors;

// Deletes the error of the `EG: 4330` identification number.
generalErrors.delete('EG: 4330');

// Returns Map(1)
generalErrors.errors;
```
