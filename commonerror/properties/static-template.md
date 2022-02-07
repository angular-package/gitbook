---
description: >-
  A template of the error message of string type with the replaceable
  `{problem}`, `{fix}` and optional `{id}`, `{max}`, `{min}`, `{type}` tags.
---

# static template

## `CommonError.template`

A template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../constructor.md#problem), [`{fix}`](../constructor.md#fix) and optional [`{id}`](../constructor.md#id), [`{max}`](../constructor.md#max), [`{min}`](../constructor.md#min), [`{type}`](../constructor.md#type) tags. By default, it's set to `Problem{id}: {problem} => Fix: {fix}`.

{% code title="common-error.class.ts" %}
```typescript
public static template = `Problem{id}: {problem} => Fix: {fix}`;
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error'; 

// Change the template.
CommonError.template = `Problem({id}): {problem} => Fix: {fix}`;

// Extend the `CommonError` class.
class TestError extends CommonError {}

// Returns
// Error: Problem(AE:427): The `age` parameter is wrong. => Fix: Provided `age`
// must be different type. 
new TestError(
  'The `age` parameter is wrong.', // Problem
  'Provided `age` must be different type. ', // Fix
  'AE:427' // Identification
);
```
