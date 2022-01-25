# isKey()

### `isKey()`

Checks if any value is one of the `string`, `number`, or `symbol` type.

{% code title="is-key.func.ts" %}
```typescript
const isKey = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is PropertyKey =>
  callback(
    isStringType(value) || isNumberType(value) || isSymbol(value),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](iskey.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](iskey.md#payload-payload) optional parameter of the [`isKey()`](iskey.md#iskey) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](iskey.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](iskey.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isKey } from '@angular-package/type';

```

