# isRegExp()

### `isRegExp()`

Checks if any value is a regular expression of the type obtained from its `Object.prototype` equal to `'regexp'`, or an `object` type, and an instance of `RegExp`.

{% code title="is-reg-exp.func.ts" %}
```typescript
const isRegExp = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is RegExp =>
  callback(
    (typeOf(value) === 'regexp' || typeof value === 'object') &&
    value instanceof RegExp,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isregexp.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isregexp.md#payload-payload) optional parameter of the [`isRegExp()`](isregexp.md#isregexp) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isregexp.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isregexp.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isRegExp } from '@angular-package/type';

```

