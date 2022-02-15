# throw()

## `CommonErrors.prototype.throw()`

Throws an error of the given [`id`](throw.md#id-errorid) if the unique id was provided in the [constructor](../constructor.md).

{% code title="common-errors.class.ts" %}
```typescript
public throw<ErrorId extends Id>(id: ErrorId): void {
  if (this.isAllowedId(id)) {
    throw this.errors.get(id);
  }
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#commonerrors-less-than-id-greater-than)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../generic-type-variables.md#commonerrors-less-than-id-greater-than) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../generic-type-variables.md#commonerrors-less-than-id-greater-than) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](throw.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification of a generic type variable [`ErrorId`](throw.md#erroridextendsid) to remove the error from the object.

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
  .set(
    'Detected numbers',
    'Provide only letters',
    'EG: 4331'
  );


try {
  // Throw the specified EG: 4330 error.
  generalErrors.throw('EG: 4330');
} catch (e) {
  if (e instanceof Error) {
    e.fix; // Provide proper type, the `string`
    e.message; // ProblemEG: 4330: Bad parameter type, detected number => Fix: Provide proper type, the `string`
    e.name; // Error
    e.problem; // Bad parameter type, detected number
    e.template; // Problem{id}: {problem} => Fix: {fix}
    e.id; // EG: 4330
  }
}
```
