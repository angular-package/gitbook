# isNotUndefined()

## `isNotUndefined()`

Checks if the [`value`](isnotundefined.md#value-type) is **not** the type obtained from its [object class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'undefined'`, **not** an [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined) type and **not** equal to [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="is-not-undefined.func.ts" %}
```typescript
const isNotUndefined = <Type, Payload extends object = object>(
  value: Type,
  callback: ResultCallback<Type, Payload> = resultCallback,
  payload?: Payload
): value is Defined<Type> =>
  callback(
    typeOf(value) !== 'undefined' &&
    typeof value !== 'undefined' &&
    value !== undefined,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

A generic type variable `Type` indicates the captured type of the given [`value`](isnotundefined.md#value-array-less-than-type-greater-than) via the [return type](isnotundefined.md#return-type) `value is Defined<Type>` and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isnotundefined.md#callback-resultcallback-less-than-array-less-than-type-greater-than-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnotundefined.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnotundefined.md#payload-payload) optional parameter of the [`isNotUndefined()`](isnotundefined.md#isnotundefined) function from which it captures its value.

### Parameters

#### `value: Type`

The `value` of generic type variable [`Type`](isnotundefined.md#type), by default of the type captured from itself to check.

#### `callback: ResultCallback<Type, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnotundefined.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnotundefined.md#payloadextendsobject) with optional properties from the provided [`payload`](isnotundefined.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnotundefined.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnotundefined.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Defined<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isnotundefined.md#value-type) is a generic type [`Defined`](../types/defined.md) that takes a generic type variable [`Type`](isnotundefined.md#type) of value by default equal to the type captured from the supplied [`value`](isnotundefined.md#value-type) parameter excepts [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) which changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isnotundefined.md#value-type) is **not** [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { is } from '@angular-package/type';

interface Config {
  a?: string;
  b?: string;
}
const config: Config = {
  a: 'x',
  b: 'y'
};

function configFunction(value: string): string {
  return '';
}

if (is.not.undefined(config.a)) {
  configFunction(config.a);
}
```
