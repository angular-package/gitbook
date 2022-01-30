# NumberBetween

## `NumberBetween<Min, Max, Type>`

A [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type or an instance of [`Number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) between a specified range takes generic type variable [`Min`](numberbetween.md#minextendsnumber) and [`Max`](numberbetween.md#maxextendsnumber) constrained by [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type as range, and takes generic type variable [`Type`](numberbetween.md#typeextendsanynumber-number) constrained by generic type [`AnyNumber`](anynumber.md) as the type.

{% code title="number-between.type.ts" %}
```typescript
type NumberBetween<
  Min extends number,
  Max extends number,
  Type extends AnyNumber = number
> = Type & MinMax<Min, Max>;
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/type/number-between.type.ts" %}

### Generic type variables

#### <mark style="color:green;">`Min`</mark>`extends`<mark style="color:green;">`number`</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type indicates the **minimum** range __ of the generic type variable [`Type`](numberbetween.md#typeextendsanynumber-number).

#### <mark style="color:green;">`Max`</mark>`extends`<mark style="color:green;">`number`</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type indicates the **maximum** range of the generic type variable [`Type`](numberbetween.md#typeextendsanynumber-number).

#### <mark style="color:green;">`Type`</mark>`extends`<mark style="color:green;">`AnyNumber`</mark>`=`<mark style="color:green;">`number`</mark>

A generic type variable `Type` constrained by generic type [`AnyNumber`](anynumber.md) indicates [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type.
