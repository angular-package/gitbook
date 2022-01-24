# StringOfLength

## `StringOfLength<Min, Max, Type>`

A [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type or an instance of [`String`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) of length between a specified range takes generic type variable [`Min`](stringoflength.md#minextendsnumber) and [`Max`](stringoflength.md#max-extends-number) constrained by [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type as length, and takes generic type variable [`Type`](stringoflength.md#typeextendsanystring-string) constrained by generic type [`AnyString`](anystring.md) as the type.

{% code title="string-of-length.type.ts" %}
```typescript
type StringOfLength<
  Min extends number,
  Max extends number,
  Type extends AnyString = string
> = Type & MinMax<Min, Max>;
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Min`</mark>`extends`<mark style="color:green;">`number`</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type indicates the **minimum** length of the generic type variable [`Type`](stringoflength.md#typeextendsanystring-string).

#### <mark style="color:green;">`Max`</mark>`extends`<mark style="color:green;">`number`</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type indicates the **maximum** length of the generic type variable [`Type`](stringoflength.md#typeextendsanystring-string).

#### <mark style="color:green;">`Type`</mark>`extends`<mark style="color:green;">`AnyString`</mark>`=`<mark style="color:green;">`string`</mark>

A generic type variable `Type` constrained by generic type [`AnyString`](anystring.md) indicates [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type.
