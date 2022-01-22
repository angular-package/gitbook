# guardDate()

### `guardDate()`

Description

{% code title="guard-date.func.ts" %}
```typescript
const guardDate = <Payload extends object>(
  value: Date,
  callback?: ResultCallback<Date, Payload>,
  payload?: Payload
): value is Date => isDate(value, callback, payload);
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

