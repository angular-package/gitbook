---
description: The `TypeError` object constructor
---

# Constructor

## `TypeError()`

Creates a [`TypeError`](broken-reference) instance that represents type error with the [message](../commonerror/accessors/get-message.md) built of the given described [problem](v-constructor.md#problem-string) and its [solution](v-constructor.md#fix-string), optional [type](v-constructor.md#type-type), and an explicit [identification](v-constructor.md#id-id) on the supplied or stored error message [template](v-constructor.md#template-string-typeerror.template).

{% code title="type-error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  type?: Type,
  template = TypeError.template
) {
  super(problem, fix, id, template, { type });
  this.#type = type;
}
```
{% endcode %}

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the [problem](../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](v-constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

Optional unique [identification](../getting-started/basic-concepts.md#identification) to the given [`problem`](v-constructor.md#problem-string) of generic type variable [`Id`](generic-type-variables.md#wrap-opening).

#### `type?:`[<mark style="color:green;">`Type`</mark>](generic-type-variables.md#wrap-opening-1)

The optional type of generic type variable [`Type`](generic-type-variables.md#wrap-opening-1) that causes an error to be thrown(or not thrown).

#### `template:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)`=`<mark style="color:green;">`TypeError`</mark>`.template`

Optional template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../commonerror/properties/static-template.md#problem), [`{fix}`](../commonerror/properties/static-template.md#fix) and optional [`{id}`](../commonerror/properties/static-template.md#id), [`{max}`](../commonerror/properties/static-template.md#max), [`{min}`](../commonerror/properties/static-template.md#min), [`{type}`](../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property [`TypeError.template`](properties/static-template.md).

## Example usage

```typescript
// Example usage.
import { TypeError } from '@angular-package/error';

// Returns
// TypeError: Problem(TE:201): Wrong type => Fix: The type of `age` parameter must be of the string
new TypeError('Wrong type', 'Change the type', '(TE:201)', 'string');
```