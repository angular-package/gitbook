# isNull()

### `isNull()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'null'` or an `object` type that is equal to `null`.

{% code title="is-null.func.ts" %}
```typescript
const isNull = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is null =>
  callback(
    (typeOf(value) === 'null' || typeof value === 'object') && value === null,
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
import { isNull } from '@angular-package/type';

```

