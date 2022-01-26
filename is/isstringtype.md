# isStringType()

## `isStringType()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

{% code title="is-string-type.func.ts" %}
```typescript
const isStringType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is string =>
  callback(typeof value === 'string', value, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstringtype.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isstringtype.md#payload-payload) optional parameter of the [`isStringType()`](isstringtype.md#isstringtype) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isstringtype.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isstringtype.md#payloadextendsobject) with optional properties from the provided [`payload`](isstringtype.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstringtype.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstringtype.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is string`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isstringtype.md#value-any) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { isStringType } from '@angular-package/type';

isStringType('age'); // Returns `true` as `value is string`
isStringType(new String('age')) // Returns `false` as `value is string`
```
