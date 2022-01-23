# NumberBetween

### `NumberBetween<Min, Max, Type>`

A generic type `NumberBetween` that takes generic type variable `Min` and `Max` constrained by `number` type as range, and takes generic type variable `Type` constrained by `AnyNumber` as the type by default `number` or an instance of `Number`.

{% code title="number-between.type.ts" %}
```typescript
type NumberBetween<
  Min extends number,
  Max extends number,
  Type extends AnyNumber = number
> = Type & MinMax<Min, Max>;
```
{% endcode %}

