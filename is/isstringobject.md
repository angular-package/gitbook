# isStringObject()

## `isStringObject()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value is of the type obtained from its [`object` class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'string'` or an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type, and an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

{% code title="is-string-object.func.ts" %}
```typescript
const isStringObject = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is String =>
  callback(
    (typeOf(value) === 'string' || typeof value === 'object') &&
    value instanceof String,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstringobject.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isstringobject.md#payload-payload) optional parameter of the [`isStringObject()`](isstringobject.md#isstringobject) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isstringobject.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isstringobject.md#payloadextendsobject) with optional properties from the provided [`payload`](isstringobject.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstringobject.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstringobject.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is String`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isstringobject.md#value-any) is [`String`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isstringobject.md#value-any) is an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

### Example usage

```typescript
// Example usage.
import { isStringObject } from '@angular-package/type';

isStringObject('age'); // Returns `false` as `value is String`
isStringObject(new String('age')) // Returns `true` as `value is String`
```
