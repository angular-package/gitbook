# guardObjectSomeKeys()

## `guardObjectSomeKeys()`

Guards the value to be an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobjectsomekeys.md#objextendsobject) with some of its [`keys`](guardobjectsomekeys.md#keys-key) or some groups of its [`keys`](guardobjectsomekeys.md#keys-key). The function uses [`isObjectSomeKeys()`](../is/isobjectsomekeys.md) to search for the [`keys`](guardobjectsomekeys.md#keys-key).

{% code title="guard-object-some-keys.func.ts" %}
```typescript
const guardObjectSomeKeys = <
  Obj extends object,
  Payload extends object = object
>(
  value: Obj,
  keys: (keyof Obj | Array<keyof Obj>)[],
  callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>,
  payload?: Payload
): value is Obj => isObjectSomeKeys(value, keys, callback, payload as any);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Obj`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](guardobjectsomekeys.md#value-type) via the [return type](guardobjectsomekeys.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardobjectsomekeys.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardobjectsomekeys.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardobjectsomekeys.md#payload-payload) optional parameter of the [`guardObject()`](guardobjectsomekeys.md#guardobject) function from which it captures its value.

### Parameters

#### `value: Obj`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobjectsomekeys.md#objextendsobject), by default of the type captured from itself that contains some or some of the groups of the given [`keys`](guardobjectsomekeys.md#keys-key), to guard.

#### `keys: (keyof Obj | Array)[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of property names or a two-dimensional array of property names to check if the given [`value`](guardobjectsomekeys.md#value-obj) contains some of them.

#### `callback?: ResultCallback<Obj, { keys: typeof keys } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardobjectsomekeys.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

{% hint style="info" %}
The `payload` parameter of the callback function consists of the `keys` property given in the [`keys`](guardobjectsomekeys.md#keys-key) parameter, and it can't be overwritten by the given [`payload`](guardobjectsomekeys.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardobjectsomekeys.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardobjectsomekeys.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is`<mark style="color:green;">`Obj`</mark>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardobjectsomekeys.md#value-obj) is an [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Obj`](guardobjectsomekeys.md#objextendsobject), by default of type captured from the supplied [`value`](guardobjectsomekeys.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardobjectsomekeys.md#keys-key) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with some or some groups of the given [`keys`](guardobjectsomekeys.md#keys-key).

### Example usage

```typescript
// Example usage.
import { guardObjectSomeKeys } from '@angular-package/type';

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

guardObjectSomeKeys(OBJECT_ONE, [NUMBER, STRING]), // true, value is ObjectOne
guardObjectSomeKeys(OBJECT_ONE, ['no property' as any, STRING]), // true, value is ObjectOne
guardObjectSomeKeys(OBJECT_ONE, ['no property', 2 as any ]), // false, value is ObjectOne
guardObjectSomeKeys(OBJECT_ONE, [['no property'], [2 as any] ]), // false, value is ObjectOne
guardObjectSomeKeys(OBJECT_ONE, [
  [1030405027, NUMBER], // Or
  [1030405027, STRING], // Or
  [1030405027, SYMBOL_NUMBER]
]); // true, value is ObjectOne
```
