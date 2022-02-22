---
description: The `Minimum` primitive wrapper object generic type variables
---

# Generic type variables

### `Minimum<`<mark style="color:green;background-color:green;">`Value`</mark>`>`

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`value`](constructor.md#value-value) indicates the [primitive value](../less/methods/valueof.md) type of a new [`Minimum`](broken-reference) instance.

{% code title="minimum.class.ts" %}
```typescript
class Minimum<
  Value extends number // <--- Declare generic type variable Value.
> extends Inequality<Value> {
  constructor(
    value: Value // <--- Capture generic type variable Value.
  ) {
    super(value);
  }
}
```
{% endcode %}
