# isObjectKey()

## `isObjectKey()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object)(by using the [`isObject()`](isobject.md)) function with its **key** of the `PropertyKey` type.

{% hint style="info" %}
The function uses the [`hasOwnProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/hasOwnProperty) method of [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) to find enumerable and non-enumerable `PropertyKey` as string, number, symbol unlike [`Object.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/keys) that finds only [enumerable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability\_and\_ownership\_of\_properties) property names excluding symbol, but it can't find getter accessor unlike [`in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) operator, which can. To find also getter accessors use the [`isObjectKeyIn()`](isobjectkeyin.md) function.
{% endhint %}

{% code title="is-object-key.func.ts" %}
```typescript
const isObjectKey = <
  Obj extends object,
  Payload extends object = object
>(
  value: any,
  key: PropertyKey,
  callback: ResultCallback<any, { key: typeof key } & Payload> = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) ? {}.hasOwnProperty.call(value, key) : false,
    value,
    { ...payload, key } as any
  );
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-object-key.func.ts" %}

### Generic type variables

#### <mark style="color:green;">`Obj`</mark>`extends`<mark style="color:green;">`object`</mark>

A generic type variable `Obj` indicates the type of [`value`](isobjectkey.md#value-any) parameter by default [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) via the [return type](isobjectkey.md#return-type) `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkey.md#callback-resultcallback-less-than-any-key-typeof-key-and-payload-greater-than) function and [`payload`](isobjectkey.md#payload-payload) optional parameter of the [`isObjectKey()`](isobjectkey.md#isobjectkey) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check against an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that contains a key from a given [`key`](isobjectkey.md#key-propertykey).

#### `key: PropertyKey`

A property key to check if a given [`value`](isobjectkey.md#value-any) contains.

#### `callback: ResultCallback<any, { key: typeof key } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isobjectkey.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isobjectkey.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isobjectkey.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](isobjectkey.md#callback-resultcallback-less-than-any-key-typeof-key-and-payload-greater-than) function consists of the [`key`](isobjectkey.md#key-propertykey) property given in parameter of the core function, and it can't be overwritten by the given [`payload`](isobjectkey.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkey.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkey.md#callback-resultcallback-less-than-any-key-typeof-key-and-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the [`value`](isobjectkey.md#value-any) is a generic type variable [`Obj`](isobjectkey.md#obj) by default equal to the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isobjectkey.md#value-any) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with its [`key`](isobjectkey.md#key-propertykey).

## Example usage

```typescript
// Example usage.
import { isObjectKey } from '@angular-package/type';

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
isObjectKey(OBJECT_ONE, STRING); // true
isObjectKey(OBJECT_ONE, 1030405027); // true
isObjectKey(OBJECT_ONE, NUMBER); // true
isObjectKey(OBJECT_ONE, SYMBOL_NUMBER); // true
isObjectKey(OBJECT_ONE, SYMBOL_STRING); // true

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

// One of the differences between the `in` operator and the `hasOwnProperty()`
// method is that it doesn't find a getter key
isObjectKey(CLASS, SYMBOL_NUMBER); // false
isObjectKey(CLASS, SYMBOL_STRING); // false
```
