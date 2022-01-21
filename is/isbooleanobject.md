# isBooleanObject()

### `isBooleanObject()`

Description

{% code title="is-array.func.ts" %}
```typescript
const isArray = <Type = any, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Array<Type> =>
  callback(
    (typeOf(value) === 'array' || typeof value === 'object') &&
      Array.isArray(value),
    value,
    payload
  );
```
{% endcode %}

### Parameters

| Name: type          | Description                                                                                                            |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `value: any`        |                                                                                                                        |
|                     |                                                                                                                        |
| `payload?: Payload` | Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function. |

### Returns

### Example usage

```typescript
// Example usage
import { isBooleanObject } from '@angular-package/type';

```

