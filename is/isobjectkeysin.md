# isObjectKeysIn()

## `isObjectKeysIn()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object)(by using the [`isObject()`](isobject.md)) with [`keys`](isobjectkeysin.md#keys-propertykey) of the `PropertyKey` in it(or its prototype chain) by using the [`in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) operator.

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

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-object-keys-in.func.ts" %}

### Generic type variables

#### <mark style="color:green;">`Obj`</mark>`=`<mark style="color:green;">`object`</mark>

A generic type variable `Obj` indicates the type of the given [`value`](isobjectkeysin.md#value-any) parameter via the [return type](isobjectkeysin.md#return-type) `value is Obj`, by default [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isobjectkeysin.md#callback-resultcallback-less-than-any-keys-typeof-keys-and-payload-greater-than) function and [`payload`](isobjectkeysin.md#payload-payload) optional parameter of the [`isObjectKeysIn()`](isobjectkeysin.md#isobjectkeysin) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check against the [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that contains(or its prototype chain) keys from the given [`keys`](isobjectkeysin.md#keys-propertykey).

#### `keys: PropertyKey[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of property keys to check if a given [`value`](isobjectkeysin.md#value-any) contains(or its prototype chain).

#### `callback: ResultCallback<any, { keys: typeof keys } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isobjectkeysin.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isobjectkeysin.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isobjectkeysin.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](isobjectkeysin.md#callback-resultcallback-less-than-any-keys-typeof-keys-and-payload-greater-than) function consists of the [`keys`](isobjectkeysin.md#keys-propertykey) property given in parameter of the core function, and it can't be overwritten by the given [`payload`](isobjectkeysin.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isobjectkeysin.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isobjectkeysin.md#callback-resultcallback-less-than-any-keys-typeof-keys-and-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isobjectkeysin.md#value-any) is a generic type variable [`Obj`](isobjectkeysin.md#obj-object) by default equal to the [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isobjectkeysin.md#value-any) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that contains(or its prototype chain) given [`keys`](isobjectkeysin.md#keys-propertykey).

## Example usage

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
