---
description: Defines the `ValidationError` instance
---

# static define()

## `ValidationError.define()`

Defines the [`ValidationError`](broken-reference) instance with the [message](../../commonerror/accessors/get-message.md) built of the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id) on the supplied or stored [`template`](static-define.md#template-validationerror.template).

{% code title="validation-error.class.ts" %}
```typescript
public static define<Id extends string>(
  problem: string,
  fix: string,
  id?: Id,
  template = ValidationError.template
): ValidationError<Id> {
  return new this(problem, fix, id, template);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-define.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of a new [`ValidationError`](broken-reference) instance.

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the [problem](../../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](static-define.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](static-define.md#idextendsstring)<mark style="color:green;">``</mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) to the given [`problem`](static-define.md#problem-string) of generic type variable [`Id`](static-define.md#idextendsstring).

#### `template =`<mark style="color:green;">`ValidationError`</mark>`.template`

A template of error message with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix) and optional [`{id}`](../../commonerror/properties/static-template.md#id) tags. By default, the value is equal to the static property `ValidationError.template`.

### Return type

#### `ValidationError<`[<mark style="color:green;">`Id`</mark>](static-define.md#idextendsstring)`>`

The **return type** is the [`ValidationError`](broken-reference) object that takes generic type variable [`Id`](static-define.md#idextendsstring).

### Returns

The **return value** is a new instance of the [`ValidationError`](broken-reference) with the [message](../../commonerror/accessors/get-message.md) built from the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id) on the given or stored [`template`](static-define.md#template-validationerror.template).

## Example usage

```typescript
// Example usage.
import { ValidationError } from '@angular-package/error';

// Returns
// ValidationError: Problem(TE:201): The parameter age is not filled => Fix: Fill the age parameter
ValidationError.define('The parameter age is not filled', 'Fill the age parameter', '(TE:201)');
```
