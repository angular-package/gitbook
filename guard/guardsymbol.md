# guardSymbol()

### `guardSymbol()`

Description

{% code title="guard-symbol.func.ts" %}
```typescript
const guardSymbol = <Payload extends object>(
  value: symbol,
  callback?: ResultCallback<symbol, Payload>,
  payload?: Payload
): value is symbol => isSymbol(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardsymbol.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardsymbol.md#payload-payload) optional parameter of the [`guardObject()`](guardsymbol.md#guardobject) function from which it captures its value.

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage.
import {  } from '@angular-package/type';


```

