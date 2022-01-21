# is: Is {}

### `is: Is {}`

The object contains prefixed with `is` functions and prefixed with `isNot` functions in property `not`.

```typescript
const is: Is = Object.freeze({
  array: isArray,
  bigint: isBigInt,
  boolean: isBoolean,
  booleanObject: isBooleanObject,
  booleanType: isBooleanType,
  class: isClass,
  date: isDate, // From the `4.2.0` version.
  defined: isDefined,
  false: isFalse, // From the `4.2.0` version.
  function: isFunction,
  instance: isInstance,
  key: isKey,
  not: isNot,
  null: isNull,
  number: isNumber,
  numberBetween: isNumberBetween, // From the `4.2.0` version.
  numberObject: isNumberObject,
  numberType: isNumberType,
  object: isObject,
  objectKey: isObjectKey,
  objectKeyIn: isObjectKeyIn,
  objectKeys: isObjectKeys,
  objectKeysIn: isObjectKeysIn, // From the `5.0.0` version.
  objectSomeKeys: isObjectSomeKeys, // From the `5.0.0` version.
  primitive: isPrimitive,
  regexp: isRegExp, // From the `4.2.0` version.
  string: isString,
  stringIncludes: isStringIncludes, // From the `5.0.0` version.
  stringIncludesSome: isStringIncludesSome, // From the `5.0.0` version.
  stringLength: isStringLength, // From the `4.2.0` version.
  stringObject: isStringObject,
  stringType: isStringType,
  symbol: isSymbol,
  true: isTrue, // From the `4.2.0` version.
  type: isType,
  undefined: isUndefined
});
```

### Example usage
