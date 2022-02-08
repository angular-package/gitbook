# static template

## `RangeError.template`

A template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../../commonerror/constructor.md#problem), [`{fix}`](../../commonerror/constructor.md#fix) and optional [`{id}`](../../commonerror/properties/static-template.md#id), [`{max}`](../../commonerror/properties/static-template.md#max), [`{min}`](../../commonerror/properties/static-template.md#min), [`{type}`](../../commonerror/properties/static-template.md#type) tags.

By default, it's set to `Problem{id}: {problem} must be between {min} and {max} => Fix: {fix}`.

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
// Error: Problem(AE:427): The `age` parameter is wrong. => Fix: Provided `age`
// must be different type.
new RangeError(
  'The `age` parameter is wrong.', // Problem
  'Provided `age` must be different type. ', // Fix
  'AE:427', // Identification
  9,  // Minimum
  27 // Maximum range
);
```
