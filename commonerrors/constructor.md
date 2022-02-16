---
description: The `CommonErrors` constructor
---

# Constructor

## `CommonErrors()`

Creates an instance of the errors storage with [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers.

{% hint style="info" %}
Identification numbers given in the rest parameter [`id`](constructor.md#...id-id) are used by the instance [`isAllowedId()`](methods/isallowedid.md) method to check the existence of the specific [`id`](constructor.md#...id-id).
{% endhint %}

{% code title="common-errors.class.ts" %}
```typescript
constructor(...id: Id[]) {
  Array.isArray(id) && (this.#id = new Set(id));
}
```
{% endcode %}

### Parameters

#### `...id:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#commonerrors-less-than-id-greater-than)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of generic type variable [`Id`](generic-type-variables.md#commonerrors-less-than-id-greater-than) indicates [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the errors are stored in the object.

## Example usage

```typescript
// Example usage.
import { CommonErrors } from '@angular-package/error';

class CustomErrors<Id extends string> extends CommonErrors<Id> {
  constructor(...id: Id[]) {
    super(...id);
  }
}

// Initialize `CustomErrors` without defined `id`.
// Returns CustomErrors {} of CustomErrors<string>
new CustomErrors();

// Initialize `CustomErrors` with defined `id`.
// Returns CustomErrors {} of CustomErrors<"ERR1" | "ERR2" | "ERR3">
new CustomErrors('ERR1', 'ERR2', 'ERR3');
```
