# ★ isNumber()

## `isNumber()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type, or the type obtained from its [`object` class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'number'` or an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type and an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number). The value is also checked by the [`Number.isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isFinite) method to determine whether it's finite and is validated by the [`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isNaN) method.

{% code title="is-number.func.ts" %}
```typescript
const isNumber = <
  Type extends AnyNumber = number,
  Payload extends object = object
>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Type =>
  callback(
    (typeof value === 'number' ||
      ((typeOf(value) === 'number' || typeof value === 'object') &&
        value instanceof Number)) &&
      !Number.isNaN(value.valueOf()) &&
      Number.isFinite(value.valueOf()),
    value,
    payload
  );xz
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Type`</mark>`extends`<mark style="color:green;">`AnyNumber`</mark>`=`<mark style="color:green;">`number`</mark>

A generic type variable `Type` constrained by [`AnyNumber`](../types/anynumber.md) indicates the number type of the given [`value`](isnumber.md#value-any) via the [return type](isnumber.md#return-type), by default [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional  [`payload`](../types/resultcallback.md#payload-payload) parameter of the supplied [`callback`](isnumber.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnumber.md#payload-payload) optional parameter of the [`isNumber()`](isnumber.md#isnumber) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnumber.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnumber.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isnumber.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnumber.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnumber.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isnumber.md#value-any) is a generic type variable [`Type`](isnumber.md#type) constrained by [`AnyNumber`](../types/anynumber.md) by default of [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isnumber.md#value-any) is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

## Example usage

```typescript
// Example usage.
import { isNumber } from '@angular-package/type';

isNumber(10304050); // true, value is number
isNumber(Number(10304050)); // true, value is number
isNumber(new Number(10304050)); // true, value is number
isNumber<Number>(new Number(10304050)); // true, value is Number
```
