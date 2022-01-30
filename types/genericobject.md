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

{% embed url="https://github.com/angular-package/type/blob/main/src/type/generic-object.type.ts" %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`=`<mark style="color:green;">`any`</mark>

A generic type variable `Value` indicates the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) property type, by default [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any).
