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

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by object indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

### Return type

### Returns

The return value is a `boolean` indicating whether the provided `value` is a `string` type or an instance of `String`.

### Example usage

```typescript
// Example usage.
import { isString } from '@angular-package/type';

```

