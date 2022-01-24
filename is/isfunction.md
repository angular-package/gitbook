# isFunction()

### `isFunction()`

Checks if any value is a [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) type or the type obtained from its `Object.prototype` equal to `'function'` and an instance of [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions). It also denies it's a [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) by using `regexp` on the obtained string from its `Function.prototype`.

{% code title="is-function.func.ts" %}
```typescript
const isFunction = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Function =>
  callback(
    typeof value === 'function' ||
    (typeOf(value) === 'function' && (value as any) instanceof Function)
    ? /class/.test(Function.prototype.toString.call(value).slice(0, 5)) ===
        false
    : false,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of the `payload` parameter of the main function from which it gets its value and `payload` parameter of a given `callback` function [`ResultCallback`](../types/resultcallback.md) type.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](isfunction.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of generic type variable [`Payload`](isfunction.md#payloadextendsobject) is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is Function`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the `value` is a [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).

### Example usage

```typescript
// Example usage.
import { isFunction } from '@angular-package/type';

class Class { x = 5; }
const FUNC = (x: number): any => x + 5;

isFunction(Class); // Returns `false` as `value is typeof Class`, it must not be a `class`.
isFunction(FUNC); // Returns `true` as `value is (x: number) => any`
isFunction(() => 5); // Returns `true` as `value is () => 5`

// Example usage with callback and payload.
isFunction(() => 5, (result, value, payload) => {
  value // Returns `() => 5`
  if (payload) {
    payload.number // Returns `true`
  }
  return result;
}, { number: true }); // Returns `true` as `value is () => 5`
```
