# isObjectKeyIn()

### `isObjectKeyIn()`

Checks if any value is an `object` by using the `isObject()` function with a key of the `PropertyKey` in it(or its prototype chain) by using the `in` operator.

{% code title="is-object-key-in.func.ts" %}
```typescript
const isObjectKeyIn = <Obj = object, Payload extends object = object>(
  value: any,
  key: PropertyKey,
  callback: ResultCallback<any, { key: typeof key } & Payload> = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(isObject(value) ? key in value : false, value, {
    ...payload,
    key,
  } as any);
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
import { isObjectKeyIn } from '@angular-package/type';

```

