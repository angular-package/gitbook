---
description: The `ValidationErrors` object generic type variables
---

# v: Generic type variables

## `TypeErrors<`<mark style="color:green;background-color:green;">`Id`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) [`id`](../rangeerrors/constructor.md#...id-id) indicates the identification type of a new [`TypeErrors`](broken-reference) instance.

{% code title="type-errors.class.ts" %}
```typescript
class TypeErrors<
  Id extends string // <--- Declare generic type variable Id.
> {
  constructor(
    ...id: Id[] // <--- Capture generic type variable Id.
  ) {
    super(...id);
  }
}
```
{% endcode %}
