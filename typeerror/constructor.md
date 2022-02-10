---
description: The `TypeError` object constructor
---

# Constructor

## `TypeError()`

Creates a [`TypeError`](broken-reference) instance that represents type error with the [message](../commonerror/accessors/get-message.md) built of the given described [problem](constructor.md#problem-string) and its [solution](constructor.md#fix-string), optional [type](constructor.md#type-string), and an explicit [identification](constructor.md#id-id) on the supplied or stored error message [template](constructor.md#template-string-typeerror.template).

{% code title="type-error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  type?: string,
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

A solution to the given [`problem`](constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md)<mark style="color:green;">``</mark>

Optional unique [identification](../getting-started/basic-concepts.md#identification) to the given [`problem`](constructor.md#problem-string) of generic type variable [`Id`](generic-type-variables.md).

#### `type?:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

The optional type that causes an error to be thrown(or not thrown).

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
