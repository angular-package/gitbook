# isObjectKeys()

## `isObjectKeys()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object)(by using the [`isObject()`](isobject.md)) with its keys by using [`hasOwnProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/hasOwnProperty) method of [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object).

{% hint style="info" %}
The function uses the [`hasOwnProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/hasOwnProperty) method of [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) to find enumerable and non-enumerable `PropertyKey` as string, number, symbol unlike [`Object.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/keys) that finds only [enumerable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability\_and\_ownership\_of\_properties) property names excluding symbol, but it can't find getter accessor unlike [`in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) operator, which can. To find also getter accessors use the [`isObjectKeysIn()`](isobjectkeysin.md) function.
{% endhint %}

{% code title="is-object-keys.func.ts" %}
```typescript
const isObjectKeys = <Obj = object, Payload extends object = object>(
  value: any,
  keys: PropertyKey[],
  callback: ResultCallback<
    any,
    { keys: typeof keys } & Payload
  > = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) && isArray(keys)
    ? keys.every((key) => ({}.hasOwnProperty.call(value, key)))
    : false,
    value,
    { ...payload, keys } as any
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Obj`</mark>`=`<mark style="color:green;">`object`</mark>

A generic type variable `Obj` indicates the type of [`value`](isobjectkeys.md#value-any) parameter by default [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) via the [return type](isobjectkeys.md#return-type) `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkeys.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isobjectkeys.md#payload-payload) optional parameter of the [`isObjectKeys()`](isobjectkeys.md#isobjectkeys) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check against an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that contains its keys from given [`keys`](isobjectkeys.md#keys-propertykey).

#### `keys: PropertyKey[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of property keys to check if a given [`value`](isobjectkeys.md#value-any) contains all of them.

#### `callback: ResultCallback<any, { keys: typeof keys } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isobjectkeys.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isobjectkeys.md#payloadextendsobject) with optional properties from the provided [`payload`](isobjectkeys.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](isobjectkeys.md#callback-resultcallback-less-than-any-payload-greater-than) function consists of the [`keys`](isobjectkeys.md#keys-propertykey) property given in parameter of the core function, and it can't be overwritten by the given [`payload`](isobjectkeys.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkeys.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkeys.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isobjectkeys.md#value-any) is a generic type variable [`Obj`](isobjectkeys.md#obj-object) by default equal to the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isobjectkeys.md#value-any) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) with its [`keys`](isobjectkeys.md#keys-propertykey).

## Example usage

```typescript
// Example usage.
import { isObjectKeys } from '@angular-package/type';

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
isObjectKeys(person, ['firstName']); // Returns `true` as `value is object`.
isObjectKeys(person, ['firstName', 'surname']); // Returns `true` as `value is object`.
isObjectKeys(person, ['firstName', 'no property']); // Returns `false` as `value is object`.
// Getter.
isObjectKeys(person, ['getAge']); // Returns `false` as `value is object`.
// not enumerable.
isObjectKeys(person, ['notEnumerable']); // Returns `true` as `value is object`.
/*
  Returns [
    "firstName",
    "surname",
    "age",
    "city",
    "sex"
]
*/
Object.keys(person);
```
