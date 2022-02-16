---
description: A template of the error message of string type with the replaceable tags
---

# static template

## `CommonError.template`

A template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../constructor.md#problem), [`{fix}`](../constructor.md#fix) and optional [`{id}`](static-template.md#id), [`{link}`](static-template.md#link), [`{max}`](static-template.md#max), [`{min}`](static-template.md#min), [`{type}`](static-template.md#type) tags.

{% hint style="info" %}
By default, it's set to:

`Problem{id}: {problem} => Fix: {fix}`.
{% endhint %}

{% code title="common-error.class.ts" %}
```typescript
public static template = `Problem{id}: {problem} => Fix: {fix}`;
```
{% endcode %}

### Tags

Replaceable tags on the [`template`](static-template.md#template-string-commonerror.template).

#### `{fix}`

Replaceable by the given required [`fix`](../constructor.md#fix-string) parameter.

#### `{id}`

Replaceable by the given [`id`](../constructor.md#id-id) parameter.

#### `{link}`

Replaceable by the property `link` of the given [`additional`](../constructor.md#additional-min-number-max-number-type-string) parameter.

#### `{max}`

Replaceable by the property `max` of the given [`additional`](../constructor.md#additional-min-number-max-number-type-string) parameter.

#### `{min}`

Replaceable by the property `min` of the given [`additional`](../constructor.md#additional-min-number-max-number-type-string) parameter.

#### `{problem}`

Replaceable by the given required [`problem`](../constructor.md#problem-string) parameter.

#### `{type}`

Replaceable by the property `type` of the given [`additional`](../constructor.md#additional-min-number-max-number-type-string) parameter.

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

// Change the template.
CommonError.template = `Problem({id}): {problem} => Fix: {fix}`;

// Extend the `CommonError` class.
class TestError<Id extends string> extends CommonError<Id> {}

// Returns
// Error: Problem(AE:427): The `age` parameter is wrong. => Fix: Provided `age`
// must be different type.
new TestError(
  'The `age` parameter is wrong.', // Problem
  'Provided `age` must be different type. ', // Fix
  'AE:427' // Identification
);
```
