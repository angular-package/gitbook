---
description: Checks whether the value of any type is an instance of `RangeError`.
---

# static isRangeError()

## `RangeError.isRangeError()`

Checks whether the [`value`](static-israngeerror.md#value-any) of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type is an instance of [`RangeError`](broken-reference) of any or the given [minimum](static-israngeerror.md#min-number)/[maximum](static-israngeerror.md#max-number) range and [identification](static-israngeerror.md#id-id).

{% code title="range-error.class.ts" %}
```typescript
public static isRangeError<Id extends string>(
  value: any,
  id?: Id,
  min?: number,
  max?: number
): value is RangeError<Id> {
  return (
    super.isError(value, id) &&
    (typeof min === 'number' ? (value as any).min === min : true) &&
    (typeof max === 'number' ? (value as any).max === max : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">Id</mark> extends [<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-israngeerror.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of the [`RangeError`](broken-reference) via [return type](static-israngeerror.md#return-type).

### Parameters

#### value: [<mark style="color:green;">any</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;"></mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against the [`RangeError`](broken-reference) instance.

#### id?: [<mark style="color:green;">Id</mark>](../../error/generic-type-variables.md#wrap-opening)<mark style="color:green;"></mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) of generic type variable [`Id`](static-israngeerror.md#id-extends-string) to check whether the given [`value`](static-israngeerror.md#value-any) contains.

#### min?: [<mark style="color:green;">number</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;"></mark>

The optional minimum range of a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type that causes an error to be thrown(or not thrown) to check whether the given [`value`](static-israngeerror.md#value-any) contains.

#### max?: [<mark style="color:green;">number</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)<mark style="color:green;"></mark>

The optional minimum range of a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type that causes an error to be thrown(or not thrown) to check whether the given [`value`](static-israngeerror.md#value-any) contains.

### Return type

#### value is RangeError<<mark style="color:green;">Id</mark>>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-israngeerror.md#value-any) is the [`RangeError`](broken-reference) object that takes the generic type variable [`Id`](static-israngeerror.md#id-extends-string).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](static-israngeerror.md#value-any) is an instance of [`RangeError`](broken-reference) of any or the given optional [`min`](static-israngeerror.md#min-number), [`max`](static-israngeerror.md#max-number) and [`id`](static-israngeerror.md#id-id) properties.

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

