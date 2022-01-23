# Constructor

### `Constructor<Type>`

An instance of a type from the provided generic type variable `Type`.

{% code title="constructor.type.ts" %}
```typescript
type Constructor<Type> = new (...args: any[]) => Type;
```
{% endcode %}

### Generic type variables

Type
