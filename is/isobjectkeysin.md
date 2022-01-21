# isObjectKeysIn()

### `isObjectKeysIn()`

Checks if any value is an `object` by using the `isObject()` function with keys of the `PropertyKey` in it(or its prototype chain) by using the `in` operator.

{% code title="is-object-keys-in.func.ts" %}
```typescript
const isObjectKeysIn = <Obj = object, Payload extends object = object>(
  value: any,
  keys: PropertyKey[],
  callback: ResultCallback<
    any,
    { keys: typeof keys } & Payload
  > = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) && isArray(keys) ? keys.every((k) => k in value) : false,
    value,
    { ...payload, keys } as any
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
import { isObjectKeysIn } from '@angular-package/type';

```

