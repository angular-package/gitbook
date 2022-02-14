---
description: Defines the `TypeError` instance
---

# static define()

## `TypeError.define()`

Defines the [`TypeError`](broken-reference) instance with the [message](../../commonerror/accessors/get-message.md) built of the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id) and [`type`](static-define.md#type-string) on the given or stored [`template`](static-define.md#template-typeerror.template).

{% code title="type-error.class.ts" %}
```typescript
public static define<
  Id extends string,
  Type extends string | undefined = undefined
>(
  problem: string,
  fix: string,
  id?: Id,
  type?: Type,
  template = TypeError.template
): TypeError<Id, Type> {
  return new this(problem, fix, id, type, template);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)``

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-define.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of a new [`TypeError`](broken-reference) instance.

#### <mark style="color:green;">`Type`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)`=`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) ``&#x20;

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) and [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined), by default of the value equal to [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) indicates the captured type of the supplied [`type`](static-define.md#type-type) of a new [`TypeError`](broken-reference) instance.

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the [problem](../../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](static-define.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](static-define.md#idextendsstring)<mark style="color:green;">``</mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) to the given [`problem`](static-define.md#problem-string) of generic type variable [`Id`](static-define.md#idextendsstring).

#### `type?:`[<mark style="color:green;">`Type`</mark>](static-define.md#typeextendsstring-or-undefined-undefined)<mark style="color:green;">``</mark>

The optional type of generic type variable [`Type`](static-define.md#typeextendsstring-or-undefined-undefined) that causes an error to be thrown(or not thrown).

#### `template =`<mark style="color:green;">`TypeError`</mark>`.template`

A template of error message with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix) and optional [`{id}`](../../commonerror/properties/static-template.md#id), [`{max}`](../../commonerror/properties/static-template.md#max), [`{min}`](../../commonerror/properties/static-template.md#min) and [`{type}`](../../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property [`TypeError.template`](../properties/static-template.md).

### Return type

#### `TypeError<`[<mark style="color:green;">`Id`</mark>](static-define.md#idextendsstring)`,`[<mark style="color:green;">`Type`</mark>](static-define.md#typeextendsstring-or-undefined-undefined)`>`

The **return type** is the [`TypeError`](broken-reference) object that takes generic type variable [`Id`](static-define.md#idextendsstring) as identification and  generic type variable [`Type`](static-define.md#typeextendsstring-or-undefined-undefined) as the type.

### Returns

The **return value** is a new instance of the [`TypeError`](broken-reference) with the [message](../../commonerror/accessors/get-message.md) built from the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id), [`type`](static-define.md#type-type) on the given or stored [`template`](static-define.md#template-typeerror.template).

## Example usage

```typescript
// Example usage.
import { TypeError } from '@angular-package/error';

// Returns
// TypeError: Problem(TE:201): Wrong type => Fix: The parameter age type must be of the string
TypeError.define('Wrong type', 'The parameter age type', '(TE:201)', 'string');
```
