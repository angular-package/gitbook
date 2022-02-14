---
description: The `CommonErrors` constructor
---

# Constructor

## `CommonErrors()`

Creates an instance of the errors storage with [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers.

{% code title="common-errors.class.ts" %}
```typescript
constructor(...id: Id[]) {
  Array.isArray(id) && (this.#id = new Set(id));
}
```
{% endcode %}

### Parameters

#### `...id:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#commonerrors-less-than-id-greater-than)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of generic type variable [`Id`](generic-type-variables.md#wrap-opening) indicates [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the errors are stored in the object.

## Example usage

```typescript
// Example usage.
import { CommonErrors } from '@angular-package/error';


```
