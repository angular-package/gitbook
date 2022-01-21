# isRegExp()

### `isRegExp()`

Checks if any value is a regular expression of the type obtained from its `Object.prototype` equal to `'regexp'`, or an `object` type, and an instance of `RegExp`.

{% code title="is-reg-exp.func.ts" %}
```typescript
const isRegExp = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is RegExp =>
  callback(
    (typeOf(value) === 'regexp' || typeof value === 'object') &&
    value instanceof RegExp,
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
import { isRegExp } from '@angular-package/type';

```

