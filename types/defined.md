# Defined

## `Defined<Type>`

A generic type `Defined` that takes generic type variable `Type` constrained by `undefined` which constraint causes its change to `never`.

{% code title="defined.type.ts" %}
```typescript
type Defined<Type> = Type extends undefined ? never : Type;
```
{% endcode %}

### Generic type variables

#### `Type`
