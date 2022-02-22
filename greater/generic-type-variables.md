---
description: The `Greater` primitive wrapper object generic type variables
---

# Generic type variables

### `Greater<`<mark style="color:green;background-color:green;">`Value`</mark>`>`

#### <mark style="color:green;">`Value`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`value`](constructor.md#value-value) indicates the [primitive value](methods/valueof.md) type of a new [`Greater`](broken-reference) instance.

{% code title="greater.class.ts" %}
```typescript
class Greater<
  Value extends number // <--- Declare generic type variable Value.
> extends Number{
  constructor(
    value: Value // <--- Capture generic type variable Value.
  ) {
    super(value);
  }
}
```
{% endcode %}
