# isDefined()

### `isDefined()`

Checks if any value is not an [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined) type and is not equal to [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined).

{% code title="is-defined.func.ts" %}
```typescript
const isDefined = <Type, Payload extends object = object>(
  value: Type,
  callback: ResultCallback<Type, Payload> = resultCallback,
  payload?: Payload
): value is Defined<Type> =>
  callback(typeof value !== 'undefined' && value !== undefined, value, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

The `Type` generic type variable indicates captured type of the given `value` via the return type except [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined), which changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of the `payload` parameter of the main function from which it gets its value and `payload` parameter of a given `callback` function [`ResultCallback`](../types/resultcallback.md) type.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](isdefined.md#type), by default of type captured from the provided `value`, to check.

#### `callback: ResultCallback<Type, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is Defined<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the `value` is a generic type [`Defined`](../types/defined.md) that takes a generic type variable [`Type`](isdefined.md#type) of value by default equal to the type captured from the supplied `value` parameter excepts `undefined` which changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is defined, not [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined).

### Example usage

```typescript
// Example usage.
import { isDefined } from '@angular-package/type';

const UNDEFINED = undefined;
let defined;

isDefined(UNDEFINED); // Returns `false` as `value is never`
isDefined(defined); // Returns `false` as `value is never`
isDefined(27); // Returns `true` as `value is number`
isDefined('age'); // Returns `true` as `value is string`

// Example usage with callback and payload.
isDefined('age', (result, value, payload) => {
  value // 'age'
  if (payload) {
    result // Returns `true`
    payload.notDefined // Returns `false`
  }
  return result;
}, { notDefined: false }); // Returns `true` as `value is string`
```
