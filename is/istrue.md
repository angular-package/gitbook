# isTrue()

### `isTrue()`

Checks if any value is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean)(by using the `isBoolean()`) equal to `true`.

{% code title="is-true.func.ts" %}
```typescript
const isTrue = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is true =>
  callback(isBoolean(value) ? value.valueOf() === true : false, value, payload);
```
{% endcode %}

### Generic type variables

### Parameters

### Return type

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) that is equal to `true`.

### Example usage

```typescript
// Example usage
import { isTrue } from '@angular-package/type';

```

