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

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../v-generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../v-generic-type-variables.md#wrap-opening) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../v-generic-type-variables.md#wrap-opening) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](isallowedid.md#erroridextendsid)<mark style="color:green;">``</mark>

The error identification number of generic type variable [`ErrorId`](isallowedid.md#erroridextendsid) to test for its presence in the object.

### Return type

#### <mark style="color:green;">`this`</mark>

## Example usage

```typescript
// Example usage.
import { } from '@angular-package/error';


```
