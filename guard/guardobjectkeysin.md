# guardObjectKeysIn()

### `guardObjectKeysIn()`

Description

{% code title="guard-object-keys-in.func.ts" %}
```typescript
const guardObjectKeysIn = <
  Obj extends object,
  Key extends keyof Obj,
  Payload extends object = object
>(
  value: Obj,
  keys: Key[],
  callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>,
  payload?: Payload
): value is Obj => isObjectKeysIn(value, keys, callback, payload as any);
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

