---
description: A template of the error message
---

# static template

## `TypeError.template`

A template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix) and optional [`{id}`](../../commonerror/properties/static-template.md#id), [`{max}`](../../commonerror/properties/static-template.md#max), [`{min}`](../../commonerror/properties/static-template.md#min), [`{type}`](../../commonerror/properties/static-template.md#type) tags.

By default, it's set to `Problem{id}: {problem} => Fix: {fix} must be of the {type}`.

{% code title="type-error.class.ts" %}
```typescript
public static template = `Problem{id}: {problem} => Fix: {fix} must be of the {type}`;
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { TypeError } from '@angular-package/error'; 

// Change the template.
TypeError.template = `Problem({id}): {problem} => Fix: {fix}`;

// Returns
// TypeError: Problem(AE:427): The `age` parameter is wrong. => Fix: Provided `age` must be different type. 
new RangeError(
  'The `age` parameter is wrong.', // Problem
  'Provided `age` must be different type. ', // Fix
  'AE:427', // Identification
  'string',  // Type
);
```
