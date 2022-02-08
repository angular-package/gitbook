---
description: Checks whether the value of any type is an instance of `TypeError`
---

# static isTypeError()

## `TypeError.isTypeError()`

Checks whether the [`value`](static-istypeerror.md#value-any) of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type is an instance of [`TypeError`](broken-reference) of any or the given [`type`](static-istypeerror.md#type-string) and [identification](static-istypeerror.md#id-id).

{% code title="type-error.class.ts" %}
```typescript
public static isTypeError<Id extends string>(
  value: any,
  id?: Id,
  type?: string,
): value is TypeError<Id> {
  return (
    super.isError(value, id) &&
    (typeof type === 'string' ? (value as any).type === type : true)
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">Id</mark> extends [<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](static-istypeerror.md#id-id) indicates the [identification](../../getting-started/basic-concepts.md#identification) type of the [`TypeError`](broken-reference) via [return type](static-istypeerror.md#return-type).

### Parameters

#### value: [<mark style="color:green;">any</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;"></mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against the [`TypeError`](broken-reference) instance.

#### id?: [<mark style="color:green;">Id</mark>](../../error/generic-type-variables.md#wrap-opening)<mark style="color:green;"></mark>

Optional unique [identification](../../getting-started/basic-concepts.md#identification) of generic type variable [`Id`](static-istypeerror.md#id-extends-string) to check whether the given [`value`](static-istypeerror.md#value-any) contains.

#### type?: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

The optional type that causes an error to be thrown(or not thrown) to check whether the given [`value`](static-istypeerror.md#value-any) contains.

### Return type

#### value is TypeError<<mark style="color:green;">Id</mark>>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-istypeerror.md#value-any) is the [`TypeError`](broken-reference) object that takes the generic type variable [`Id`](static-istypeerror.md#id-extends-string).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](static-istypeerror.md#value-any) is an instance of [`TypeError`](broken-reference) of any or the given optional [`type`](static-istypeerror.md#type-string) and [`id`](static-istypeerror.md#id-id) properties.

## Example usage

```typescript
// Example usage.
import { TypeError } from '@angular-package/error';

// Define error.
const err = TypeError.define('Wrong type', 'Change the type', 'TE:201', 'string');

// Returns true.
TypeError.isTypeError(err);

// Returns true.
TypeError.isTypeError(err, 'TE:201');

// Returns true.
TypeError.isTypeError(err, 'TE:201', 'string');

// Returns false.
TypeError.isTypeError(err, 'TE:202', 'number');

// Returns false.
TypeError.isTypeError(err, 'TE:202', 'string');

// Returns false.
TypeError.isTypeError(new Array());
```
