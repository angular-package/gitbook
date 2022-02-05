# guardObjectKeysIn()

## `guardObjectKeysIn()`

Guards the value to be an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobjectkeysin.md#objextendsobject) with specified keys in it(or its prototype chain).

{% code title="guard-object-keys-in.func.ts" %}
```typescript
const guardObjectKeysIn = <
  Obj extends object,
  Key extends keyof Obj,
  Payload extends object = object
>(
  value: Obj,
  keys: Key[],
  callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>,
  payload?: Payload
): value is Obj => isObjectKeysIn(value, keys, callback, payload as any);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/guard/lib/guard-object-keys-in.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Obj`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](guardobjectkeysin.md#value-obj) via the [return type](guardobjectkeysin.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardobjectkeysin.md#callback-resultcallback-less-than-obj-keys-typeof-keys-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Key`**</mark>**`extends keyof`**<mark style="color:green;">**`Obj`**</mark>

A generic type variable `Key` constrained by the `keyof Obj`, by default of value captured from the supplied [`keys`](guardobjectkeysin.md#keys-key) indicates the specific property name of [`Obj`](guardobjectkeysin.md#objextendsobject).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardobjectkeysin.md#callback-resultcallback-less-than-obj-keys-typeof-keys-and-payload-greater-than) function and [`payload`](guardobjectkeysin.md#payload-payload) optional parameter of the [`guardObjectKeysIn()`](guardobjectkeysin.md#guardobjectkeysin) function from which it captures its value.

### Parameters

#### `value: Obj`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable `Obj`, by default of the type captured from itself that contains(or its prototype chain) the given [`keys`](guardobjectkeysin.md#keys-key) to guard.

#### `keys: Key[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of property keys to check whether the given [`value`](guardobjectkeysin.md#value-obj) contains(or its prototype chain).

#### `callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](guardobjectkeysin.md#value-obj) that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardobjectkeysin.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

{% hint style="info" %}
The `payload` parameter of the callback function consists of the **`keys`** property given in the [`keys`](guardobjectkeysin.md#keys-key) parameter, and it can't be overwritten by the given [`payload`](guardobjectkeysin.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardobjectkeysin.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardobjectkeysin.md#callback-resultcallback-less-than-obj-keys-typeof-keys-and-payload-greater-than) function.

### Return type

#### `value is`<mark style="color:green;">`Obj`</mark>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardobjectkeysin.md#value-obj) is an [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Obj`](guardobjectkeysin.md#objextendsobject), by default of type captured from the supplied [`value`](guardobjectkeysin.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardobjectkeysin.md#value-obj) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with specified [`keys`](guardobjectkeysin.md#keys-key) in it(or its prototype chain).

## Example usage

```typescript
// Example usage.
import { guardObjectKeysIn } from '@angular-package/type';

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

guardObjectKeysIn(OBJECT_ONE, [
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
// Getter found.
guardObjectKeysIn(CLASS, [NUMBER]); // true, value is Class
```