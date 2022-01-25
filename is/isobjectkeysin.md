# isObjectKeysIn()

### `isObjectKeysIn()`

Checks if any value is an `object` by using the `isObject()` function with keys of the `PropertyKey` in it(or its prototype chain) by using the `in` operator.

Use `isObjectKeysIn()` or `is.objectKeysIn()` to check if **any** value is an \[`object`]\[js-object] with keys in it(or its prototype chain) by using the \[`in`]\[js-in-operator] operator.

{% code title="is-object-keys-in.func.ts" %}
```typescript
const isObjectKeysIn = <Obj = object, Payload extends object = object>(
  value: any,
  keys: PropertyKey[],
  callback: ResultCallback<
    any,
    { keys: typeof keys } & Payload
  > = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) && isArray(keys) ? keys.every((k) => k in value) : false,
    value,
    { ...payload, keys } as any
  );
```
{% endcode %}

### Generic type variables

`Obj`

A generic type variable `Obj` indicates the type of `value` parameter by default `object` via the return type `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkeysin.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectkeysin.md#payload-payload) optional parameter of the [`isObjectKeysIn()`](isobjectkeysin.md#isobjectkeysin) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

The value of any type to check against an \[`object`]\[js-object] that contains(or its prototype chain) keys from given `keys`.

#### `keys: PropertyKey[]`

An \[`Array`]\[js-array] of property keys to check if a given `value` contains(or its prototype chain) all of them.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkeysin.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkeysin.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type variable `Obj` by default equal to the `object`.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is an `object` that contains(or its prototype chain) given `keys`.

### Example usage

```typescript
// Example usage.
import { isObjectKeysIn } from '@angular-package/type';

class Person {
  firstName = 'name';
  surname = 'surname';
  age = 27;
  city = 'New York';
  sex = 'Male';
  get getAge(): number {
    return this.age;
  }
}
const person = new Person();
// Define property.
Object.defineProperty(person, 'notEnumerable', { enumerable: false });
person.propertyIsEnumerable('notEnumerable'); // Returns `false`.
isObjectKeysIn(person, ['firstName']); // Returns `true` as `value is object`.
isObjectKeysIn(person, ['firstName', 'surname']); // Returns `true` as `value is object`.
isObjectKeysIn(person, ['firstName', 'no property']); // Returns `false` as `value is object`.
// Getter.
isObjectKeysIn(person, ['getAge']); // Returns `true` as `value is object`.
// not enumerable.
isObjectKeysIn(person, ['notEnumerable']); // Returns `true` as `value is object`.
```
