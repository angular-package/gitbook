# isObject()

## `isObject()`

Checks if any value is an `object` type or the type obtained from its `Object.prototype` equal to `'object'`, and an instance of `Object`.

Use `isObject()` or `is.object()` to check if **any** value is an \[`object`]\[js-object] type or the type obtained from its `Object.prototype` equal to `'object'`, and an instance of \[`Object`]\[js-object].

{% code title="is-object.func.ts" %}
```typescript
const isObject = <Obj = object, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    (typeof value === 'object' || typeOf(value) === 'object') &&
    value instanceof Object,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

Obj

A generic type variable `Obj` indicates the type of `value` parameter via the return type `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobject.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobject.md#payload-payload) optional parameter of the [`isObject()`](isobject.md#isobject) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobject.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobject.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type variable `Obj` by default equal to `object`.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is an \[`object`]\[js-object].

### Example usage

```typescript
// Example usage.
import { isObject } from '@angular-package/type';

const x = 10304050;
const NUMBER = 10304050;
const STRING = '!@#$%^&*()abcdefghijklmnoprstuwyz';
const SYMBOL_NUMBER: unique symbol = Symbol(NUMBER);
const SYMBOL_STRING: unique symbol = Symbol(STRING);

interface ObjectOne {
  'key as string'?: boolean;
  1030405027?: string;
  5?: string;
  [NUMBER]: number;
  [STRING]: string;
  [SYMBOL_NUMBER]?: string;
  [SYMBOL_STRING]?: number;
  x: number;
}

const OBJECT_ONE: ObjectOne = {
  'key as string': true,
  1030405027: 'key is number',
  5: 'key is also number',
  [NUMBER]: NUMBER,
  [STRING]: 'key is string',
  [SYMBOL_NUMBER]: 'key is symbol number',
  [SYMBOL_STRING]: 6,
  x: 3000
};

isObject(OBJECT_ONE); // true
```
