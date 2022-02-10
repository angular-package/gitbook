---
description: The `TypeError` object generic type variables
---

# Generic type variables

## `TypeError<`<mark style="color:green;background-color:green;">`Id`</mark>`,Type>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`=`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`id`](v-constructor.md#id-id) indicates the identification type of a new [`TypeError`](broken-reference) instance.

{% code title="type-error.class.ts" %}
```typescript
class TypeError<
  Id extends string,  // <--- Declare generic type variable Id.
  Type extends string | undefined = undefined
> extends Error {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id, // <--- Capture generic type variable Id.
    type?: Type,
    template = TypeError.template
  ) { ... }
  ...
}
```
{% endcode %}

## `TypeError<Id,`<mark style="color:green;background-color:green;">`Type`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Type`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)`=`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) and [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined), by default of the value equal to [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) indicates the captured type of the supplied [`type`](v-constructor.md#type-type) of a new [`TypeError`](broken-reference) instance.

{% code title="type-error.class.ts" %}
```typescript
class TypeError<
  Id extends string,
  Type extends string | undefined = undefined  // <--- Declare generic type variable Type.
> extends Error {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id,
    type?: Type,  // <--- Declare generic type variable Type.
    template = TypeError.template
  ) { ... }
  ...
}
```
{% endcode %}
