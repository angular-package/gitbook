# isObjectKeyIn()

## `isObjectKeyIn()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) by using the [`isObject()`](isobject.md) function with a key of the `PropertyKey` in it(or its prototype chain) by using the [`in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) operator.

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

#### <mark style="color:green;">`Obj`</mark>`=`<mark style="color:green;">`object`</mark>

A generic type variable `Obj` indicates the type of [`value`](isobjectkeyin.md#value-any) parameter by default [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) via the [return type](isobjectkeyin.md#return-type) `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkeyin.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectkeyin.md#payload-payload) optional parameter of the [`isObjectKeyIn()`](isobjectkeyin.md#isobjectkeyin) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to check against an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that contains(or its prototype chain) a key from a given [`key`](isobjectkeyin.md#key-propertykey).

#### `key: PropertyKey`

A property key to check if a given [`value`](isobjectkeyin.md#value-any) contains(or its prototype chain).

#### `callback: ResultCallback<any, { key: typeof key } Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isobjectkeyin.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isobjectkeyin.md#payloadextendsobject) with optional properties from the provided [`payload`](isobjectkeyin.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](isobjectkeyin.md#callback-resultcallback-less-than-any-key-typeof-key-payload-greater-than) function consists of the [`key`](isobjectkeyin.md#key-propertykey) property given in parameter of the core function, and it can't be overwritten by the given [`payload`](isobjectkeyin.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkeyin.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkeyin.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isobjectkeyin.md#value-any) is a generic type variable [`Obj`](isobjectkeyin.md#obj-object) by default equal to the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isobjectkeyin.md#value-any) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that contains(or its prototype chain) a given [`key`](isobjectkeyin.md#key-propertykey).

## Example usage

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
