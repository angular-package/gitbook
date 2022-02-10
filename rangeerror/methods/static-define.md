---
description: Defines the `RangeError` instance.
---

# static define()

## `RangeError.define()`

Defines the [`RangeError`](broken-reference) instance with the [message](../../commonerror/accessors/get-message.md) built from the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id), [`max`](static-define.md#max-number), [`min`](static-define.md#min-number) on the given or stored [`template`](static-define.md#template-rangeerror.template).

{% code title="range-error.class.ts" %}
```typescript
public static define<
  Id extends string,
  Min extends number | undefined = undefined,
  Max extends number | undefined = undefined
>(
  problem: string,
  fix: string,
  id?: Id,
  min?: Min,
  max?: Max,
  template = RangeError.template
): RangeError<Id, Min, Max> {
  return new this(problem, fix, id, min, max, template);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-define.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of a new [`RangeError`](broken-reference) instance.

#### <mark style="color:green;">`Min`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)`=`<mark style="color:green;">`undefined`</mark>



#### <mark style="color:green;">`Max`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`<mark style="color:green;">`undefined`</mark>`=`<mark style="color:green;">`undefined`</mark>



### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the [problem](../../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](static-define.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](../../error/generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) to the given [`problem`](static-define.md#problem-string) of generic type variable [`Id`](static-define.md#id-extends-string).

#### `min?:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;">``</mark>

The optional minimum range of a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type that causes an error to be thrown(or not thrown).

#### `max?:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;">``</mark>

The optional maximum range of a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type that causes an error to be thrown(or not thrown).

#### `template =`<mark style="color:green;">`RangeError`</mark>`.template`

A template of error message with the replaceable [`{problem}`](../../commonerror/properties/static-template.md#problem), [`{fix}`](../../commonerror/properties/static-template.md#fix) and optional [`{id}`](../../commonerror/properties/static-template.md#id), [`{max}`](../../commonerror/properties/static-template.md#max), [`{min}`](../../commonerror/properties/static-template.md#min) and [`{type}`](../../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property [`RangeError.template`](../properties/static-template.md).

### Return type

#### `RangeError<`[<mark style="color:green;">`Id`</mark>](static-define.md#id-extends-string)`>`

The **return type** is the [`RangeError`](broken-reference) object that takes generic type variable [`Id`](static-define.md#id-extends-string).

### Returns

The **return value** is a new instance of the [`RangeError`](broken-reference) with the [message](../../commonerror/accessors/get-message.md) built from the given required [`problem`](static-define.md#problem-string), [`fix`](static-define.md#fix-string) and optional [`id`](static-define.md#id-id), [`min`](static-define.md#min-number), [`max`](static-define.md#max-number) on the given or stored [`template`](static-define.md#template-rangeerror.template).

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Returns "RangeError: ProblemTE:201: Wrong age, must be between 9 and 27 => Fix: Change the value".
RangeError.define('Wrong age,', 'Change the value', 'TE:201', 9, 27);
```
