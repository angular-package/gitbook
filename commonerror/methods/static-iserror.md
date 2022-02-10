# static isError()

## `CommonError.isError()`

Checks whether the [`value`](static-iserror.md#value-any) of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type is a `this` instance of any or the given [identification](static-iserror.md#id-id).

{% code title="common-error.class.ts" %}
```typescript
protected static isError<Id extends string>(
  value: any,
  id?: Id
): value is CommonError<Id> {
  return typeof value === 'object' && value instanceof this
    ? typeof id === 'string'
      ? value.id === id
      : true
    : false;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) indicates the&#x20;

### Parameters

#### `value:` [<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against the `this` instance.

#### `id?:` [<mark style="color:green;">`Id`</mark>](static-iserror.md#id-extends-string)<mark style="color:green;">``</mark>

Optional identification of generic type variable [`Id`](static-iserror.md#id-extends-string) to check whether the given [`value`](static-iserror.md#value-any) contains.

### Return type

#### `value is`[<mark style="color:green;">`CommonError`</mark>](broken-reference)`<`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#wrap-opening)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating the [`value`](static-iserror.md#value-any) is the [`CommonError`](broken-reference) object that takes generic type variable [`Id`](../generic-type-variables.md#wrap-opening).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the given [`value`](static-iserror.md#value-any) is a `this` instance of any or the given [`id`](static-iserror.md#id-id).

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

class TestError<Id extends string> extends CommonError<Id> {
  public static isError<Id extends string>(
    value: any,
    id?: Id
  ): value is TestError<Id> {
    return super.isError(value, id);
  }
}

const testError = new TestError(
  'Problem accessor.',
  'Fix accessor.',
  '(AE:427)',
  '{problem} {fix} {id}'
);

// Returns "true".
TestError.isError(testError, '(AE:427)');
```
