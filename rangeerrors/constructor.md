---
description: The `RangeErrors` constructor
---

# Constructor

## `RangeErrors()`

Creates the [`RangeErrors`](broken-reference) instance of [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the [`RangeError`](broken-reference) objects are stored.

{% code title="range-errors.class.ts" %}
```typescript
constructor(...id: Id[]) {
  super(...id);
}
```
{% endcode %}

### Parameters

#### `...id:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#wrap-opening)`[]`

A [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) of generic type variable [`Id`](generic-type-variables.md#wrap-opening) indicates [unique identification](../getting-started/basic-concepts.md#unique-identification) numbers under which the [`RangeError`](broken-reference) objects are stored.

## Example usage

```typescript
// Example usage.
import { RangeErrors } from '@angular-package/error';

// Returns RangeErrors {}
new RangeErrors('RE: 4332', 'RE: 4331', 'RE: 4330');

// Returns RangeErrors {}
new RangeErrors('RV: 332', 'RV: 331', 'RV: 330');
```
