# isObjectKeyIn()

## `isObjectKeyIn()`

Checks if any value is an `object` by using the `isObject()` function with a key of the `PropertyKey` in it(or its prototype chain) by using the `in` operator.

Use `isObjectKeyIn()` or `is.objectKeyIn()` to check if **any** value is an \[`object`]\[js-object] function with a key of the `PropertyKey` in it(or its prototype chain) by using the \[`in`]\[js-in-operator] operator.

{% code title="is-object-key-in.func.ts" %}
```typescript
const isObjectKeyIn = <Obj = object, Payload extends object = object>(
  value: any,
  key: PropertyKey,
  callback: ResultCallback<any, { key: typeof key } & Payload> = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(isObject(value) ? key in value : false, value, {
    ...payload,
    key,
  } as any);
```
{% endcode %}

### Generic type variables



A generic type variable `Obj` indicates the type of `value` parameter by default `object` via the return type `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkeyin.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectkeyin.md#payload-payload) optional parameter of the [`isObjectKeyIn()`](isobjectkeyin.md#isobjectkeyin) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

The value of any type to check against an `object` that contains(or its prototype chain) a key from a given `key`.

#### `key: PropertyKey`

A property key to check if a given `value` contains(or its prototype chain).

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkeyin.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkeyin.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type variable `Obj` by default equal to the `object`.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is an `object` that contains(or its prototype chain) a given `key`.

### Example usage

```typescript
// Example usage.
import { isObjectKeyIn } from '@angular-package/type';

const NUMBER = 10304050;
const STRING = '!@#$%^&*()abcdefghijklmnoprstuwyz';
const SYMBOL_NUMBER: unique symbol = Symbol(NUMBER);
const SYMBOL_STRING: unique symbol = Symbol(STRING);

class Class {

   1030405027 = 'my new number';
   5 = 'my number';

   firstName = 'My name';
   surname = 'Surname';

   x = NUMBER;
   y = STRING;

   get [NUMBER](): number {
     return this.x;
   }
   get [STRING](): string {
     return this.y;
   }

   get [SYMBOL_NUMBER](): number {
     return this.x;
   }

   get [SYMBOL_STRING](): string {
     return this.y;
   }
}

const CLASS = new Class();

// One of the differences between `in` operator and the `hasOwnProperty()`
// method is that it finds a getter key
isObjectKeyIn(CLASS, SYMBOL_NUMBER); // true
isObjectKeyIn(CLASS, SYMBOL_STRING); // true
```
