# isNumberObject()

### `isNumberObject()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'number'`, or an `object` type and an instance of `Number` and is also checked by the `isFinite()` method to determine whether it's finite and is validated by the `Number.isNaN()` method.

{% code title="is-number-object.func.ts" %}
```typescript
const isNumberObject = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Number =>
  callback(
    (typeOf(value) === 'number' || typeof value === 'object') &&
    value instanceof Number &&
    !Number.isNaN(value.valueOf()) &&
    Number.isFinite(value.valueOf()),
    value,
    payload
  );
```
{% endcode %}

### Parameters

| Name: type | Description |
| ---------- | ----------- |
|            |             |
|            |             |
|            |             |

### Returns

### Example usage

```typescript
// Example usage
import { isNumberObject } from '@angular-package/type';

```

