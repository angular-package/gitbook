# guardIs: GuardIs {}

## `guardIs: GuardIs {}`

The object contains prefixed with **guard** functions.

{% code title="guard-is.object.ts" %}
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
  objectKeysIn: guardObjectKeysIn,
  objectSomeKeys: guardObjectSomeKeys,
  primitive: guardPrimitive,
  regexp: guardRegExp,
  string: guardString,
  stringIncludes: guardStringIncludes,
  stringIncludesSome: guardStringIncludesSome,
  stringLength: guardStringLength,
  stringLengthBetween: guardStringLengthBetween,
  symbol: guardSymbol,
  true: guardTrue,
  type: guardType,
  undefined: guardUndefined
});
```
{% endcode %}
