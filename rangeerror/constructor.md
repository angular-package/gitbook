---
description: The `RangeError` object constructor
---

# Constructor

## `RangeError()`

Creates the [`RangeError`](broken-reference) instance that represents range error with the [message](../commonerror/accessors/get-message.md) built of the given described [`problem`](constructor.md#problem-string) and its [solution](constructor.md#fix-string), optional [`min`](constructor.md#min-number)/[`max`](constructor.md#max-number) range, and an explicit [identification](constructor.md#id-id) on the given or stored error message [template](constructor.md#template-string-rangerror.template).

{% code title="error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  min?: Min,
  max?: Max,
  template = RangeError.template
) {
  super(problem, fix, id, template, { min, max });
  this.#max = max;
  this.#min = min;
}
```
{% endcode %}

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)

Description of the problem of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)

A solution to the given [`problem`](constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than)

Optional unique identification to the given [`problem`](constructor.md#problem-string) of generic type variable [`Id`](generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than).

#### `min?:`[<mark style="color:green;">`Min`</mark>](generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-1)<mark style="color:green;">``</mark>

The optional minimum range of generic type variable [`Min`](generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-1) that causes an error to be thrown(or not thrown).

#### `max?:`[<mark style="color:green;">`Max`</mark>](generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-2)<mark style="color:green;">``</mark>

The optional maximum range of generic type variable [`Max`](generic-type-variables.md#rangeerror-less-than-id-min-max-greater-than-2) that causes an error to be thrown(or not thrown).

#### `template:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)`=`<mark style="color:green;">`RangError`</mark>`.template`

Optional template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../commonerror/properties/static-template.md#problem), [`{fix}`](../commonerror/properties/static-template.md#fix) and optional [`{id}`](../commonerror/properties/static-template.md#id), [`{max}`](../commonerror/properties/static-template.md#max), [`{min}`](../commonerror/properties/static-template.md#min), [`{type}`](../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property [`RangeError.template`](properties/static-template.md).

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Returns
// RangeError: ProblemTE:201: Wrong age, must be between 9 and 27 => Fix: Change the value
RangeError.define('Wrong age,', 'Change the value', 'TE:201', 9, 27);
```
