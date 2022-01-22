# Types

### `Types<Obj>`

The main types as string values, besides the `Constructor` which is an instance of an Obj.

{% code title="types.type.ts" %}
```typescript
type Types<Obj> = Constructor<Obj> | 'function' | 'object' | Primitives;
```
{% endcode %}

