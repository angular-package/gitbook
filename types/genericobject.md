# GenericObject

### `GenericObject<Value>`

The type of generic object that takes generic type variable `Value`.

{% code title="generic-object.type.ts" %}
```typescript
type GenericObject<Value = any> = {
  [index: string]: Value;
};
```
{% endcode %}

