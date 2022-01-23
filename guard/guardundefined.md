# guardUndefined()

## `guardUndefined()`

Guards the value to be [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="guard-undefined.func.ts" %}
```typescript
const guardUndefined = <Payload extends object>(
  value: undefined,
  callback?: ResultCallback<undefined, Payload>,
  payload?: Payload
): value is undefined => isUndefined(value, callback, payload);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-undefined.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardundefined.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardundefined.md#payload-payload) optional parameter of the [`guardObject()`](guardundefined.md#guardobject) function from which it captures its value.

### Parameters

#### `value: undefined`

The value of an [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined) type to guard.

#### `callback?: ResultCallback<undefined, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardundefined.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardundefined.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardundefined.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is`<mark style="color:green;">`undefined`</mark>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardundefined.md#value-undefined) is [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

### Example usage

```typescript
// Example usage.
import { guardUndefined } from '@angular-package/type';

const UNDEFINED: undefined = undefined;

guardUndefined(UNDEFINED); // true; 
guardUndefined('x'); // false; type error
guardUndefined(5); // false; type error

const tracker = {
  error: 'sentry',
};

const undefinedCallback = <Type, Payload>(
  result: boolean,
  value: Type,
  payload?: typeof tracker & Payload
) => {
  if (payload?.error === 'sentry') {
    // ...
  }
  value; // 5
  result; // false
  /*
  payload {
      "name": "guardUndefined",
      "error": "sentry"
    }
  */
  return result;
};

const gUndefined = (value: undefined): value is undefined =>
  guardUndefined(value, undefinedCallback, tracker);

gUndefined(5 as any); // false
```
