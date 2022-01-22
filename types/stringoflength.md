# StringOfLength

### `StringOfLength<Min, Max, Type>`

A generic type `StringOfLength` that takes generic type variable `Min` and `Max` constrained by `number` type as length, and takes generic type variable `Type` constrained by [`AnyString`](anystring.md) as the type by default `string` or an instance of `String`.

{% code title="string-of-length.type.ts" %}
```typescript
type StringOfLength<
  Min extends number,
  Max extends number,
  Type extends AnyString = string
> = Type & MinMax<Min, Max>;
```
{% endcode %}

