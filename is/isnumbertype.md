# isNumberType()

### `isNumberType()`

Checks if any value is a `number` type and is checked by the `Number.isFinite()` method to determine whether it's finite and is validated by the `Number.isNaN()` method.

{% code title="is-number-type.func.ts" %}
```typescript
const isNumberType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is number =>
  callback(
    typeof value === 'number' && Number.isFinite(value) && !Number.isNaN(value),
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
import { isNumberType } from '@angular-package/type';

```

