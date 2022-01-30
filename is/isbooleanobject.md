# isBooleanObject()

## `isBooleanObject()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is of the type obtained from its [`object` class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'boolean'` or an `object` type, and an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) and equal `true` or `false`.

{% code title="is-boolean-object.func.ts" %}
```typescript
const isBooleanObject = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Boolean =>
  callback(
    (typeOf(value) === 'boolean' || typeof value === 'object') &&
    value instanceof Boolean &&
    (value.valueOf() === true || value.valueOf() === false),
    value,
    payload
  );
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-boolean-object.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isbooleanobject.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isbooleanobject.md#payload-payload) optional parameter of the [`isBooleanObject()`](isbooleanobject.md#isbooleanobject) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isbooleanobject.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isbooleanobject.md#payloadextendsobject) with optional properties from the provided [`payload`](isbooleanobject.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isbooleanobject.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isbooleanobject.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Boolean`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isbooleanobject.md#value-any) is [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isbooleanobject.md#value-any) is an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

## Example usage

```typescript
// Example usage.
import { isBooleanObject } from '@angular-package/type';

isBooleanObject(false); // false
isBooleanObject(new Boolean(false)); // true
```
