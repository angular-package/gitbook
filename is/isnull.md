# isNull()

### `isNull()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'null'` or an `object` type that is equal to `null`.

{% code title="is-null.func.ts" %}
```typescript
const isNull = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is null =>
  callback(
    (typeOf(value) === 'null' || typeof value === 'object') && value === null,
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
import { isNull } from '@angular-package/type';

```

