---
description: The method returns the JSON object of set errors
---

# toObject()

## `toObject()`

The method returns the [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/JSON) object of set errors, where the key is a unique identification.

{% code title="errors.class.ts" %}
```typescript
public toObject(): { [Key in Id]: Error<Id> } {
  return Object.fromEntries(this.errors.entries()) as any;
}
```
{% endcode %}

### Return type

#### `{ [`<mark style="color:green;">`Key`</mark>`in`<mark style="color:green;">`Id`</mark>`]: Error<`<mark style="color:green;">`Id`</mark>`> }`

The **return type** is an object of the [`Error`](broken-reference) objects in the keys of generic type variable [`Id`](../generic-type-variables.md#wrap-opening).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors.

## Example usage

```typescript
// Example usage.
import { Errors } from '@angular-package/error';

```
