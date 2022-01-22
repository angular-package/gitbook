# ★ guardFalse()

## `guardFalse()`

Guards the provided [`value`](page-7-1.md#value-false) to be `false`.

{% code title="guard-false.func.ts" %}
```typescript
const guardFalse = <Payload extends object>(
  value: false,
  callback?: ResultCallback<false, Payload>,
  payload?: Payload
): value is false => isFalse(value, callback, payload);
```
{% endcode %}

Code on [**GitHub**](https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-false.func.ts)****

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](page-7-1.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-7-1.md#payload-payload) optional parameter of the [`guardFalse()`](page-7-1.md#guardfalse) function from which it captures its value.

### Parameters

#### `value: false`

The value of `false` type to guard.

#### `callback?: ResultCallback<false, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-7-1.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-7-1.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](page-7-1.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is false`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement `value` is `false`.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](page-7-1.md#value-date) is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `false`.

### Example usage

```typescript
// Example usage.
import { guardFalse } from '@angular-package/type';

const valTrue = true as any;
const valFalse = false;

guardFalse(valTrue); // false, value is false
guardFalse(valFalse); // true, value is false
guardFalse(new Boolean(valTrue) as any); // false, value is false
guardFalse(new Boolean(valFalse) as any); // true, value is false
```
