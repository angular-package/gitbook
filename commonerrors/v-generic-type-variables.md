---
description: The `CommonErrors` generic type variables
---

# v: Generic type variables

## `CommonErrors<`<mark style="color:green;background-color:green;">`Id`</mark>`>`

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided rest parameter [`id`](v-constructor.md#...id-id) indicates the identification type of a new [`CommonErrors`](broken-reference) instance.

{% code title="common-errors.class.ts" %}
```typescript
abstract class CommonErrors<
  Id extends string // <--- Declare generic type variable Id.
> {
  constructor(
    ...id: Id[] // <--- Capture generic type variable Id.
  ) {
    Array.isArray(id) && (this.#id = new Set(id));
  }
}
```
{% endcode %}
