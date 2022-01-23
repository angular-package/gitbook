# ★ guardTrue()

## `guardTrue()`

Guards the value to be [`true`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

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

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../type/resultcallback.md#payload-payload) of the supplied [`callback`](page-3.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-3.md#payload-payload) optional parameter of the [`guardTrue()`](page-3.md#guardtrue) function from which it captures its value.

### Parameters

#### `value: true`

The value of [`true`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type to guard.

#### `callback?: ResultCallback<null, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-3.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-3.md#payloadextendsobject-object) is assigned to the [`payload`](../type/resultcallback.md#payload-payload) of the given [`callback`](page-3.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is`<mark style="color:green;">`true`</mark>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement [`value`](page-3.md#value-true) is [`true`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](page-3.md#value-true) is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to [`true`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

### Example usage

```typescript
// Example usage.
import { guardTrue } from '@angular-package/type';

const valTrue = true as any;
const valFalse = false;

guardTrue(valTrue); // false, value is false
guardTrue(valFalse); // true, value is false
guardTrue(new Boolean(valTrue) as any); // false, value is false
guardTrue(new Boolean(valFalse) as any); // true, value is false
```
