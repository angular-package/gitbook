# isClass()

### `isClass()`

Description

{% code title="is-class.func.ts" %}
```typescript
const isClass = <Class = Function, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Class =>
  callback(
    typeof value === 'function' ||
    (typeOf(value) === 'function' && value instanceof Function)
    ? /class/.test(Function.prototype.toString.call(value).slice(0, 5))
    : false,
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
import { isClass } from '@angular-package/type';

```

