# guardObject()

### `guardObject()`

Description

{% code title="guard-object.func.ts" %}
```typescript
const guardObject = <
  Obj extends object,
  Payload extends object = object
>(
  value: Obj,
  callback?: ResultCallback<Obj, Payload>,
  payload?: Payload
): value is Obj => isObject(value, callback, payload);
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

