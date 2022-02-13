---
description: Sets the `TypeError` object under the given `id`
---

# set()

## `TypeErrors.prototype.set()`

Sets the [`TypeError`](broken-reference) object with the message built from the given required [`problem`](set.md#problem-string), [`fix`](set.md#fix-string), [`id`](set.md#id-errorid) and optional [`type`](set.md#type-string) on the given or stored [`template`](set.md#template-errors.template) under the given [`id`](set.md#id-errorid).

{% code title="type-errors.class.ts" %}
```typescript
public set<ErrorId extends Id>(
  problem: string,
  fix: string,
  id: ErrorId,
  type?: string,
  template = TypeErrors.template
): this {
  this.isAllowedId(id) &&
    this.errors.set(id, new TypeError(problem, fix, id, type, template));
  return this;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../../rangeerrors/generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../../rangeerrors/generic-type-variables.md#wrap-opening) of the [`TypeErrors`](broken-reference) object indicates the type picked from the [`Id`](../../rangeerrors/generic-type-variables.md#wrap-opening) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the problem of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](set.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](set.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification to the given [`problem`](set.md#problem-string) of generic type variable [`ErrorId`](set.md#erroridextendsid).

#### `type?:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

The optional type of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type that causes an error to be thrown(or not thrown).

#### `template =`<mark style="color:green;">`TypeErrors`</mark>`.template`

A template of error message with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix),[`{id}`](../../commonerror/properties/static-template.md#id), and optional [`{type}`](../../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property `TypeErrors.template`.

### Return type

#### <mark style="color:green;">`this`</mark>

## Example usage

```typescript
// Example usage.
import { TypeErrors } from '@angular-package/error';

// Define type errors.
const typeErrors = new RangeErrors('RE: 4332', 'RE: 4331', 'RE: 4330');

// Set the `TypeErrors` objects under the given identification numbers.
typeErrors
  .set(
    'Age is 99',
    'Age must be',
    'RE: 4330',
    9,
    27
  )
  .set('Detected numbers', 'Provide only letters', 'RE: 4331');
```
