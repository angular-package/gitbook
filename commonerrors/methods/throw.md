# throw()

## `CommonErrors.prototype.throw()`

Deletes the error of a specified `id` from the object

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

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](throw.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification of a generic type variable [`ErrorId`](throw.md#erroridextendsid) to remove the error from the object.

## Example usage

