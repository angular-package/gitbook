# isBooleanType()

### `isBooleanType()`

Description

{% code title="is-boolean-type.func.ts" %}
```typescript
const isBooleanType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is boolean =>
  callback(
    typeof value === 'boolean' && (value === true || value === false),
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
import { isBooleanType } from '@angular-package/type';

```

