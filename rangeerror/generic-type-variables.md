---
description: The `RangeError` object generic type variables
---

# Generic type variables

## `RangeError<`<mark style="color:green;background-color:green;">`Id`</mark>`,Min,Max>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`id`](constructor.md#id-id) indicates the [identification](../getting-started/basic-concepts.md#identification) type of a new [`RangeError`](broken-reference) instance.

{% code title="range-error.class.ts" %}
```typescript
class RangeError<
  Id extends string, // <--- Declare generic type variable Id.
  Min extends number | undefined = undefined,
  Max extends number | undefined = undefined
> extends CommonError<Id> {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id, // <--- Capture generic type variable Id.
    min?: Min,
    max?: Max,
    template = RangeError.template
  ) { ... }
  ...
}
```
{% endcode %}

## `RangeError<Id,`<mark style="color:green;background-color:green;">`Min`</mark>`,Max>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Min`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)`=`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) and [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined), by default of the value **captured** from the provided [`min`](constructor.md#min-min) indicates the minimum range type of a new [`RangeError`](broken-reference) instance.

{% code title="range-error.class.ts" %}
```typescript
class RangeError<
  Id extends string,
  Min extends number | undefined = undefined, // <--- Declare generic type variable Min.
  Max extends number | undefined = undefined
> extends CommonError<Id> {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id,
    min?: Min, // <--- Capture generic type variable Min.
    max?: Max,
    template = RangeError.template
  ) { ... }
  ...
}
```
{% endcode %}

## `RangeError<Id,Min,`<mark style="color:green;background-color:green;">`Max`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Max`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)`=`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) and [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) by default of the value **captured** from the provided [`max`](constructor.md#max-max) indicates the maximum range type of a new [`RangeError`](broken-reference) instance.

{% code title="range-error.class.ts" %}
```typescript
class RangeError<
  Id extends string,
  Min extends number | undefined = undefined,
  Max extends number | undefined = undefined // <--- Declare generic type variable Max.
> extends CommonError<Id> {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id,
    min?: Min,
    max?: Max, // <--- Capture generic type variable Max.
    template = RangeError.template
  ) { ... }
  ...
}
```
{% endcode %}
