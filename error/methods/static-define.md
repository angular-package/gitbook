---
description: Defines the `Error` instance.
---

# static define()

## `Error.define()`

Defines the `Error` instance with the message built of the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id) on the [`template`](static-define.md#template-error.template).

{% code title="error.class.ts" %}
```typescript
public static define<Id extends string>(
  problem: string,
  fix: string,
  id?: Id,
  template = Error.template
): Error<Id> {
  return new this(problem, fix, id, template);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">Id</mark> extends [<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-define.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of a new [`Error`](broken-reference) instance.

### Parameters

#### problem: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

Description of the [problem](../../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### fix: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

A solution to the given [`problem`](static-define.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### id?: [<mark style="color:green;">Id</mark>](../generic-type-variables.md#wrap-opening)<mark style="color:green;"></mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) to the given [`problem`](static-define.md#problem-string) of generic type variable [`Id`](../generic-type-variables.md#wrap-opening).

#### template = <mark style="color:green;">Error</mark>.template

A template of error message with the replaceable [`{problem}`](static-define.md#problem), [`{fix}`](static-define.md#fix) and optional [`{id}`](static-define.md#id), [`{max}`](static-define.md#max), [`{min}`](static-define.md#min) and [`{type}`](static-define.md#type) tags. By default, the value is equal to the static property [`template`](../../commonerror/properties/static-template.md).

### Return type

#### Error<<mark style="color:green;">Id</mark>>

The **return type** is the [`Error`](broken-reference) object that takes generic type variable [`Id`](static-define.md#id-extends-string).

### Returns

The **return value** is a new instance of the [`Error`](broken-reference) with the message built from the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id) on the [`template`](static-define.md#template-error.template).

## Example usage

```typescript
// Example usage.
import { Error } from '@angular-package/error';

// Returns "Error: ProblemTE:201: Wrong type => Fix: Change the type".
Error.define('Wrong type', 'Change the type', 'TE:201');
```
