---
description: The `RangeErrors` constructor
---

# Constructor

## `TypeErrors()`

Creates the [`TypeErrors`](broken-reference) instance of [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the [`TypeError`](broken-reference) objects are stored.

{% code title="type-errors.class.ts" %}
```typescript
constructor(...id: Id[]) {
  super(...id);
}
```
{% endcode %}

### Parameters

#### `...id:`[<mark style="color:green;">`Id`</mark>](../rangeerrors/generic-type-variables.md#wrap-opening)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of generic type variable [`Id`](../rangeerrors/generic-type-variables.md#wrap-opening) indicates [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the [`TypeError`](broken-reference) objects are stored.

## Example usage

```typescript
// Example usage.
import { TypeErrors } from '@angular-package/error';

// Returns TypeErrors {}
new TypeErrors('RE: 4332', 'RE: 4331', 'RE: 4330');

// Returns TypeErrors {}
new TypeErrors('RV: 332', 'RV: 331', 'RV: 330');
```
