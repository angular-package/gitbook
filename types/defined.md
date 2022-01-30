# Defined

## `Defined<Type>`

A generic type `Defined` indicates the generic type variable [`Type`](defined.md#type) is never [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined). It takes generic type variable [`Type`](defined.md#type) constrained by [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) which constraint causes its change to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

{% code title="defined.type.ts" %}
```typescript
type Defined<Type> = Type extends undefined ? never : Type;
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/type/defined.type.ts" %}

### Generic type variables

#### `Type`

A generic type variable `Type` is never [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) but captured type.
