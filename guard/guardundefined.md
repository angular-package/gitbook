# guardUndefined()

### `guardUndefined()`

Description

{% code title="guard-undefined.func.ts" %}
```typescript
const guardUndefined = <Payload extends object>(
  value: undefined,
  callback?: ResultCallback<undefined, Payload>,
  payload?: Payload
): value is undefined => isUndefined(value, callback, payload);
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

