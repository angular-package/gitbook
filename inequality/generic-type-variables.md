---
description: The `Inequality` primitive wrapper object generic type variables
---

# Generic type variables

## `Inequality<`<mark style="color:green;background-color:green;">`Value`</mark>`>`

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`value`](constructor.md#value-value) indicates the [primitive value](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) type of a new child class instance.

{% code title="inequality.class.ts" %}
```typescript
abstract class Inequality<
  Value extends number // <--- Declare generic type variable Value.
> extends Number {
  constructor(
    value: Value // <--- Capture generic type variable Value.
  ) {
    super(value);
    this.#greater = new Greater(value);
    this.#less = new Less(value);
  }
}
```
{% endcode %}
