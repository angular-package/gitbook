# guardPrimitive()

### `guardPrimitive()`

Description

{% code title="guard-primitive.func.ts" %}
```typescript
const guardPrimitive = <
  Type extends Primitive,
  Payload extends object = object
>(
  value: Type,
  type?: Primitives,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isPrimitive(value, type, callback, payload);
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

