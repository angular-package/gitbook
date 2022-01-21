# isNumber()

### `isNumber()`

Checks if any value is a `number` type, or the type obtained from its `Object.prototype` equal to `'number'` or an `object` type and an instance of `Number`. The value is also checked by the `Number.isFinite()` method to determine whether it's finite and is validated by the `Number.isNaN()` method.

{% code title="is-number.func.ts" %}
```typescript
const isNumber = <
  Type extends AnyNumber = number,
  Payload extends object = object
>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Type =>
  callback(
    (typeof value === 'number' ||
    ((typeOf(value) === 'number' || typeof value === 'object') &&
      value instanceof Number)) &&
    !Number.isNaN(value.valueOf()) &&
    Number.isFinite(value.valueOf()),
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
import { isNumber } from '@angular-package/type';

```

