# isObjectKey()

### `isObjectKey()`

Checks if any value is an `object` by using the `isObject()` function with its key of the `PropertyKey` type.

{% code title="is-object-key.func.ts" %}
```typescript
const isObjectKey = <
  Obj extends object,
  Payload extends object = object
>(
  value: any,
  key: PropertyKey,
  callback: ResultCallback<Obj, { key: typeof key } & Payload> = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) ? {}.hasOwnProperty.call(value, key) : false,
    value,
    { ...payload, key } as any
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
import { isObjectKey } from '@angular-package/type';

```

