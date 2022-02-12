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

#### <mark style="color:green;">`ErrorId`</mark>`extends`<mark style="color:green;">`Id`</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../v-generic-type-variables.md#wrap-opening) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../v-generic-type-variables.md#wrap-opening) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](delete.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification of a generic type variable [`ErrorId`](delete.md#erroridextendsid) to remove the error from the object.

## Example usage

```typescript
// Example usage.

```
