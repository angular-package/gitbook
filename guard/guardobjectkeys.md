# guardObjectKeys()

## `guardObjectKeys()`

Guards the value to be an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobjectkeys.md#objextendsobject) with its specified [`keys`](guardobjectkeys.md#keys-key).

{% code title="guard-object-keys.func.ts" %}
```typescript
const guardObjectKeys = <
  Obj extends object,
  Key extends keyof Obj,
  Payload extends object = object
>(
  value: Obj,
  keys: Key[],
  callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>,
  payload?: Payload
): value is Obj => isObjectKeys(value, keys, callback, payload as any);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Obj`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](guardobjectkeys.md#value-type) via the [return type](guardobjectkeys.md#return-type) and the [`value`](../type/resultcallback.md#value-value) parameter of the provided [`callback`](guardobjectkeys.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../type/resultcallback.md) type.

#### <mark style="color:green;">**`Key`**</mark>**`extends keyof`**<mark style="color:green;">**`Obj`**</mark>

A generic type variable `Key` constrained by the `keyof Obj`, by default of value captured from the supplied [`keys`](guardobjectkeys.md#keys-key) indicates the specific property name of [`Obj`](guardobjectkeys.md#objextendsobject).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../type/resultcallback.md#payload-payload) of the supplied [`callback`](guardobjectkeys.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardobjectkeys.md#payload-payload) optional parameter of the [`guardObject()`](guardobjectkeys.md#guardobject) function from which it captures its value.

### Parameters

#### `value: Obj`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobjectkeys.md#objextendsobject), by default of the type captured from itself that contains the given [`keys`](guardobjectkeys.md#keys-key) to guard.

#### `keys: Key[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of property keys to check whether the given [`value`](guardobjectkeys.md#value-obj) contains.

#### `callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardobjectkeys.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

{% hint style="info" %}
The `payload` parameter of the callback function consists of the `keys` property given in the [`keys`](guardobjectkeys.md#keys-key) parameter, and it can't be overwritten by the given [`payload`](guardobjectkeys.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardobjectkeys.md#payloadextendsobject-object) is assigned to the [`payload`](../type/resultcallback.md#payload-payload) of the given [`callback`](guardobjectkeys.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardobjectkeys.md#value-obj) is an [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Obj`](guardobjectkeys.md#objextendsobject), by default of type captured from the supplied [`value`](guardobjectkeys.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardobjectkeys.md#value-obj) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with its specified [`keys`](guardobjectkeys.md#keys-key).

### Example usage

```typescript
// Example usage.
import { guardObjectKeys } from '@angular-package/type';

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

guardObjectKeys(OBJECT_ONE, [
  STRING,
  SYMBOL_NUMBER,
  NUMBER,
  1030405027]); // true, value is Class

// Searching in an instance of `Class`.
class Class {
  get [NUMBER](): number {
    return NUMBER;
  }
}
const CLASS = new Class();
// Getter not found.
guardObjectKeys(CLASS, [NUMBER]); // false, value is Class
```
