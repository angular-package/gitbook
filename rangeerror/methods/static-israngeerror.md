---
description: Checks whether the value of any type is an instance of `RangeError`.
---

# static isRangeError()

## `RangeError.isRangeError()`

Checks whether the [`value`](static-israngeerror.md#value-any) of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type is an instance of [`RangeError`](broken-reference) of any or the given [minimum](static-israngeerror.md#min-number)/[maximum](static-israngeerror.md#max-number) range and [identification](static-israngeerror.md#id-id).

{% code title="range-error.class.ts" %}
```typescript
public static isRangeError<
  Id extends string,
  Min extends number | undefined = undefined,
  Max extends number | undefined = undefined
>(
  value: any,
  id?: Id,
  min?: Min,
  max?: Max
): value is RangeError<Id, Min, Max> {
  return (
    super.isError(value, id) &&
    (typeof min === 'number' ? (value as any).min === min : true) &&
    (typeof max === 'number' ? (value as any).max === max : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)``

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-israngeerror.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of the [`RangeError`](broken-reference) via [return type](static-israngeerror.md#return-type).

#### <mark style="color:green;">`Min`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)`=`<mark style="color:green;">`undefined`</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) and [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined), by default of the value equal to [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) indicates the captured type of the supplied [`min`](static-israngeerror.md#min-min) via the [return type](static-israngeerror.md#return-type).

#### <mark style="color:green;">`Max`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`<mark style="color:green;">`undefined`</mark>`=`<mark style="color:green;">`undefined`</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) and [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined), by default of the value equal to [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) indicates the captured type of the supplied [`max`](static-israngeerror.md#max-max) via the [return type](static-israngeerror.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against the [`RangeError`](broken-reference) instance.

#### `id?:`[<mark style="color:green;">`Id`</mark>](static-israngeerror.md#idextendsstring)<mark style="color:green;">``</mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) of generic type variable [`Id`](static-israngeerror.md#idextendsstring) to check whether the given [`value`](static-israngeerror.md#value-any) contains.

#### `min?:`[<mark style="color:green;">`Min`</mark>](static-israngeerror.md#minextendsnumber-or-undefined-undefined)

The optional minimum range of generic type variable [`Min`](static-israngeerror.md#minextendsnumber-or-undefined-undefined) that causes an error to be thrown(or not thrown) to check whether the given [`value`](static-israngeerror.md#value-any) contains.

#### `max?:`[<mark style="color:green;">`Max`</mark>](static-israngeerror.md#maxextendsnumber-or-undefined-undefined)

The optional minimum range of generic type variable [`Max`](static-israngeerror.md#maxextendsnumber-or-undefined-undefined) that causes an error to be thrown(or not thrown) to check whether the given [`value`](static-israngeerror.md#value-any) contains.

### Return type

#### `value is RangeError<`[<mark style="color:green;">`Id`</mark>](static-israngeerror.md#idextendsstring)`,`[<mark style="color:green;">`Min`</mark>](static-israngeerror.md#minextendsnumber-or-undefined-undefined)`,`[<mark style="color:green;">`Max`</mark>](static-israngeerror.md#maxextendsnumber-or-undefined-undefined)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-israngeerror.md#value-any) is the [`RangeError`](broken-reference) object that takes the generic type variable [`Id`](static-israngeerror.md#idextendsstring) as identification, [`Min`](static-israngeerror.md#minextendsnumber-or-undefined-undefined) as minimum range and [`Max`](static-israngeerror.md#maxextendsnumber-or-undefined-undefined) as maximum range.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](static-israngeerror.md#value-any) is an instance of [`RangeError`](broken-reference) of any or the given optional [`min`](static-israngeerror.md#min-min), [`max`](static-israngeerror.md#max-max) and [`id`](static-israngeerror.md#id-id) properties.

## Example usage

```typescript
// Example usage.
import { RangeError } from '@angular-package/error';

// Define error.
const err = RangeError.define('Wrong type', 'Change the type', 'TE:201', 9, 27);

// Returns true.
RangeError.isRangeError(err);

// Returns true.
RangeError.isRangeError(err, 'TE:201');

// Returns false.
RangeError.isRangeError(err, 'TE:202', 9);

// Returns false.
RangeError.isRangeError(err, 'TE:202', 9, 27);

// Returns false.
RangeError.isRangeError(new Array());
```
