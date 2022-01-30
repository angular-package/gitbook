# Never

## `Never<Not, Type>`

A generic type `Never` indicates the generic type variable [`Type`](never.md#type) is never of the generic type variable [`Not`](never.md#not). It takes generic type variable [`Type`](never.md#type) constrained by a generic type variable [`Not`](never.md#not) which constraint causes its change to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

{% code title="never.type.ts" %}
```typescript
type Never<Not, Type> = Type extends Not ? never : Type;
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/type/never.type.ts" %}

### Generic type variables

#### `Not`

A generic type variable `Not` constrain the generic type variable [`Type`](never.md#type) causing the [`Type`](never.md#type) change to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

#### `Type`

A generic type variable `Type` constrained by generic type variable [`Not`](never.md#not) is never [`Not`](never.md#not).
