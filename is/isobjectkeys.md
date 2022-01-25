# isObjectKeys()

### `isObjectKeys()`

Checks if any value is an `object` by using the `isObject()` function with some of its keys or some groups of its keys of the `PropertyKey` type.

{% code title="is-object-keys.func.ts" %}
```typescript
const isObjectKeys = <Obj = object, Payload extends object = object>(
  value: any,
  keys: PropertyKey[],
  callback: ResultCallback<
    any,
    { keys: typeof keys } & Payload
  > = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) && isArray(keys)
    ? keys.every((key) => ({}.hasOwnProperty.call(value, key)))
    : false,
    value,
    { ...payload, keys } as any
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkeys.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectkeys.md#payload-payload) optional parameter of the [`isObjectKeys()`](isobjectkeys.md#isobjectkeys) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkeys.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkeys.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isObjectKeys } from '@angular-package/type';

```

