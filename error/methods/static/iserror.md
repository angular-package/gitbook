# isError()

## `Error.isError()`

Checks whether the value of any type is an instance of `Error` of any or the given identification.

{% code title="error.class.ts" %}
```typescript
public static isError<Id extends string>(
  value: any,
  id?: Id
): value is Error<Id> {
  return super.isError(value, id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">Id</mark> extends [<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided optional [`id`](iserror.md#id-id) indicates the [identification](../../../getting-started/basic-concepts.md#identification) type of a new [`Error`](broken-reference) instance.

### Parameters

#### value: [<mark style="color:green;">any</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;"></mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against the [`Error`](broken-reference) instance.

#### id?: [<mark style="color:green;">Id</mark>](../../generic-type-variables.md#wrap-opening)<mark style="color:green;"></mark>

Optional unique [identification](../../../getting-started/basic-concepts.md#identification) to the given [`problem`](iserror.md#problem-string) of generic type variable [`Id`](../../generic-type-variables.md#wrap-opening).

### Return type

#### value is Error<<mark style="color:green;">Id</mark>>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating the [`value`](iserror.md#value-any) is the `Error` object that takes generic type variable `Id`.

### Returns



## Example usage
