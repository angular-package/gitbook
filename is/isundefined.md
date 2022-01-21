# isUndefined()

### ​`isUndefined()`

Checks if any value is an `undefined` type.

{% code title="is-undefined.func.ts" %}
```typescript
const isUndefined = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is undefined =>
  callback(typeof value === 'undefined', value, payload);
```
{% endcode %}

### Parameters

| Name: type | Description |
| ---------- | ----------- |
|            |             |
|            |             |
|            |             |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is `undefined`.

### Example usage

```typescript
// Example usage
import { isUndefined } from '@angular-package/type';

```

