# isObjectKeys()

### `isObjectKeys()`

Checks if any value is an `object` by using the `isObject()` function with some of its keys or some groups of its keys of the `PropertyKey` type.

{% code title="is-object-keys.func.ts" %}
```typescript
const isObjectKeys = <Obj = object, Payload extends object = object>(
  value: any,
  keys: PropertyKey[],
  callback: ResultCallback<
    any,
    { keys: typeof keys } & Payload
  > = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) && isArray(keys)
    ? keys.every((key) => ({}.hasOwnProperty.call(value, key)))
    : false,
    value,
    { ...payload, keys } as any
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
import { isObjectKeys } from '@angular-package/type';

```

