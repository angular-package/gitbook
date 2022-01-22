# guardKey()

### `guardKey()`

Description

{% code title="guard-key.func.ts" %}
```typescript
const guardKey = <Key extends PropertyKey, Payload extends object>(
  value: Key,
  callback?: ResultCallback<PropertyKey, Payload>,
  payload?: Payload
): value is Key => isKey(value, callback, payload);
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

