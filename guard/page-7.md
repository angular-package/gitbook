# guardDefined()

### `guardDefined()`

Description

{% code title="guard-defined.func.ts" %}
```typescript
const guardDefined = <Type, Payload extends object = object>(
  value: Defined<Type>,
  callback?: ResultCallback<Defined<Type>, Payload>,
  payload?: Payload
): value is Defined<Type> => isDefined(value, callback, payload);
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

