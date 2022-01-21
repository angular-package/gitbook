# isStringObject()

### `isStringObject()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'string'` or an `object` type, and an instance of `String`.

{% code title="is-string-object.func.ts" %}
```typescript
const isStringObject = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is String =>
  callback(
    (typeOf(value) === 'string' || typeof value === 'object') &&
    value instanceof String,
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
import { isStringObject } from '@angular-package/type';

```

