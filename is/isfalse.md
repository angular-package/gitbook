# isFalse()

### `isFalse()`

Description

{% code title="is-false.func.ts" %}
```typescript
const isFalse = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is false =>
  callback(
    isBoolean(value) ? value.valueOf() === false : false,
    value,
    payload
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
import { isFalse } from '@angular-package/type';

```

