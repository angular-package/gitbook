# GenericObject

## `GenericObject<Value>`

The type of generic object that takes generic type variable [`Value`](genericobject.md#value-any).

{% code title="generic-object.type.ts" %}
```typescript
type GenericObject<Value = any> = {
  [index: string]: Value;
};
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`=`<mark style="color:green;">`any`</mark>
