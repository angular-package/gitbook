---
description: Sets the `RangeError` object under the given `id`
---

# set()

## `RangeErrors.prototype.set()`

Sets the [`RangeError`](broken-reference) object with the message built from the given required [`problem`](set.md#problem-string), [`fix`](set.md#fix-string), [`id`](set.md#id-errorid) and optional [`min`](set.md#min-number), [`max`](set.md#max-number) on the given or stored [`template`](set.md#template-errors.template) under the given [`id`](set.md#id-errorid).

{% code title="range-errors.class.ts" %}
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

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../5-generic-type-variables.md#rangeerrors-less-than-id-greater-than)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../5-generic-type-variables.md#rangeerrors-less-than-id-greater-than) of the [`RangeErrors`](broken-reference) object indicates the type picked from the [`Id`](../5-generic-type-variables.md#rangeerrors-less-than-id-greater-than) and its exact type is useful in picking the specific error from the storage.

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the problem of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](set.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](set.md#erroridextendsid)<mark style="color:green;">``</mark>

The unique identification to the given [`problem`](set.md#problem-string) of generic type variable [`ErrorId`](set.md#erroridextendsid).

#### min?: [<mark style="color:green;">number</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;"></mark>

The optional minimum range of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type that causes an error to be thrown(or not thrown).

#### max?: [<mark style="color:green;">number</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;"></mark>

The optional maximum range of [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type that causes an error to be thrown(or not thrown).

#### `template =`<mark style="color:green;">`RangeErrors`</mark>`.template`

A template of error message with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix),[`{id}`](../../commonerror/properties/static-template.md#id), and optional  [`{max}`](../../commonerror/properties/static-template.md#max), [`{min}`](../../commonerror/properties/static-template.md#min), [`{type}`](../../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property `RangeErrors.template`.

### Return type

#### <mark style="color:green;">`this`</mark>

## Example usage

```typescript
// Example usage.
import { RangeErrors } from '@angular-package/error';

// Define range errors.
const rangeErrors = new RangeErrors('RE: 4332', 'RE: 4331', 'RE: 4330');

// Set the `RangeError` objects under the given identification numbers.
rangeErrors
  .set(
    'Age is 99',
    'Age must be',
    'RE: 4330',
    9,
    27
  )
  .set('Detected numbers', 'Provide only letters', 'RE: 4331');
```
