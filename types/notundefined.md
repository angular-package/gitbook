# NotUndefined

### `NotUndefined<Type>`

A generic type `NotUndefined` that takes generic type variable `Type` constrained by `undefined` and `null` which constraint causes its change to `never`.

{% code title="not-undefined.type.ts" %}
```typescript
type NotUndefined<Type> = Type extends undefined | null ? never : Type;
```
{% endcode %}

