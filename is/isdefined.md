# isDefined()

## `isDefined()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is not an [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined) type and is not equal to [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined).

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

A generic type variable indicates the captured type of the given [`value`](isdefined.md#value-type) except [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined), which changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never) via the [return type](isdefined.md#return-type) and the [`value`](../types/resultcallback.md#value-value) type of the supplied [`callback`](isdefined.md#callback-resultcallback-less-than-type-payload-greater-than) function.&#x20;

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isdefined.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isdefined.md#payload-payload) optional parameter of the [`isDefined()`](isdefined.md#isdefined) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](isdefined.md#type), by default of type captured from itself, to check.

#### `callback: ResultCallback<Type, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isdefined.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isdefined.md#payloadextendsobject) with optional properties from the provided [`payload`](isdefined.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isdefined.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isdefined.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Defined<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isdefined.md#value-type) is a generic type [`Defined`](../types/defined.md) that takes a generic type variable [`Type`](isdefined.md#type) of value by default equal to the type captured from the supplied [`value`](isdefined.md#value-type) parameter excepts [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) which changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isdefined.md#value-type) is defined, not [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined).

## Example usage

```typescript
// Example usage.
import { isDefined } from '@angular-package/type';

const UNDEFINED = undefined;
let defined;

isDefined(UNDEFINED); // Returns `false` as `value is never`
isDefined(defined); // Returns `false` as `value is never`
isDefined(27); // Returns `true` as `value is number`
isDefined('age'); // Returns `true` as `value is string`
```

### Callback and payload parameters

```typescript
// Callback and payload parameters example usage.
import { isDefined } from '@angular-package/type';

isDefined('age', (result, value, payload) => {
  value // 'age'
  if (payload) {
    result // Returns `true`
    payload.notDefined // Returns `false`
  }
  return result;
}, { notDefined: false }); // Returns `true` as `value is string`
```

