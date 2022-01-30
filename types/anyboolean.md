# AnyBoolean

## `AnyBoolean`

A [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) type or an instance of a [`Boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean).

{% code title="any-boolean.type.ts" %}
```typescript
type AnyBoolean = Exclude<boolean | Boolean, true | false>;
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/type/any-boolean.type.ts" %}
