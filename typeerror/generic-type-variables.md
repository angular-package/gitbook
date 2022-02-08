---
description: The `TypeError` object generic type variables
---

# Generic type variables

## `TypeError<`<mark style="color:green;">`Id`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`=`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`id`](constructor.md#id-id) indicates the identification type of a new [`TypeError`](broken-reference) instance.

{% code title="type-error.class.ts" %}
```typescript
class TypeError<
  Id extends string = string  // <--- Declare generic type variable Id.
> extends Error {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id,  // <--- Capture generic type variable Id.
    type?: string,
    template = TypeError.template
  ) { ... }
  ...
}
```
{% endcode %}
