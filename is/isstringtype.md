# isStringType()

### `isStringType()`

Checks if any value is one of the `string`, `number`, or `symbol` type.

{% code title="is-string-type.func.ts" %}
```typescript
const isStringType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is string =>
  callback(typeof value === 'string', value, payload);
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
import { isStringType } from '@angular-package/type';

```

