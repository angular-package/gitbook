# throw()

## `CommonErrors.prototype.throw()`

Throws an error of the given [`id`](throw.md#id-errorid) if the unique id was provided in the [constructor](../v-constructor.md).

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

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../v-generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../v-generic-type-variables.md#wrap-opening) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../v-generic-type-variables.md#wrap-opening) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](throw.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification of a generic type variable [`ErrorId`](throw.md#erroridextendsid) to remove the error from the object.

### Return type

#### <mark style="color:green;">`this`</mark>

## Example usage

```typescript
// Example usage.
import { } from '@angular-package/error';


```
