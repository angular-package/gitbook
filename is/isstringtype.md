# isStringType()

### `isStringType()`

Checks if any value is one of the `string`, `number`, or `symbol` type.

{% code title="is-string-type.func.ts" %}
```typescript
const isStringType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is string =>
  callback(typeof value === 'string', value, payload);
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
import { isStringType } from '@angular-package/type';

```

