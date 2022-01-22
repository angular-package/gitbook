# guardStringLength()

### `guardStringLength()`

Description

{% code title="guard-string-length.func.ts" %}
```typescript
const guardStringLength = <
  Type extends AnyString,
  Min extends number,
  Max extends number,
  Payload extends object = object
>(
  value: Type,
  length: MinMax<Min, Max> | Min | Max,
  callback?: ResultCallback<Type, MinMax<Min, Max> & Payload>,
  payload?: Payload
): value is StringOfLength<Min, Max, Type> =>
  isStringLength(value, length, callback, payload);
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

