# isNumberType()

## `isNumberType()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type and finite by using the [`Number.isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isFinite) method and valid by the [`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isNaN) method.

{% code title="is-number-type.func.ts" %}
```typescript
const isNumberType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is number =>
  callback(
    typeof value === 'number' && Number.isFinite(value) && !Number.isNaN(value),
    value,
    payload
  );
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-number-type.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnumbertype.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnumbertype.md#payload-payload) optional parameter of the [`isNumberType()`](isnumbertype.md#isnumbertype) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnumbertype.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnumbertype.md#payloadextendsobject) with optional properties from the provided [`payload`](isnumbertype.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnumbertype.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnumbertype.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is number`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the provided [`value`](isnumbertype.md#value-any) is a [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isnumbertype.md#value-any) is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type.

## Example usage

```typescript
// Example usage.
import { isNumberType } from '@angular-package/type';

isNumberType(10304050); // true
isNumberType(Number(10304050)); // true
isNumberType(new Number(10304050)); // false
```
