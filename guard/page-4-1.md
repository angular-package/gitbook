# guardKey()

## `guardKey()`

Guards the value to be one of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number), or [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type.

{% code title="guard-key.func.ts" %}
```typescript
const
  value: Key,
  callback?: ResultCallback<Key, Payload>,
  payload?: Payload
): value is Key => isKey(value, callback, payload);
```
{% endcode %}

Code on [**GitHub**](https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-key.func.ts).

### Generic type variables

#### <mark style="color:green;">**`Key`**</mark>**`extends`**<mark style="color:green;">**`PropertyKey`**</mark>

A generic type variable `Key` constrained by `PropertyKey` indicates captured type of the given [`value`](page-4-1.md#value-type) via the [return type](page-4-1.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](page-4-1.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](page-4-1.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-4-1.md#payload-payload) optional parameter of the [`guardKey()`](page-4-1.md#guardkey) function from which it captures its value.

### Parameters

#### `value: Key`

The value of generic type variable [`Key`](page-4-1.md#keyextendspropertykey) to guard.

#### `callback?: ResultCallback<Key, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-4-1.md#payloadextendsobject-object) with optional properties from the provided [`payload`](page-4-1.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-4-1.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](page-4-1.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Key`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](page-4-1.md#value-key) is generic type variable [`Key`](page-4-1.md#keyextendspropertykey).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](page-4-1.md#value-key) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number), or [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol).

## Example usage

```typescript
// Example usage.
import { guardKey } from '@angular-package/type';

guardKey('string key'); // true, value is PropertyKey
guardKey(27); // true, value is PropertyKey
guardKey(Symbol('string key')); // true, value is PropertyKey
guardKey(Symbol(27)); // true, value is PropertyKey

guardKey(new String('string key') as any); // false, value is PropertyKey
guardKey(new Number(27) as any); // false, value is PropertyKey
```
