# guardFalse()

### `guardFalse()`

Description

{% code title="guard-false.func.ts" %}
```typescript
const guardFalse = <Payload extends object>(
  value: false,
  callback?: ResultCallback<false, Payload>,
  payload?: Payload
): value is false => isFalse(value, callback, payload);
```
{% endcode %}

### Generic type variables

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage.
import { guardFalse } from '@angular-package/type';

```

