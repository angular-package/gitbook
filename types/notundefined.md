# NotUndefined

## `NotUndefined<Type>`

A generic type `NotUndefined` represents any type instead of [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined). It takes generic type variable [`Type`](notundefined.md#type) constrained by [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) which constraint causes its change to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

{% code title="not-undefined.type.ts" %}
```typescript
type NotUndefined<Type> = Type extends undefined ? never : Type;
```
{% endcode %}

### Generic type variables

#### `Type`
