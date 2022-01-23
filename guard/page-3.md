# ★ guardTrue()

### `guardTrue()`

Description

{% code title="guard-true.func.ts" %}
```typescript
const guardTrue = <Payload extends object>(
  value: true,
  callback?: ResultCallback<true, Payload>,
  payload?: Payload
): value is true => isTrue(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](page-3.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-3.md#payload-payload) optional parameter of the [`guardObject()`](page-3.md#guardobject) function from which it captures its value.

### Parameters

### Return type

### Returns

### Example usage

```typescript
// Example usage.
import {  } from '@angular-package/type';


```

