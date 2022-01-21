# isStringLength()

### `isStringLength()`

Checks if any value is a `string` type or an instance of `String` by using `isString()` of `length` within the specified range.

{% code title="is-string-length.func.ts" %}
```typescript
const isStringLength = <
  Type extends AnyString = string,
  Min extends number = number,
  Max extends number = number,
  Payload extends object = object
>(
  value: any,
  length: MinMax<Min, Max> | Min | Max,
  callback: ResultCallback<any, MinMax<Min, Max> & Payload> = resultCallback,
  payload?: Payload
): value is StringOfLength<Min, Max, Type> =>
  callback(
    isString(value)
    ? isObject(length)
      ? (isNumberType(length.min) && length.min >= 0
          ? value.valueOf().length >= length.min
          : true) &&
        (isNumberType(length.max) && length.max >= 0
          ? value.valueOf().length <= length.max
          : true)
      : isNumberType(length) && value.valueOf().length === length
    : false,
    value,
    { ...payload, ...(isNumberType(length) ? { length } : length) } as Payload
  );
```
{% endcode %}

### Parameters

| Name: type | Description |
| ---------- | ----------- |
|            |             |
|            |             |
|            |             |

### Returns

The return value is a `boolean` indicating whether the provided `value` is a `string` type or an instance of `String` of length within the specified range.

### Example usage

```typescript
// Example usage
import { isStringLength } from '@angular-package/type';

```

