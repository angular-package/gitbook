# guardUndefined()

### `guardUndefined()`

Description

{% code title="guard-undefined.func.ts" %}
```typescript
const guardUndefined = <Payload extends object>(
  value: undefined,
  callback?: ResultCallback<undefined, Payload>,
  payload?: Payload
): value is undefined => isUndefined(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardundefined.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardundefined.md#payload-payload) optional parameter of the [`guardObject()`](guardundefined.md#guardobject) function from which it captures its value.

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage.
import {  } from '@angular-package/type';


```

