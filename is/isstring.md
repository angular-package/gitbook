# isString()

### `isString()`

Checks if any value is a `string` type by using the `isStringType()` function or an instance of `String` by using the `isStringObject()` function.

{% code title="is-string.func.ts" %}
```typescript
const isString = <
  Type extends AnyString = string,
  Payload extends object = object
>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Type =>
  callback(isStringType(value) || isStringObject(value), value, payload);
```
{% endcode %}

### Parameters

| Name: type                               | Description                     |
| ---------------------------------------- | ------------------------------- |
| `value: any`                             | The value of any type to check. |
| `callback: ResultCallback<any, Payload>` |                                 |
| `payload?: Payload`                      |                                 |

### Returns

The return value is a `boolean` indicating whether the provided `value` is a `string` type or an instance of `String`.

### Example usage

```typescript
// Example usage.
import { isString } from '@angular-package/type';

```

