---
description: The `TypeError` object constructor
---

# Constructor

## `TypeError()`

Creates the [`Error`](broken-reference) instance with the [message](../commonerror/accessors/get-message.md) built from the given described [`problem`](constructor.md#problem-string) and its [solution](constructor.md#fix-string), optional explicit [identification](constructor.md#id-id) on the given or stored [`template`](constructor.md#template-string-error.template).

Creates a [`TypeError`](broken-reference) instance that represents type error with the [message](../commonerror/accessors/get-message.md) built of the given described [problem](constructor.md#problem-string) and its [solution](constructor.md#fix-string), optional [type](constructor.md#type-string), and an explicit [identification](constructor.md#id-id) on the supplied or stored error message template.

{% code title="error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  template = Error.template
) {
  super(problem, fix, id, template);
}
```
{% endcode %}

### Parameters

#### problem: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

Description of the [problem](../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### fix: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

A solution to the given [`problem`](constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### id?: [<mark style="color:green;">Id</mark>](../commonerror/generic-type-variables.md#wrap-opening)<mark style="color:green;"></mark>

Optional unique [identification](../getting-started/basic-concepts.md#identification) to the given [`problem`](constructor.md#problem-string) of generic type variable [`Id`](../commonerror/generic-type-variables.md#wrap-opening).

#### type?: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

asd

#### template: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) = <mark style="color:green;">TypeError</mark>.template

A template of error message with the replaceable [`{problem}`](../commonerror/properties/static-template.md#problem), [`{fix}`](../commonerror/properties/static-template.md#fix) and optional [`{id}`](../commonerror/properties/static-template.md#id), [`{max}`](../commonerror/properties/static-template.md#max), [`{min}`](../commonerror/properties/static-template.md#min) and [`{type}`](../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property [`template`](../commonerror/properties/static-template.md).

## Example usage

```typescript
// Example usage.
import { TypeError } from '@angular-package/error';

// Returns "Error: ProblemTE:201: Wrong type => Fix: Change the type".
new TypeError('Wrong type', 'Change the type', 'TE:201', 'string');
```
