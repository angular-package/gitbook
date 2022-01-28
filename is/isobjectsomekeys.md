# isObjectSomeKeys()

## `isObjectSomeKeys()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) by using the [`isObject()`](isobject.md) function with some of its keys or some groups of its keys of the `PropertyKey` type.

{% hint style="info" %}
The two-dimensional `Array` of the given [`value`](isobjectsomekeys.md#value-any) is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of [`Arrays`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) where the relation between elements of the first [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) is a logical **OR**, and the relationship between elements of the second [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) is a logical **AND**.

The logical **OR** results from the use of the [`some()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/some) method of the [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array), and a logical **`AND`** result from [`every()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/every).
{% endhint %}

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

#### <mark style="color:green;">`Obj`</mark>`extends`<mark style="color:green;">`object`</mark>

A generic type variable `Obj` constrained by the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of the given [`value`](isobjectsomekeys.md#value-any) parameter by default [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) via the [return type](isobjectsomekeys.md#return-type) `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectsomekeys.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectsomekeys.md#payload-payload) optional parameter of the [`isObjectSomeKeys()`](isobjectsomekeys.md#isobjectsomekeys) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check against an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that contains some of its keys or some groups of its keys from a given [`keys`](isobjectsomekeys.md#keys-propertykey-or-propertykey).

#### `keys: (PropertyKey | PropertyKey[])[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of property names or a two-dimensional [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of property names to check if the given [`value`](isobjectsomekeys.md#value-any) contains some of them or some groups of them.

#### `callback: ResultCallback<any, { keys: typeof keys } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isobjectsomekeys.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isobjectsomekeys.md#payloadextendsobject) with optional properties from the provided [`payload`](isobjectsomekeys.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](isobjectsomekeys.md#callback-resultcallback-less-than-any-keys-typeof-keys-and-payload-greater-than) function consists of the [`keys`](isobjectsomekeys.md#keys-propertykey-or-propertykey) property given in parameter of the core function, and it can't be overwritten by the given [`payload`](isobjectsomekeys.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectsomekeys.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectsomekeys.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isobjectsomekeys.md#value-any) is a generic type variable [`Obj`](isobjectsomekeys.md#obj-extends-object) by default equal to the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isobjectsomekeys.md#value-any) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with some of its keys or some groups of its keys from a given [`keys`](isobjectsomekeys.md#keys-propertykey-or-propertykey).

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
