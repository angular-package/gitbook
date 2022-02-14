---
description: The `TypeErrors` constructor
---

# Constructor

## `TypeErrors()`

Creates the [`ValidationErrors`](broken-reference) instance of [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the [`ValidationError`](broken-reference) objects are stored.

{% code title="validation-errors.class.ts" %}
```typescript
constructor(...id: Id[]) {
  super(...id);
}
```
{% endcode %}

### Parameters

#### `...id:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#validationerrors-less-than-id-greater-than)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of generic type variable [`Id`](generic-type-variables.md#validationerrors-less-than-id-greater-than) indicates [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the [`ValidationError`](broken-reference) objects are stored.

## Example usage

```typescript
// Example usage.
import { ValidationErrors } from '@angular-package/error';

// Define validation errors.
new ValidationErrors(
  '(VE: 4332)',
  '(VE: 4331)',
  '(VE: 4330)'
);
```
