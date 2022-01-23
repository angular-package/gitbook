# guardNull()

## `guardNull()`

Guards the value to be [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).

{% code title="guard-null.func.ts" %}
```typescript
const guardNull = <Payload extends object>(
  value: null,
  callback?: ResultCallback<null, Payload>,
  payload?: Payload
): value is null => isNull(value, callback, payload);
```
{% endcode %}

Code on [**GitHub**](https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-null.func.ts).

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../type/resultcallback.md#payload-payload) of the supplied [`callback`](page-9.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-9.md#payload-payload) optional parameter of the [`guardNull()`](page-9.md#guardnull) function from which it captures its value.

### Parameters

#### `value: null`

The value of [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null) type to guard.

#### `callback?: ResultCallback<null, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-9.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-9.md#payloadextendsobject-object) is assigned to the [`payload`](../type/resultcallback.md#payload-payload) of the given [`callback`](page-9.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is null`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](page-9.md#value-null) is [`null`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](page-9.md#value-null) is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).

### Example usage

```typescript
// Example usage.
import { guardNull } from '@angular-package/type';

guardNull(null); // true, value is null
guardNull(undefined as any); // false, value is null
```
