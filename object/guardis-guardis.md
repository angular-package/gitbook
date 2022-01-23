# guardIs: GuardIs {}

## `guardIs: GuardIs {}`

The object contains prefixed with **guard** functions.

```typescript
const guardIs: GuardIs = Object.freeze({
  array: guardArray,
  bigint: guardBigInt,
  boolean: guardBoolean,
  class: guardClass,
  date: guardDate,
  defined: guardDefined,
  false: guardFalse,
  function: guardFunction,
  instance: guardInstance,
  key: guardKey,
  null: guardNull,
  number: guardNumber,
  numberBetween: guardNumberBetween,
  object: guardObject,
  objectKey: guardObjectKey,
  objectKeyIn: guardObjectKeyIn,
  objectKeys: guardObjectKeys,
  objectSomeKeys: guardObjectSomeKeys,
  primitive: guardPrimitive,
  regexp: guardRegExp,
  string: guardString,
  stringLength: guardStringLength,
  symbol: guardSymbol,
  true: guardTrue,
  type: guardType,
  undefined: guardUndefined
});
```
