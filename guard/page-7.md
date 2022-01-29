# guardDefined()

## `guardDefined()`

Guards the value to be defined, not [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="guard-defined.func.ts" %}
```typescript
const guardDefined = <Type, Payload extends object = object>(
  value: Defined<Type>,
  callback?: ResultCallback<Defined<Type>, Payload>,
  payload?: Payload
): value is Defined<Type> => isDefined(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

A generic type variable `Type` indicates captured type of the given [`value`](page-7.md#value-defined-less-than-type-greater-than) via the [return type](page-7.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](page-7.md#callback-resultcallback-less-than-defined-less-than-type-greater-than-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](page-7.md#callback-resultcallback-less-than-defined-less-than-type-greater-than-payload-greater-than) function and [`payload`](page-7.md#payload-payload) optional parameter of the [`guardDefined()`](page-7.md#guarddefined) function from which it captures its value.

### Parameters

#### `value: Defined<Type>`

The value of generic type [`Defined<Type>`](../types/defined.md), [never](https://www.typescriptlang.org/docs/handbook/basic-types.html#never) undefined type captured from itself to guard against [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined).

#### `callback?: ResultCallback<Defined<Type>, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](page-7.md#value-defined-less-than-type-greater-than) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](page-7.md#payloadextendsobject-object) with optional properties from the provided [`payload`](page-7.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-7.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](page-7.md#callback-resultcallback-less-than-defined-less-than-type-greater-than-payload-greater-than) function.

### Return type

#### `value is Defined<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](page-7.md#value-defined-less-than-type-greater-than) is a generic type [`Defined`](../types/defined.md) that takes a generic type variable [`Type`](page-7.md#type) of value by default equal to the type captured from the supplied [`value`](page-7.md#value-defined-less-than-type-greater-than) parameter excepts [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) which changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](page-7.md#value-defined-less-than-type-greater-than) is defined.

## Example usage

```typescript
// Example usage.
import { guardDefined } from '@angular-package/type';

let letFirstName = 'my name';
guardDefined(letFirstName); // true; return type `value is string`

const firstName = 'my const name';
guardDefined(firstName); // true; return type `value is string`
```
