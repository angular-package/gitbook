---
description: Sets the `Error` object under the given `id`
---

# set()

## `Errors.prototype.set()`

Sets the [`Error`](broken-reference) object with the message built from the given required [`problem`](set.md#problem-string), [`id`](set.md#id-errorid), [`fix`](set.md#fix-string) on the given or stored [`template`](set.md#template-errors.template) under the given [`id`](set.md#id-errorid).

{% code title="errors.class.ts" %}
```typescript
public set<ErrorId extends Id>(
  problem: string,
  fix: string,
  id: ErrorId,
  template = Errors.template
): this {
  this.isAllowedId(id) &&
    this.errors.set(id, new Error(problem, fix, id, template));
  return this;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../../commonerrors/generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../generic-type-variables.md#wrap-opening) of the [`CommonErrors`](broken-reference) object indicates the type picked from the [`Id`](../generic-type-variables.md#wrap-opening) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the problem of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](set.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](set.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification to the given [`problem`](set.md#problem-string) of generic type variable [`Id`](../generic-type-variables.md#wrap-opening).

#### `template =`<mark style="color:green;">`Errors`</mark>`.template`

A template of error message with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix) and optional [`{id}`](../../commonerror/properties/static-template.md#id), [`{max}`](../../commonerror/properties/static-template.md#max), [`{min}`](../../commonerror/properties/static-template.md#min) and [`{type}`](../../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property [`Errors.template`](../../commonerror/properties/static-template.md#commonerror.template).

### Return type

#### <mark style="color:green;">`this`</mark>

## Example usage

```typescript
// Example usage.
import { Errors } from '@angular-package/error';

// Define general errors.
const generalErrors = new Errors('EG: 4332', 'EG: 4331', 'EG: 4330');

// Set the `Error` objects under the given identification numbers.
generalErrors
  .set(
    'Bad parameter type, detected number',
    'Provide proper type, the `string`',
    'EG: 4330'
  )
  .set('Detected numbers', 'Provide only letters', 'EG: 4331');
```