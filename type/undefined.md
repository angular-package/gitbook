# Undefined

### `Undefined<Type>`

A generic type `Undefined` that takes generic type variable `Type` constrained by `undefined` causes other types than `undefined` its change to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

{% code title="undefined.type.ts" %}
```typescript
type Undefined<Type> = Type extends undefined ? Type : never;
```
{% endcode %}

