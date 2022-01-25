# isObjectKey()

### `isObjectKey()`

Checks if any value is an `object` by using the `isObject()` function with its key of the `PropertyKey` type.

{% code title="is-object-key.func.ts" %}
```typescript
const isObjectKey = <
  Obj extends object,
  Payload extends object = object
>(
  value: any,
  key: PropertyKey,
  callback: ResultCallback<Obj, { key: typeof key } & Payload> = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) ? {}.hasOwnProperty.call(value, key) : false,
    value,
    { ...payload, key } as any
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkey.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectkey.md#payload-payload) optional parameter of the [`isObjectKey()`](isobjectkey.md#isobjectkey) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkey.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkey.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isObjectKey } from '@angular-package/type';

```

