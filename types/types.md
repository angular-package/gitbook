# Types

## `Types<Obj>`

The **main** types as string values, besides the [`Constructor`](constructor.md) which is an instance of an [`Obj`](types.md#obj).

{% code title="types.type.ts" %}
```typescript
type Types<Obj> = Constructor<Obj> | 'function' | 'object' | Primitives;
```
{% endcode %}

### Generic type variables

#### `Obj`

Generic type variable `Obj` indicates an instance of the generic type [`Constructor`](constructor.md).
