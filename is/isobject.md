# isObject()

### `isObject()`

Checks if any value is an `object` type or the type obtained from its `Object.prototype` equal to `'object'`, and an instance of `Object`.

{% code title="is-object.func.ts" %}
```typescript
const isObject = <Obj = object, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    (typeof value === 'object' || typeOf(value) === 'object') &&
    value instanceof Object,
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
import { isObject } from '@angular-package/type';

```

