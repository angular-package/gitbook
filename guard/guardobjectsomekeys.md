# guardObjectSomeKeys()

## `guardObjectSomeKeys()`

Description

{% code title="guard-object-some-keys.func.ts" %}
```typescript
const guardObjectSomeKeys = <
  Obj extends object,
  Payload extends object = object
>(
  value: Obj,
  keys: (keyof Obj | Array<keyof Obj>)[],
  callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>,
  payload?: Payload
): value is Obj => isObjectSomeKeys(value, keys, callback, payload as any);
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

