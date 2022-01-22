# guardRegExp()

### `guardRegExp()`

Description

{% code title="guard-regexp.func.ts" %}
```typescript
const guardRegExp = <Type extends RegExp, Payload extends object>(
  value: Type,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isRegExp(value, callback, payload);
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

