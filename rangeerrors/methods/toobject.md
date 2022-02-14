---
description: The method returns the JSON object of set errors
---

# toObject()

## `RangeErrors.prototype.toObject()`

The method returns the [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/JSON) object of set errors, where the key is a [unique identification](../../getting-started/basic-concepts.md#unique-identification).

{% code title="range-errors.class.ts" %}
```typescript
public toObject(): { [Key in Id]: RangeError<Id> } {
  return Object.fromEntries(this.errors.entries()) as any;
}
```
{% endcode %}

### Return type

#### `{ [`<mark style="color:green;">`Key`</mark>`in`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#rangeerrors-less-than-id-greater-than)`]:` [<mark style="color:green;">`RangeError`</mark>](broken-reference)`<`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#rangeerrors-less-than-id-greater-than)`> }`

The **return type** is an object of the [`RangeError`](broken-reference) objects in the keys of generic type variable [`Id`](../generic-type-variables.md#rangeerrors-less-than-id-greater-than).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors.

## Example usage

```typescript
// Example usage.
import { RangeErrors } from '@angular-package/error';


```
