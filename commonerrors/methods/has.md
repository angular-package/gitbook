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

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../v-generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../v-generic-type-variables.md#wrap-opening) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../v-generic-type-variables.md#wrap-opening) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](has.md#erroridextendsid)<mark style="color:green;">``</mark>

The error identification number of generic type variable [`ErrorId`](has.md#erroridextendsid) to test for the presence of the error in the object.

## Example usage

```typescript
// Example usage.
import { } from '@angular-package/error';


```

