# isAllowedId()

## `CommonErrors.prototype.isAllowedId()`

Checks whether the given [identification](../../getting-started/basic-concepts.md#unique-identification) number was provided in the [constructor](../v-constructor.md).

{% code title="common-errors.class.ts" %}
```typescript
protected isAllowedId<ErrorId extends Id>(id: ErrorId): boolean {
  return this.#id ? this.#id.has(id) : false;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../v-generic-type-variables.md#commonerrors-less-than-id-greater-than)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../v-generic-type-variables.md#commonerrors-less-than-id-greater-than) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../v-generic-type-variables.md#commonerrors-less-than-id-greater-than) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](isallowedid.md#erroridextendsid)<mark style="color:green;">``</mark>

The error identification number of generic type variable [`ErrorId`](isallowedid.md#erroridextendsid) to test for its presence in the object.

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
    // <--- Use the isAllowedId() here ----------------
    if (super.isAllowedId(id)) {
      this.errors.set(id, new Error(problem, fix, id));
    }
    // <-----------------------------------------------
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
    'EG: 3000' as any // <--- Wrong ID
  )
  .set(
    'Detected numbers',
    'Provide only letters',
    'EG: 4335' as any // <--- Wrong ID
  );

// Returns Map(0) {size: 0}
generalErrors.errors;

  // Returns `false`.
generalErrors.has('EG: 3000' as any);

// Returns `false`.
generalErrors.has('EG: 4335' as any);
```
