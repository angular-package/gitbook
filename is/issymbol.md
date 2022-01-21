# isSymbol()

### `isSymbol()`

Checks if any value is a `symbol` type.

{% code title="is-symbol.func.ts" %}
```typescript
const isSymbol = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is symbol =>
  callback(typeof value === 'symbol', value, payload);
```
{% endcode %}

### Generic type variables

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isSymbol } from '@angular-package/type';

```

