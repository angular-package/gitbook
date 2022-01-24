# isNot: IsNot {}

## `isNot: IsNot {}`

The [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) consists of **isNot** functions.

```typescript
const isNot: IsNot = Object.freeze({
  boolean: isNotBoolean,
  defined: isNotDefined,
  function: isNotFunction,
  null: isNotNull,
  number: isNotNumber,
  string: isNotString,
  undefined: isNotUndefined
});
```
