# isStringIncludesSome()

### `isStringIncludesSome()`

Checks if any value is a `string` type or an instance of `String` by using `isString()` that includes some of the specified words/sentences.

{% code title="is-string-inludes-some.func.ts" %}
```typescript
const isKey = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is PropertyKey =>
  callback(
    isStringType(value) || isNumberType(value) || isSymbol(value),
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

The return value is a `boolean` indicating whether the provided `value` is a `string` type or an instance of `String` that includes some of the specified words/sentences.

### Example usage

```typescript
// Example usage
import { isStringIncludesSome } from '@angular-package/type';

```

