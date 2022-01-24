# guardObjectKeyIn()

## `guardObjectKeyIn()`

Guards the `value` to be an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobjectkeyin.md#objextendsobject) that contains(or its prototype chain) the given [`key`](guardobjectkeyin.md#key-key).

{% code title="guard-object-key-in.func.ts" %}
```typescript
const guardObjectKeyIn = <
  Obj extends object,
  Key extends keyof Obj,
  Payload extends object = object
>(
  value: Obj,
  key: Key,
  callback?: ResultCallback<Obj, { key: typeof key } & Payload>,
  payload?: Payload
): value is Obj => isObjectKeyIn(value, key, callback, payload as any);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Obj`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](guardobjectkeyin.md#value-type) via the [return type](guardobjectkeyin.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardobjectkeyin.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Key`**</mark>**`extends keyof`**<mark style="color:green;">**`Obj`**</mark>

A generic type variable `Key` constrained by the `keyof Obj`, by default of value captured from the supplied [`key`](guardobjectkeyin.md#key-key) indicates the specific property name of [`Obj`](guardobjectkeyin.md#objextendsobject).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardobjectkeyin.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardobjectkeyin.md#payload-payload) optional parameter of the [`guardObject()`](guardobjectkeyin.md#guardobject) function from which it captures its value.

### Parameters

#### `value: Obj`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobjectkeyin.md#objextendsobject), by default of the type captured from itself that contains(or its prototype chain) the given [`key`](guardobjectkeyin.md#key-key), to guard.

#### `key: Key`

A key of [`Obj`](guardobjectkeyin.md#objextendsobject) type, as the name of the property that the given [`value`](guardobjectkeyin.md#value-obj) contains(or its prototype chain).

#### `callback?: ResultCallback<Obj, { key: typeof key } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardobjectkeyin.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

{% hint style="info" %}
The `payload` parameter of the callback function consists of the `key` property given in the [`key`](guardobjectkeyin.md#key-key) parameter, and it can't be overwritten by the given [`payload`](guardobjectkeyin.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardobjectkeyin.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardobjectkeyin.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

**`value is Obj`**

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardobjectkeyin.md#value-obj) is an [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Obj`](guardobjectkeyin.md#objextendsobject), by default of type captured from the supplied [`value`](guardobjectkeyin.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardobjectkeyin.md#value-obj) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic [`Obj`](guardobjectkeyin.md#objextendsobject) that contains(or its prototype chain) the given [`key`](guardobjectkeyin.md#key-key).

### Example usage

```typescript
// Example usage.
import { guardObjectKeyIn } from '@angular-package/type';

const NUMBER = 10304050;
const STRING = '!@#$%^&*()abcdefghijklmnoprstuwyz';
const SYMBOL_NUMBER: unique symbol = Symbol(NUMBER);

interface ObjectOne {
  1030405027?: string;
  [NUMBER]: number;
  [STRING]: string;
  [SYMBOL_NUMBER]?: string;
}
const OBJECT_ONE: ObjectOne = {
  1030405027: 'key is number',
  [STRING]: 'key is string',
  [SYMBOL_NUMBER]: 'key is symbol number',
  get [NUMBER](): number {
    return NUMBER;
  },
};
guardObjectKeyIn(OBJECT_ONE, 1030405027); // true, value is ObjectOne
guardObjectKeyIn(OBJECT_ONE, SYMBOL_NUMBER); // true, value is ObjectOne
guardObjectKeyIn(OBJECT_ONE, STRING); // true, value is ObjectOne
guardObjectKeyIn(OBJECT_ONE, NUMBER); // true, value is ObjectOne

// Searching in an instance of `Class`.
class Class {
  get [NUMBER](): number {
    return NUMBER;
  }
}
const CLASS = new Class();
// Getter found.
guardObjectKeyIn(CLASS, NUMBER); // true, value is Class
```