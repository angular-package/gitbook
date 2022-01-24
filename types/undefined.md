# Undefined

## `Undefined<Type>`

A generic type `Undefined` indicates generic type variable [`Type`](undefined.md#type) as [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined). It takes generic type variable [`Type`](undefined.md#type) causing other types than [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) its change to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

{% code title="undefined.type.ts" %}
```typescript
type Undefined<Type> = Type extends undefined ? Type : never;
```
{% endcode %}

### Generic type variables

#### `Type`

Generic type variable that cannot be different than [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).
