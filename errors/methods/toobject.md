---
description: The method returns the JSON object of set errors
---

# toObject()

## `Errors.prototype.toObject()`

The method returns the [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/JSON) object of set errors, where the key is a [unique identification](../../getting-started/basic-concepts.md#unique-identification).

{% code title="errors.class.ts" %}
```typescript
public toObject(): { [Key in Id]: Error<Id> } {
  return Object.fromEntries(this.errors.entries()) as any;
}
```
{% endcode %}

### Return type

#### `{ [`<mark style="color:green;">`Key`</mark>`in`[<mark style="color:green;">`Id`</mark>](../3-generic-type-variables.md#errors-less-than-id-greater-than)`]: Error<`[<mark style="color:green;">`Id`</mark>](../3-generic-type-variables.md#errors-less-than-id-greater-than)`> }`

The **return type** is an object of the [`Error`](broken-reference) objects in the keys of generic type variable [`Id`](../3-generic-type-variables.md#errors-less-than-id-greater-than).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors.

## Example usage

```typescript
// Example usage.
import { Errors } from '@angular-package/error';


```
