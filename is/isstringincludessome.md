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

### Parameters

### Return type

### Returns

The return value is a `boolean` indicating whether the provided `value` is a `string` type or an instance of `String` that includes some of the specified words/sentences.

### Example usage

```typescript
// Example usage
import { isStringIncludesSome } from '@angular-package/type';

```

