# isUndefined()

## ​`isUndefined()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined) type.

{% code title="is-undefined.func.ts" %}
```typescript
const isUndefined = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is undefined => callback(typeof value === 'undefined', value, payload);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-undefined.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isundefined.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isundefined.md#payload-payload) optional parameter of the [`isUndefined()`](isundefined.md#isundefined) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isundefined.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isundefined.md#payloadextendsobject) with optional properties from the provided [`payload`](isundefined.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isundefined.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isundefined.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is undefined`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isundefined.md#value-any) is [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined).

## Example usage

```typescript
// Example usage.
import { isUndefined } from '@angular-package/type';

let age;
isUndefined(age); // Returns `true` as `value is undefined`
isUndefined(27); // Returns `false` as `value is undefined`
```
