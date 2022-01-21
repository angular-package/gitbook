# isKey()

### `isKey()`

Checks if any value is one of the `string`, `number`, or `symbol` type.

{% code title="is-key.func.ts" %}
```typescript
const isKey = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is PropertyKey =>
  callback(
    isStringType(value) || isNumberType(value) || isSymbol(value),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isKey } from '@angular-package/type';

```

