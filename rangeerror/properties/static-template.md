---
description: A template of the error message
---

# static template

## `RangeError.template`

A template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix) and optional [`{id}`](../../commonerror/properties/static-template.md#id), [`{max}`](../../commonerror/properties/static-template.md#max), [`{min}`](../../commonerror/properties/static-template.md#min) tags.

By default, it's set to `Problem{id}: {problem} => Fix: {fix} between {min} and {max}`.

{% code title="range-error.class.ts" %}
```typescript
public static template = `Problem{id}: {problem} must be between {min} and {max} => Fix: {fix}`;
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error'; 

// Change the template.
RangeError.template = `Problem({id}): {problem} => Fix: {fix}`;

// Returns
// RangeError: Problem((AE:427)): The `age` parameter is too big, got 455 => Fix: Set the `age` parameter of the `setAge()` method
new RangeError(
  'The `age` parameter is too big, got 455', // Problem
  'Set the `age` parameter of the `setAge()` method', // Fix
  '(AE:427)', // Identification
  9,  // Minimum
  27 // Maximum range
);
```
