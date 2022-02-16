---
description: The `ValidationError` constructor
---

# ★ Constructor

## `ValidationError()`

Creates the [`ValidationError`](broken-reference) instance that represents validation error with the [message](../commonerror/accessors/get-message.md) built of the given described [problem](constructor.md#problem-string), its [solution](constructor.md#fix-string), and optional explicit [identification](constructor.md#id-id), on the supplied or stored error message [template](constructor.md#template-string-error.template).

{% code title="validation-error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  template = ValidationError.template
) {
  super(problem, fix, id, template);
}
```
{% endcode %}

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the [problem](../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#validationerror-less-than-id-greater-than)<mark style="color:green;">``</mark>

Optional unique [identification](../getting-started/basic-concepts.md#identification) to the given [`problem`](constructor.md#problem-string) of generic type variable [`Id`](../commonerror/generic-type-variables.md#wrap-opening).

#### `template:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)`=`<mark style="color:green;">`ValidationError`</mark>`.template`

A template of error message with the replaceable [`{problem}`](../commonerror/properties/static-template.md#problem), [`{fix}`](../commonerror/properties/static-template.md#fix) and optional [`{id}`](../commonerror/properties/static-template.md#id) tags. By default, the value is equal to the static property [`template`](../commonerror/properties/static-template.md).

## Example usage

```typescript
// Example usage.
import { ValidationError } from '@angular-package/error';

// Returns
// ValidationError: ProblemTE:201: Wrong type => Fix: Change the type
new ValidationError('Wrong type', 'Change the type', 'TE:201');
```
