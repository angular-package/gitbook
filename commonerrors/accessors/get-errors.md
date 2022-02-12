---
description: The get accessor returns the errors of Map type
---

# get errors()

## `CommonErrors.prototype.errors()`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor returns the errors of [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Map) type by returning the [`#errors`](../properties/errors.md) property of a specified object.

{% code title="common-errors.class.ts" %}
```typescript
protected get errors(): Map<Id, any> {
  return this.#errors;
}
```
{% endcode %}

### Return type

#### `Map<`[<mark style="color:green;">`Id`</mark>](../v-generic-type-variables.md#wrap-opening)`,`<mark style="color:green;">`any`</mark>`>`

### Returns

The **return value** is the [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Map) object of errors.
