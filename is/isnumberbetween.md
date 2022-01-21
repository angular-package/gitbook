# isNumberBetween()

### `isNumberBetween()`

Checks if any value is a `number` type or an instance of `Number` by using `isNumber()` between a specified range.

{% code title="is-number-between.func.ts" %}
```typescript
const isNumberBetween = <
  Type extends AnyNumber = number,
  Min extends number = number,
  Max extends number = number,
  Payload extends object = object
>(
  value: any,
  range: MinMax<Min, Max> | Min | Max,
  callback: ResultCallback<
    any,
    MinMax<Min, Max> & Payload
  > = resultCallback,
  payload?: Payload
): value is NumberBetween<Min, Max, Type> =>
  callback(
    isNumber(value)
    ? isObject(range)
      ? (isNumberType(range.min) && range.min >= 0
          ? value.valueOf() >= range.min
          : true) &&
          (isNumberType(range.max) && range.max >= 0
            ? value.valueOf() <= range.max
            : true)
        : isNumberType(length) && value.valueOf() === range
    : false,
    value,
    {
      ...payload,
      ...(isNumberType(range) ? { range } : range),
    } as any
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

### Example usage

```typescript
// Example usage
import { isNumberBetween } from '@angular-package/type';

```

