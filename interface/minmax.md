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

#### <mark style="color:green;">`Max`</mark>`extends`<mark style="color:green;">`number`</mark>

### Properties

#### `min:`<mark style="color:green;">`Min`</mark>

The minimum value of a generic type variable `Min` constrained by a `number` type.

#### `max:`<mark style="color:green;">`Max`</mark>

The maximum value of a generic type variable `Max` constrained by a `number` type.
