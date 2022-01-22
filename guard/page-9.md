# guardNull()

### `guardNull()`

Description

{% code title="guard-null.func.ts" %}
```typescript
const guardNull = <Payload extends object>(
  value: null,
  callback?: ResultCallback<null, Payload>,
  payload?: Payload
): value is null => isNull(value, callback, payload);
```
{% endcode %}

### Generic type variables

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage.
import {  } from '@angular-package/type';


```

