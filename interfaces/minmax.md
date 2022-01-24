# MinMax

## `MinMax<Min, Max>`

A generic type `MinMax` that takes generic type variables [`Min`](minmax.md#min-extends-number) and [`Max`](minmax.md#max-max) represents the range between minimum and maximum.

{% code title="minmax.interface.ts" %}
```typescript
interface MinMax<Min extends number, Max extends number> {
  min: Min;
  max: Max;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Min`</mark>`extends`<mark style="color:green;">`number`</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type indicates the **minimum** number.

#### <mark style="color:green;">`Max`</mark>`extends`<mark style="color:green;">`number`</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type indicates the **maximum** number.

### Properties

#### `min:`<mark style="color:green;">`Min`</mark>

The **minimum** value of a generic type variable [`Min`](minmax.md#minextendsnumber) constrained by a [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type.

#### `max:`<mark style="color:green;">`Max`</mark>

The **maximum** value of a generic type variable [`Max`](minmax.md#maxextendsnumber) constrained by a [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type.
