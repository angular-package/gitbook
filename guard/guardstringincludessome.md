# guardStringIncludesSome()

### `guardStringIncludesSome()`

Description

{% code title="guard-string-includes-some.func.ts" %}
```typescript
const guardStringIncludesSome = <
  Type extends AnyString,
  Payload extends object = object
>(
  value: Type,
  includes: string[],
  callback: ResultCallback<
    Type,
    { includes: typeof includes } & Payload
  > = resultCallback,
  payload?: Payload
): value is Type => isStringIncludesSome(value, includes, callback, payload);
```
{% endcode %}

### Generic type variables

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage.
import {  } from '@angular-package/type';


```

