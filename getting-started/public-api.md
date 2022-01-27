# Public API

## Function

### Helper

Help to determine the value type.

```typescript
// Helper.
import {
  recognizeValue, // From the `5.0.0` version
  typeOf,
} from '@angular-package/type';
```

### `is`

Functions with the prefix **`is`** determine whether the value of [any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type is of the specified type.

```typescript
// `is` prefix functions.
import {
  isArray,
  isBigInt,
  isBoolean,
  isBooleanObject,
  isBooleanType,
  isClass,
  isDate, // From the 4.2.0 version.
  isDefined,
  isFalse, // From the 4.2.0 version.
  isFunction,
  isInstance,
  isKey,
  isNull,
  isNumber,
  isNumberBetween, // From the 4.2.0 version.
  isNumberObject,
  isNumberType,
  isObject,
  isObjectKey,
  isObjectKeyIn,
  isObjectKeys,
  isObjectKeysIn, // From the `5.0.0` version
  isObjectSomeKeys, // From the `5.0.0` version
  isPrimitive,
  isRegExp, // From the 4.2.0 version.
  isString,
  isStringIncludes, // From the `5.0.0` version
  isStringIncludesSome, // From the `5.0.0` version
  isStringLength, // From the 4.2.0 version.
  isStringObject,
  isStringType,
  isSymbol,
  isTrue, // From the 4.2.0 version.
  isType,
  isUndefined,
} from '@angular-package/type';
```

### `isNot`

Functions with the prefix **`isNot`** determine whether the value of [any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type is **not** of a specified type.

```typescript
// `isNot` prefix functions.
import {
  isNotBoolean,
  isNotDefined,
  isNotFunction,
  isNotNull,
  isNotNumber,
  isNotString,
  isNotUndefined
} from '@angular-package/type';
```

### `are`

Functions with the prefix **`are`** determine whether the values of [any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type are of the specified type.

```typescript
// `are` prefix functions.
import {
  // Function.
  areBigInt, // From the `5.0.0` version
  areBoolean, // From the `5.0.0` version
  areDate, // From the `5.0.0` version
  areDefined, // From the `5.0.0` version
  areFalse, // From the `5.0.0` version
  areNull, // From the `5.0.0` version
  areNumber, // From the `5.0.0` version
  areRegExp, // From the `5.0.0` version
  areString,
  areSymbol, // From the `5.0.0` version
  areTrue, // From the `5.0.0` version
  areUndefined, // From the `5.0.0` version
} from '@angular-package/type';
```

### `guard`

Functions with the prefix **`guard`** constraint the type and determine the value is of the specified type.

```typescript
// `guard` prefix functions.
import { 
  guardArray,
  guardBigInt,
  guardBoolean,
  guardClass,
  guardDate, // From the `5.0.0` version
  guardDefined,
  guardFalse,  // From the `5.0.0` version
  guardFunction,
  guardInstance,
  guardKey,
  guardNull,
  guardNumber,
  guardNumberBetween,  // From the `5.0.0` version
  guardObject,
  guardObjectKey,
  guardObjectKeyIn,  // From the `5.0.0` version
  guardObjectKeys,
  guardObjectSomeKeys, // From the `5.0.0` version
  guardPrimitive,
  guardRegExp,  // From the `5.0.0` version
  guardString,
  guardStringLength,  // From the `5.0.0` version
  guardSymbol,
  guardTrue,  // From the `5.0.0` version
  guardType,
  guardUndefined,
} from '@angular-package/type'; 
```

## Object

The objects represent the check and guard functions.

```typescript
// Objects.
import {
  are,
  guard,
  is,
  isNot,
  type
} from '@angular-package/type';
```

## Interface

```typescript
// Interfaces.
import {
  MinMax
} from '@angular-package/type';
```

## Type

```typescript
// Types.
import {
  AnyBoolean,
  AnyNumber,
  AnyString,
  CallbackPayload, // From the `5.0.0` version.
  Constructor,
  Defined,
  ForEachCallback,  // From the `5.0.0` version.
  Never,
  NotUndefined,
  NumberBetween, // From the `4.2.0` version.
  Primitive,
  Primitives,
  ResultCallback, // From the `4.2.0` version
  StringOfLength, // From the `4.2.0` version.
  Type,
  Types,
  Undefined
} from '@angular-package/type';
```
