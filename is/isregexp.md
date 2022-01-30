# isRegExp()

## `isRegExp()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular\_Expressions) of the type obtained from its [`object` class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'regexp'`, or an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type, and an instance of [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp).

{% code title="is-reg-exp.func.ts" %}
```typescript
const isRegExp = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is RegExp =>
  callback(
    (typeOf(value) === 'regexp' || typeof value === 'object') &&
      value instanceof RegExp,
    value,
    payload
  );
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-regexp.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isregexp.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isregexp.md#payload-payload) optional parameter of the [`isRegExp()`](isregexp.md#isregexp) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isregexp.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isregexp.md#payloadextendsobject) with optional properties from the provided [`payload`](isregexp.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isregexp.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isregexp.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is RegExp`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isregexp.md#value-any) is a regular expression of a [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isregexp.md#value-any) is a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular\_Expressions).

## Example usage

```typescript
// Example usage.
import { isRegExp } from '@angular-package/type';

isRegExp(/[^a-z]/g); // true; The return type `value is RegExp`
```
