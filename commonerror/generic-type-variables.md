---
description: The `CommonError` object generic type variables
---

# Generic type variables

## `CommonError<`<mark style="color:green;background-color:green;">`Id`</mark>`>`

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`id`](constructor.md#id-id) indicates the identification type of a new [`CommonError`](broken-reference) instance.

{% code title="common-error.class.ts" %}
```typescript
abstract class CommonError<
  Id extends string // <--- Declare generic type variable Id.
> extends Error {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id, // <--- Capture generic type variable Id.
    template = CommonError.template,
    additional?: { link?: string; max?: number; min?: number; type?: string }
  ) { ... }
  ...
}
```
{% endcode %}
