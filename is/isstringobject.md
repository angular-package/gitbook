# isStringObject()

### `isStringObject()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'string'` or an `object` type, and an instance of `String`.

{% code title="is-string-object.func.ts" %}
```typescript
const isStringObject = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is String =>
  callback(
    (typeOf(value) === 'string' || typeof value === 'object') &&
    value instanceof String,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isStringObject } from '@angular-package/type';

```

