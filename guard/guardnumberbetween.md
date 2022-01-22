# guardNumberBetween()

### `guardNumberBetween()`

Description

{% code title="guard-number-between.func.ts" %}
```typescript
const guardNumberBetween = <
  Type extends AnyNumber,
  Min extends number,
  Max extends number,
  Payload extends object = object
>(
  value: Type,
  range: MinMax<Min, Max> | Min | Max,
  callback?: ResultCallback<Type, MinMax<Min, Max> & Payload>,
  payload?: Payload
): value is NumberBetween<Min, Max, Type> =>
  isNumberBetween(value, range, callback, payload);
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

