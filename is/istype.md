# isType()

### `isType()`

Checks if any value is the type from a given `type` of the `Types`.

{% code title="is-type.func.ts" %}
```typescript
const isType = <T extends Type, Payload extends object = object>(
  value: any,
  type: Types<T>,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is T =>
  isStringType(type)
  ? {
      bigint: isBigInt,
      boolean: isBooleanType,
      function: isFunction,
      number: isNumberType,
      object: isObject,
      null: isNull,
      string: isStringType,
      symbol: isSymbol,
      undefined: isUndefined,
    }[type as Primitives](value, callback, payload)
  : isNotNull(type)
  ? isInstance(value, type, callback, payload)
  : false;
```
{% endcode %}

### Parameters

| Name: type | Description |
| ---------- | ----------- |
|            |             |
|            |             |
|            |             |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a type from a given `type`.

### Example usage

```typescript
// Example usage
import { isType } from '@angular-package/type';

```

