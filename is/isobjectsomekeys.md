# isObjectSomeKeys()

## `isObjectSomeKeys()`

Checks if any value is an `object` by using the `isObject()` function with some of its keys or some groups of its keys of the `PropertyKey` type.

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) by using the [`isObject()`](isobject.md) function with some of its keys or some groups of its keys of the `PropertyKey` type.

Use `isObjectSomeKeys()` or `is.objectSomeKeys()` to check if **any** value is an \[`object`]\[js-object] with **some** of its keys or **some groups** of its keys of the `PropertyKey` type. Because of using \[`some()`]\[js-array-some] method on the given `keys` parameter of \[`Array`]\[js-array] type relation between its elements are treated as logic `or`, and if an element is an \[`Array`]\[js-array] type because of using \[`every()`]\[js-array-every] method, the relation between its elements are treated as logic `and`.

{% code title="is-object-some-keys.func.ts" %}
```typescript
const isObjectSomeKeys = <
  Obj extends object,
  Payload extends object = object
>(
  value: any,
  keys: (PropertyKey | PropertyKey[])[],
  callback: ResultCallback<
    any,
    { keys: typeof keys } & Payload
  > = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) && isArray(keys)
    ? keys.some((someKey) =>
        isArray(someKey)
          ? someKey.every((everyKey) =>
              ({}.hasOwnProperty.call(value, everyKey))
            )
          : {}.hasOwnProperty.call(value, someKey) === true
      )
    : false,
    value,
    { ...payload, keys } as any
  );
```
{% endcode %}

### Generic type variables



A generic type variable `Obj` constrained by the `object` indicates the type of `value` parameter by default `object` via the return type `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectsomekeys.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectsomekeys.md#payload-payload) optional parameter of the [`isObjectSomeKeys()`](isobjectsomekeys.md#isobjectsomekeys) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

The value of any type to check against an \[`object`]\[js-object] that contains some of its keys or some groups of its keys from a given `keys`.

#### `keys: (PropertyKey | PropertyKey[])[]`

An \[`Array`]\[js-array] of property names or a two-dimensional array of property names to check if the given `value` contains some of them or some groups of them.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectsomekeys.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectsomekeys.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type variable `Obj` by default equal to the `object`.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is an `object` with some of its keys or some groups of its keys from a given `keys`.

## Example usage

```typescript
// Example usage.
import { isObjectSomeKeys } from '@angular-package/type';

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
isObjectSomeKeys(person, ['firstName']); // Returns `true` as `value is object`.
isObjectSomeKeys(person, ['firstName', 'surname']); // Returns `true` as `value is object`.
isObjectSomeKeys(person, ['firstName', 'no property']); // Returns `true` as `value is object`.
// Getter.
isObjectSomeKeys(person, ['getAge']); // Returns `false` as `value is object`.
// not enumerable.
isObjectSomeKeys(person, ['notEnumerable']); // Returns `true` as `value is object`.
isObjectSomeKeys(person, [['firstName', 'surname'], ['city', 'age']]); // Returns `true` as `value is object`.
isObjectSomeKeys(person, [['firstName', 'surname'], ['city', 'no property']]); // Returns `true` as `value is object`.
isObjectSomeKeys(person, [['firstName1', 'surname1'], ['city1', 'no property']]); // Returns `false` as `value is object`.
```
