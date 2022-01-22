# guardType()

### `guardType()`

Description

{% code title="guard-type.func.ts" %}
```typescript
const guardType = <T extends Type, Payload extends object = object>(
  value: T,
  type: Types<T>,
  callback?: ResultCallback<T, Payload>,
  payload?: Payload
): value is T => isType(value, type, callback, payload);
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

