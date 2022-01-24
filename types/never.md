# Never

## `Never<Not, Type>`

A generic type `Never` that takes generic type variable `Type` constrained by a generic type variable `Not` which constraint causes its change to `never`.

{% code title="never.type.ts" %}
```typescript
type Never<Not, Type> = Type extends Not ? never : Type;
```
{% endcode %}

### Generic type variables

#### `Not`

#### `Type`
