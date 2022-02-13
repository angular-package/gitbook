---
description: >-
  Creates the `Errors` instance of unique identification numbers under which the
  `Error` objects are stored
---

# Constructor

## `Errors()`

Creates the [`Errors`](broken-reference) instance of unique identification numbers under which the [`Error`](broken-reference) objects are stored.

{% code title="errors.class.ts" %}
```typescript
constructor(...id: Id[]) {
  super(...id);
}
```
{% endcode %}

### Parameters

#### `...id:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#wrap-opening)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of generic type variable [`Id`](generic-type-variables.md#wrap-opening) indicates [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the errors are stored in the object.

## Example usage

```typescript
// Example usage.
import { Errors } from '@angular-package/error';

// Returns Error {}
new Errors('EG: 4332', 'EG: 4331', 'EG: 4330');

// Returns Error {}
new Errors('EV: 332', 'EV: 331', 'EV: 330');
```
