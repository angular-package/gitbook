---
description: The `ValidationError` object generic type variables
---

# Generic type variables

## `ValidationError<`<mark style="color:green;background-color:green;">`Id`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`id`](constructor.md#id-id) indicates the [identification](../getting-started/basic-concepts.md#unique-identification) type of a new [`ValidationError`](broken-reference) instance.

{% code title="validation-error.class.ts" %}
```typescript
class ValidationError<
  Id extends string  // <--- Declare generic type variable Id.
> extends Error {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id,   // <--- Captureval generic type variable Id.
    template = ValidationError.template
  ) { ... }
  ...
}
```
{% endcode %}
