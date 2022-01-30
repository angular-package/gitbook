# guardObjectKey()

## `guardObjectKey()`

Guards the value to be an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of generic type variable [`Obj`](check-guardobjectkey.md#objextendsobject) that contains the given [`key`](check-guardobjectkey.md#key-key).

{% code title="guard-object-key.func.ts" %}
```typescript
const guardObjectKey = <
  Obj extends object,
  Key extends keyof Obj,
  Payload extends object = object
>(
  value: Obj,
  key: Key,
  callback?: ResultCallback<Obj, { key: typeof key } & Payload>,
  payload?: Payload
): value is Obj => isObjectKey(value, key, callback, payload as any);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/guard/lib/guard-object-key.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Obj`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](check-guardobjectkey.md#value-obj) via the [return type](check-guardobjectkey.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](check-guardobjectkey.md#callback-resultcallback-less-than-obj-key-typeof-key-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Key`**</mark>**`extends keyof`**<mark style="color:green;">**`Obj`**</mark>

A generic type variable `Key` constrained by the `keyof Obj`, by default of value captured from the supplied [`key`](check-guardobjectkey.md#key-key) indicates the specific property name of [`Obj`](check-guardobjectkey.md#objextendsobject).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](check-guardobjectkey.md#callback-resultcallback-less-than-obj-key-typeof-key-and-payload-greater-than) function and [`payload`](check-guardobjectkey.md#payload-payload) optional parameter of the [`guardObjectKey()`](check-guardobjectkey.md#guardobjectkey) function from which it captures its value.

### Parameters

#### `value: Obj`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](check-guardobjectkey.md#objextendsobject), by default of the type captured from itself that contains the given [`key`](check-guardobjectkey.md#key-key) to guard.

#### `key: Key`

A key of generic type variable [`Key`](check-guardobjectkey.md#keyextends-keyofobj) as the property name that the given [`value`](check-guardobjectkey.md#value-obj) contains.

#### `callback?: ResultCallback<Obj, { key: typeof key } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](check-guardobjectkey.md#value-obj) that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](check-guardobjectkey.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](check-guardobjectkey.md#callback-resultcallback-less-than-obj-key-typeof-key-and-payload-greater-than) function consists of the **`key`** property given in the [`key`](check-guardobjectkey.md#key-key) parameter, and it can't be overwritten by the given [`payload`](check-guardobjectkey.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](check-guardobjectkey.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](check-guardobjectkey.md#callback-resultcallback-less-than-obj-key-typeof-key-and-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](check-guardobjectkey.md#value-obj) is an [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Obj`](check-guardobjectkey.md#objextendsobject), by default of type captured from the supplied [`value`](check-guardobjectkey.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](check-guardobjectkey.md#value-obj) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic [`Obj`](check-guardobjectkey.md#objextendsobject) that contains the given [`key`](check-guardobjectkey.md#key-key).

## Example usage

```typescript
// Example usage.
import { guardObjectKey } from '@angular-package/type';

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

guardObjectKey(OBJECT_ONE, 1030405027); // true, value is ObjectOne
guardObjectKey(OBJECT_ONE, SYMBOL_NUMBER); // true, value is ObjectOne
guardObjectKey(OBJECT_ONE, STRING); // true, value is ObjectOne
// Getter found in the object.
guardObjectKey(OBJECT_ONE, NUMBER); // true, value is ObjectOne

// Searching in an instance of `Class`.
class Class {
  get [NUMBER](): number {
    return NUMBER;
  }
}
const CLASS = new Class();
// Getter not found.
guardObjectKey(CLASS, NUMBER); // false, value is Class
```
