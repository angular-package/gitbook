# guardInstance()

### `guardInstance()`

Description

{% code title="guard-instance.func.ts" %}
```typescript
const guardInstance = <
  Obj extends object,
  Payload extends object = object
>(
  value: Obj,
  constructor: Constructor<Obj>,
  callback?: ResultCallback<Obj, { ctor: typeof constructor } & Payload>,
  payload?: Payload
): value is Obj => isInstance(value, constructor, callback, payload);
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

