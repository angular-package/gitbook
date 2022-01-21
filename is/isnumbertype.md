# isNumberType()

### `isNumberType()`

Checks if any value is a `number` type and is checked by the `Number.isFinite()` method to determine whether it's finite and is validated by the `Number.isNaN()` method.

{% code title="is-number-type.func.ts" %}
```typescript
const isNumberType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is number =>
  callback(
    typeof value === 'number' && Number.isFinite(value) && !Number.isNaN(value),
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
import { isNumberType } from '@angular-package/type';

```

