# guardSymbol()

### `guardSymbol()`

Description

{% code title="guard-symbol.func.ts" %}
```typescript
const guardSymbol = <Payload extends object>(
  value: symbol,
  callback?: ResultCallback<symbol, Payload>,
  payload?: Payload
): value is symbol => isSymbol(value, callback, payload);
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

