# Undefined

## `Undefined<Type>`

A generic type `Undefined` that takes generic type variable [`Type`](undefined.md#type) constrained by [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) causes other types than [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) its change to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

{% code title="undefined.type.ts" %}
```typescript
type Undefined<Type> = Type extends undefined ? Type : never;
```
{% endcode %}

### Generic type variables

#### `Type`
